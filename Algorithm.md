# 演算法 (Python) 筆記 

- Start: [time=Sun, Aug 3, 2025 10:39 AM]
- Last Update: [time=Tue, Aug 12, 2025 8:35 PM]

### K-means 集群演算法

```python=
import matplotlib.pyplot as plt
import numpy as np
import random

i = random.random()

# Generate a 2x3 array of random floats
# np.random.rand(2, 3)
# numArr = np.floor(np.random.rand(1, 10) * 10).astype(int)
numArr = np.random.randint(0, 10, size=(1, 10))
print(numArr)

x = [4, 5, 10, 4, 3, 11, 14 , 6, 10, 12]
y = [21, 19, 24, 17, 16, 25, 24, 22, 21, 21]

plt.scatter(x, y)
plt.show()
```

- [K-means - W3schools](http://w3schools.com/python/python_ml_k-means.asp)
- [time=Sun, Aug 3, 2025 10:40 AM]


### Support Vector Machine SVM 支持向量機

Support Vector Machines (SVM) are a powerful supervised learning algorithm used for classification, regression, and outlier detection. Below is an example of how to implement SVM in Python using the scikit-learn library:

- SVM for Classification

```python=
from sklearn import datasets
from sklearn.model_selection import train_test_split
from sklearn.svm import SVC
from sklearn.metrics import accuracy_score

# Load dataset (Iris dataset as an example)
iris = datasets.load_iris()
X = iris.data  # Features
y = iris.target  # Labels

# Split dataset into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

# Create and train the SVM model
svm_model = SVC(kernel='linear', C=1.0)  # Linear kernel
svm_model.fit(X_train, y_train)

# Make predictions
y_pred = svm_model.predict(X_test)

# Evaluate the model
accuracy = accuracy_score(y_test, y_pred)
print(f"Accuracy: {accuracy:.2f}")
```

```
Key Parameters:
kernel: Specifies the kernel type (e.g., 'linear', 'rbf', 'poly').
C: Regularization parameter. A smaller value specifies stronger regularization.
gamma: Kernel coefficient for 'rbf', 'poly', and 'sigmoid'.
Notes:
You can experiment with different kernels and hyperparameters to optimize performance.
For non-linear data, consider using the 'rbf' kernel.
Let me know if you'd like further clarification or examples!
```
- [time=Tue, Aug 5, 2025 4:14 AM]


### Principle Component Analysis (PCA)

#### Overview

Principal Component Analysis (PCA) is a statistical technique for reducing the dimensionality of a dataset while preserving as much variance (information) as possible.  

Through an orthogonal linear transformation, PCA converts a set of possibly correlated variables into a new set of uncorrelated variables called principal components. The first few components capture the largest share of variability, enabling simpler representations of high-dimensional data.

---


#### When and Why to Use PCA

- Dimensionality Reduction  
  Reduce the number of features from $n$ to a smaller $r(r < n)$ while retaining most of the dataset’s variability.

- Noise Filtering  
  Eliminate directions (components) that capture little variance, often representing noise.

- Visualization  
  Project high-dimensional data onto 2D or 3D to reveal clusters, trends, or outliers.

- Feature Engineering  
  Create new orthogonal features that can improve downstream modeling and reduce multicollinearity.

---


#### Mathematical Formulation

1. **Data Centering**  
   Subtract the mean of each feature so that each column of $X\in\mathbb{R}^{m\times n}$ has zero mean:  
   $$
     X_{\text{centered}} = X - \frac{1}{m}\mathbf{1}_m\,\mathbf{1}_m^\top\,X.
   $$

2. **Covariance Matrix**  
   Compute the covariance matrix:  
   $$
     \Sigma = \frac{1}{m-1}\,X_{\text{centered}}^\top\,X_{\text{centered}}.
   $$

3. **Eigen Decomposition**  
   Find eigenvalues \(\lambda_1 \ge \lambda_2 \ge \dots \ge \lambda_n\) and eigenvectors \(v_1, v_2, \dots, v_n\) of \(\Sigma\):  
   $$
     \Sigma\,v_i = \lambda_i\,v_i,\quad \|v_i\|_2 = 1.
   $$

4. **Principal Components**  
   Form the projection matrix $V_r = [\,v_1\;v_2\;\dots\;v_r\,]$. The transformed data is  
   $$
     Y = X_{\text{centered}}\,V_r,
   $$  
   where the \(i\)-th column of \(Y\) is the \(i\)-th principal component.

---


#### Algorithmic Steps

1. **Standardize** each feature of \(X\) (optional but recommended when variables have different units).  
2. **Center** the data by subtracting feature means.  
3. **Compute** covariance matrix \(\Sigma\).  
4. **Perform** eigen decomposition of \(\Sigma\).  
5. **Sort** eigenvectors by descending eigenvalues.  
6. **Select** top \(r\) eigenvectors to form \(V_r\).  
7. **Project** data: \(Y = X_{\text{centered}}\,V_r\).  

---

#### Practical Implementation

#### From Scratch (NumPy)

```python
import numpy as np

def pca(X, r):
    # 1. Center
    Xc = X - np.mean(X, axis=0)
    # 2. Covariance
    Sigma = np.cov(Xc, rowvar=False)
    # 3. Eigen decomposition
    eigvals, eigvecs = np.linalg.eigh(Sigma)
    # 4. Sort descending
    idx = np.argsort(eigvals)[::-1]
    eigvecs = eigvecs[:, idx]
    eigvals = eigvals[idx]
    # 5. Select top r
    V_r = eigvecs[:, :r]
    # 6. Project
    Y = Xc.dot(V_r)
    return Y, eigvals[:r], V_r
```


##### Using scikit-learn

```python
from sklearn.decomposition import PCA
pca_model = PCA(n_components=r)
Y = pca_model.fit_transform(X)
explained_variance = pca_model.explained_variance_ratio_
```


#### Interpreting Principal Components

| Component | Eigenvalue ($\lambda$) | Explained Variance Ratio |
|:---------:|:------------------------:|:------------------------:|
| PC1       | $\lambda_1$            | $\lambda_1 / \sum \lambda_i$ |
| PC2       | $\lambda_2$            | $\lambda_2 / \sum \lambda_i$ |
| …         | …                        | …                        |
| PC $r$   | $\lambda_r$            | $\lambda_r / \sum \lambda_i$ |

- **Eigenvalue** measures variance captured by each component.  
- **Cumulative variance** helps choose $r$ so that $\sum_{i=1}^r \lambda_i / \sum_{j=1}^n \lambda_j$ exceeds a threshold (e.g., 90%).


#### Applications

- Exploratory Data Analysis (EDA)  
- Preprocessing for machine learning pipelines  
- Image compression and denoising  
- Genomics (population structure in GWAS)  
- Finance (risk factor modeling)  
- Sensor fusion and anomaly detection


#### Beyond Standard PCA

- **Kernel PCA**: Captures nonlinear structure via kernel functions.  
- **Robust PCA**: Decomposes data into low-rank plus sparse matrices to handle gross outliers.  
- **Sparse PCA**: Enforces sparsity in principal components for interpretability.  
- **Factor Analysis**: Models latent factors that explain correlations among variables.  


PCA remains one of the most widely used dimensionality-reduction techniques thanks to its simplicity, computational efficiency, and clear geometric interpretation.  

For further exploration, consider comparing PCA against manifold learning methods (t-SNE, UMAP) when the data exhibits strong nonlinear structure.

- [time=Tue, Aug 12, 2025 2:38 PM]

### Interpreting PCA Results

#### Scree Plot and Explained Variance

To understand how many principal components to keep, plot the eigenvalues or explained variance ratio against component index.  

- The **scree plot** displays eigenvalues $\lambda_i$ on the vertical axis versus component number on the horizontal axis.  
- Look for the “elbow,” where additional components start contributing diminishing returns.  
- The **explained variance ratio** for component $i$ is $\lambda_i / \sum_j \lambda_j$.  


#### Choosing the Number of Components

You typically choose $r$ so that the cumulative explained variance exceeds a threshold (commonly 80%–95%).  

| Component | Eigenvalue $\lambda_i$ | Explained Variance Ratio | Cumulative Ratio |
|:---------:|:------------------------:|:------------------------:|:----------------:|
| PC1       | $\lambda_1$            | $\lambda_1 / \sum_j\lambda_j$   | $\sum_{k=1}^1 \lambda_k / \sum_j\lambda_j$   |
| PC2       | $\lambda_2$            | $\lambda_2 / \sum_j\lambda_j$   | $\sum_{k=1}^2 \lambda_k / \sum_j\lambda_j$   |
| …         | …                        | …                            | …                  |
| PC$r$   | $\lambda_r$            | $\lambda_r / \sum_j\lambda_j$   | $\sum_{k=1}^r \lambda_k / \sum_j\lambda_j$   |


#### Inspecting Loadings

Loadings (elements of eigenvectors) reveal how original variables contribute to each component.  

- A large positive loading on PC1 for variable $x_j$ means $x_j$ drives that principal axis in the positive direction.  
- Negative loadings indicate that the variable moves opposite to the principal axis.  
- Variables with near-zero loadings have little influence on that component.  


#### Examining Scores

Scores are the coordinates of each sample in the principal component space (rows of $Y$).  

- Plotting PC1 vs. PC2 scores often exposes clustering, outliers, or gradients.  
- Samples close in this scatterplot are similar in the high-dimensional space.  
- Color-coding points by class, time, or another external label can reveal hidden structure.  


#### Biplot Interpretation

A biplot overlays loadings and scores in the same plot:  

- **Arrows** represent variables (loadings). Arrow direction and length show correlation with PCs.  
- **Points** represent samples (scores). Their position relative to arrows indicates which variables drive their separation.  
- Variables pointing in similar directions are positively correlated.  


#### Practical Steps in Python

```python
from sklearn.decomposition import PCA
import matplotlib.pyplot as plt
import pandas as pd

# Fit PCA
pca = PCA()
scores = pca.fit_transform(X)                # shape: (n_samples, n_features)
loadings = pca.components_.T                 # shape: (n_features, n_components)
explained = pca.explained_variance_ratio_

# Scree plot
plt.plot(range(1, len(explained)+1), explained.cumsum(), marker='o')
plt.xlabel('Number of Components')
plt.ylabel('Cumulative Explained Variance')
plt.show()

# Biplot for PC1 vs PC2
fig, ax = plt.subplots()
ax.scatter(scores[:,0], scores[:,1])
for i, var in enumerate(feature_names):
    ax.arrow(0, 0, loadings[i,0]*max(scores[:,0]), loadings[i,1]*max(scores[:,1]),
             head_width=0.05, length_includes_head=True)
    ax.text(loadings[i,0]*max(scores[:,0])*1.1, loadings[i,1]*max(scores[:,1])*1.1, var)
ax.set_xlabel('PC1')
ax.set_ylabel('PC2')
plt.show()
```


#### Common Pitfalls and Best Practices

- Always **standardize** features before PCA if they have different units or scales.  
- Beware of over-interpreting small components that capture little variance.  
- Remember that PCA is linear—nonlinear relationships remain hidden.  
- Use domain knowledge to validate which variables drive each principal component.  


As you explore your PCA results, try combining score plots with external metadata (labels, timepoints) and comparing different subsets of variables. When greater flexibility is needed, consider kernel PCA or nonlinear embedding methods such as t-SNE or UMAP for deeper structure discovery.

- [time=Tue, Aug 12, 2025 3:12 PM]


### Q-Learning Overview

Q-learning is a model-free, value-based, off-policy reinforcement learning algorithm that computes an optimal action-value function \(Q^*(s,a)\) without requiring a model of the environment’s dynamics.


#### Definition and Objective

Q-learning seeks to learn the expected cumulative discounted reward for taking action \(a\) in state \(s\) and thereafter following the optimal policy. The ultimate goal is to derive a policy \(\pi^*\) that maximizes:

$$
\max_{\pi} \mathbb{E}_{\pi}\Bigl[\sum_{t=0}^{H} \gamma^t R(s_t,a_t)\Bigr]
$$

where:
- $s_t$ and $a_t$ are state and action at time $t$.  
- $R(s_t,a_t)$ is the immediate reward.  
- $\gamma\in[0,1)$ is the discount factor.  
- $H$ is the (possibly infinite) horizon length.


#### Key Components

- **State space** ($\mathcal{S}$): All possible configurations of the environment.  
- **Action space** ($\mathcal{A}$): Legal moves the agent can make in each state.  
- **Reward** ($r$): Scalar feedback the environment gives after each action.  
- **Policy** ($\pi$): Mapping from states to actions (deterministic or stochastic).  
- **Action-value function** $Q(s,a)$: Estimate of expected return when choosing $a$ in $s$ and acting optimally thereafter.


#### The Q-learning Algorithm

1. **Initialize**  
   Create a Q-table $Q(s,a)$ with zero or small random values for all $(s,a)$ pairs.  

2. **Repeat for each episode**  
   2.1 Set initial state $s$.  
   2.2 For each step until terminal state:  
   &emsp;a. Select action $a$ using an exploration strategy (e.g., $\varepsilon$-greedy).  
   &emsp;b. Execute $a$, observe reward $r$ and next state $s'$.  
   &emsp;c. Update the Q-value:  
   $$
   Q(s,a)\leftarrow Q(s,a) + \alpha\Bigl(r + \gamma\max_{a'}Q(s',a') - Q(s,a)\Bigr).
   $$  
   &emsp;&emsp;$\alpha$ is the learning rate; $\gamma$ is the discount factor.  
   &emsp;d. Set $s \leftarrow s'$.  


#### Pseudocode

```plaintext
Initialize Q-table Q[s,a] ← 0 for all s ∈ S, a ∈ A
For episode = 1 to M do
  Initialize state s
  Repeat
    With probability ε select random action a
    Otherwise select a = argmax_a' Q[s,a']
    Execute a, observe reward r and next state s'
    Q[s,a] ← Q[s,a]
             + α [ r + γ max_{a'} Q[s',a'] − Q[s,a] ]
    s ← s'
  Until s is terminal
End
```


#### Python Snippet

```python
import numpy as np
import random

class QLearner:
    def __init__(self, states, actions, alpha=0.1, gamma=0.99, epsilon=0.1):
        self.Q = np.zeros((len(states), len(actions)))
        self.alpha, self.gamma, self.epsilon = alpha, gamma, epsilon
        self.actions = actions

    def choose_action(self, s):
        if random.random() < self.epsilon:
            return random.choice(self.actions)
        return np.argmax(self.Q[s])

    def update(self, s, a, r, s_next):
        best_next = np.max(self.Q[s_next])
        td_target = r + self.gamma * best_next
        td_error = td_target - self.Q[s, a]
        self.Q[s, a] += self.alpha * td_error
```


#### Convergence and Properties

- Off-policy: Learns $Q^*$ independently of the policy used to generate data.  
- Guaranteed convergence to the optimal $Q^*$ under infinite exploration and a decaying learning rate.  
- Applicable when the environment model is unknown or too complex to simulate.


#### Practical Tips

- Always decay ε over time to shift from exploration to exploitation.  
- Normalize rewards or clip their range for numerical stability.  
- In large or continuous state spaces, replace the Q-table with function approximators (e.g., Deep Q-Networks).  
- Monitor convergence via tracking the maximum change in $Q$ per episode.


#### Extensions

- **Deep Q-Learning (DQN)**: Uses neural networks to approximate $Q(s,a)$.  
- **Double Q-learning**: Reduces overestimation bias by maintaining two Q-value estimators.  
- **SARSA**: On-policy counterpart that updates using the action actually taken in the next state.

- [time=Tue, Aug 12, 2025 3:20 PM]

### Deep Q-Learning Overview

Deep Q-Learning (DQN) extends classic Q-Learning by approximating the action-value function with a neural network, enabling agents to handle high-dimensional inputs such as raw pixels.


#### Why “Deep”?

  
Classic Q-Learning stores a Q-table mapping every state–action pair to a value. When the state space grows (e.g., video frames in Atari), tabular methods become infeasible. DQN uses a parameterized function $Q(s,a; \mathbf w)$ (often a convolutional neural network) to generalize across similar states.


#### Historical Milestone

In 2015, DeepMind introduced DQN and demonstrated human-level performance on many Atari 2600 games by feeding raw screen images into a convolutional neural network and learning directly from pixels to actions.


#### Core Components

- Replay Memory  
  Transitions $(s_t, a_t, r_t, s_{t+1})$ are stored in a finite buffer $D$. During training, minibatches are uniformly sampled from $D$ to break correlations between sequential frames and improve data efficiency.

- Target Network  
  A second network with parameters $\mathbf w^-$ is held fixed for multiple update steps. Periodically, $\mathbf w^- \leftarrow \mathbf w$. This stabilizes bootstrapped targets by decoupling the target calculation from rapidly changing online parameters.

- Network Architecture  
  For pixel-based tasks, DQN uses a convolutional backbone to extract spatial features, followed by fully connected layers that output one Q-value per action.  


#### Loss and Parameter Update
  
The DQN loss is the mean squared temporal-difference error over a sampled minibatch:

$$
L(\mathbf w) \;=\;\mathbb{E}_{(s,a,r,s')\sim D}\Bigl[\bigl(r + \gamma\,\max_{a'}Q(s',a';\mathbf w^-)\;-\;Q(s,a;\mathbf w)\bigr)^{2}\Bigr].
$$

Gradients are computed via backpropagation and used to update $\mathbf w$ by stochastic gradient descent.


#### Algorithm Pseudocode

```plaintext
Initialize replay memory D to capacity N
Initialize online Q-network with random weights w
Initialize target Q-network with weights w− ← w

For episode = 1 to M:
  Initialize state s
  For t = 1 to T:
    With probability ε select random action a
    Else a ← argmax_a' Q(s,a';w)
    Execute action a, observe reward r and next state s'
    Store (s, a, r, s') in D
    Sample random minibatch of transitions (s_j, a_j, r_j, s_j') from D
    Compute TD target: 
      y_j = r_j + γ max_{a'} Q(s_j', a'; w−)
    Perform gradient descent step on 
      (y_j − Q(s_j, a_j; w))^2 with respect to w
    Every C steps: w− ← w
    s ← s'
```


#### Common Extensions

| Improvement                   | Purpose                                                            | Citation |
|-------------------------------|--------------------------------------------------------------------|:--------:|
| Double DQN                    | Mitigates Q-value overestimation by decoupling action selection and evaluation  |      |
| Dueling DQN                   | Separates state-value and advantage streams for faster learning    |      |
| Prioritized Experience Replay | Samples high-TD-error transitions more often for efficiency        |      |
| Rainbow                        | Combines multiple DQN enhancements (Double, Dueling, PER, etc.)    |          |


#### Practical Tips

- Linearly anneal ε from ~1.0 to ~0.01 over early training to balance exploration/exploitation.  
- Clip rewards or normalize observations for numerical stability.  
- Use GPU acceleration and mixed precision to speed up training on image-based environments.  
- Monitor the magnitude of TD errors and loss curves to detect divergence.


For further exploration, consider how DQN variants handle continuous action spaces (e.g., DDPG), or how you might integrate a trained DQN model into a Node.js application via TensorFlow.js or ONNX Runtime for browser-based demos.

- [time=Tue, Aug 12, 2025 3:39 PM]

### 單一決策樹 比較 隨機森林

```python=
from sklearn.tree import DecisionTreeClassifier
from sklearn.ensemble import RandomForestClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

# 假設 X, y 已準備好
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

# 單一決策樹
dt = DecisionTreeClassifier(max_depth=5, min_samples_leaf=10)
dt.fit(X_train, y_train)
y_pred_dt = dt.predict(X_test)
print("Decision Tree Accuracy:", accuracy_score(y_test, y_pred_dt))

# 隨機森林
rf = RandomForestClassifier(n_estimators=100, max_features='sqrt', oob_score=True)
rf.fit(X_train, y_train)
y_pred_rf = rf.predict(X_test)
print("Random Forest Accuracy:", accuracy_score(y_test, y_pred_rf))
print("OOB Error:", 1 - rf.oob_score_)
```

- [time=Tue, Aug 12, 2025 8:34 PM]


#### Acknowledge

> [商用大數據分析, 2/e - 天瓏網路書店](https://www.tenlong.com.tw/products/9786263249967)