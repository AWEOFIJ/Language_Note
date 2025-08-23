---
title: Math 筆記

---

## Math 數學

- Start time: [time=Tue, Jun 24, 2025 12:55 PM]
- Last Update: [time=Sat, Aug 23, 2025 11:31 AM]


### Mean 平均數

#### Arithmetirc Mean 算術平均數

$$
\bar{x} = \frac{x_1 + x_2 + x_3 + ... + x_{n-1} + x_n}{n} = \frac{1}{n}\sum{i}
$$


#### Geometric Mean 幾何平均數

$$
G = \sqrt[n]{x_1 \times x_2 \times x_3 \times ... \times x_n} = (\prod_{i=1}^{n}xi)^{\frac{1}{n}}
$$

<!-- 加權幾何平均數 -->


#### Harmonic Mean 調和平均數

$$
H = \frac{n}{\frac{1}{x_1} + \frac{1}{x_2} + \frac{1}{x_3} + ... + \frac{1}{x_{n-1}} + \frac{1}{x_{n}}} = \frac{n}{\sum_{i=1}^{n} \frac{1}{x_i}}
$$


### 歐幾里德距離

$\sqrt[2]{a^2 + b^2}$

$\sqrt[2]{a^2 + b^2 + c^2}$



#### 不等式 

![螢幕擷取畫面 2025-08-10 085713](https://hackmd.io/_uploads/H1C1yOr_xx.png)


#### 標準差

- 標準差（Standard Deviation）：標準差是衡量一組資料分散程度的統計量。當標準差較大時，表示資料點離平均值的距離較遠，也就是說，資料的分散程度較高。反之，若標準差較小，則表示資料點都聚集在平均值附近，資料的分散程度較低。在品質管理中，標準差常用來評估產品或過程的穩定性。標準差越大，表示產品品質越不穩定，良率越低。

> 偏差

$$
x_i - \bar{x}
$$

> 平方每個偏差

$$
(x_i-\bar{x})^2
$$

> 變異數 

$$
s^2 = \frac{1}{n-1}\sum_{i=1}^{n}(x_i-\bar{x})^2
$$

> 標準差 

$$
s = \sqrt{s^2}
$$


### 假說檢定

#### 虛無假說

- 虛無假說的內容一般是希望能證明為錯誤的假說，與虛無假說相對的是對立假說，即希望通過證偽虛無假說而證明正確的另一種假說。從數學上來看，虛無假說和對立假說的地位是相等的，但是在統計學的實際運用中，常常需要強調一類假說為應當或期望值實現的假說，例如在相關性檢定中，一般會取「兩者之間無關聯」作為虛無假說，而在獨立性檢定中，一般會取「兩者之間非獨立」作為虛無假說。


#### 對立假說

- 假說檢定依樣本證據判斷對統計假說的真偽。其中虛無假說（Null hypothesis，記作 $H_0$），通常由研究者決定，反映研究者對未知母數的看法，而站在虛無假說立場對立面的即為對立假說，需要透過統計檢定來證明對立假說為真，當有充足證據拒絕虛無假說時，即可接受對立假說，而若無充足證據證明對立假說為真時，則「不拒絕」虛無假說。


#### 假說檢定

- 假說檢定（英語：hypothesis testing）是推論統計中用於檢定現有數據是否足以支持特定假設的方法。一旦能估計未知母數，就會希望根據結果對未知的真正母數值做出適當的推論。

- 欲檢定統計上假設的正確性的為虛無假說（Null hypothesis，記為$H_0$)，虛無假說通常由研究者決定，反映研究者對未知母數的看法。相對於虛無假說的其他有關母數之論述是對立假說（Alternative hypothesis，記為 $H_{a}$），它通常反應了執行檢定的研究者對母數可能數值的另一種（對立的）看法（換句話說，對立假說通常才是研究者最想證明的）。

- 假說檢定的種類包括：t檢定，F檢定，Z檢定，卡方檢定等等。


#### 型一錯誤與型二錯誤

<!-- <table style="table-layout: fixed; width: 100%; border-collapse: collapse;">
  <thead>
    <tr>
      <th rowspan="2" colspan="2" style="text-align: center;">根據研究結果的判斷</th>
      <th colspan="2" style="text-align: center;">真實情況</th>
    </tr>
    <tr>
      <th style="text-align: center;">\\( H_0 \\)<br>（虛無假說）為真</th>
      <th style="text-align: center;">\\( H_a \\)<br>（對立假說）為真</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center;">判斷結果</td>
      <td style="text-align: center;">拒絕 \\( H_0 \\)</td>
      <td style="text-align: left;">錯誤判斷（偽陽性、型一錯誤）<br>發生機率：\\( \\alpha \\)（顯著水準）</td>
      <td style="text-align: left;">正確判斷<br>發生機率：\\( 1 - \\beta \\)（檢定力）</td>
    </tr>
    <tr>
      <td style="text-align: center;">判斷結果</td>
      <td style="text-align: center;">不拒絕 \\( H_0 \\)</td>
      <td style="text-align: left;">正確判斷<br>機率：\\( 1 - \\alpha \\)</td>
      <td style="text-align: left;">錯誤判斷（偽陰性、型二錯誤）<br>發生機率：\\( \\beta \\)</td>
    </tr>
  </tbody>
</table> -->

| 根據研究結果的判斷 | 真實情況: $H_0$（虛無假說）為真 | 真實情況: $H_a$（對立假說）為真 |
|-|-|-|
| 判斷結果  拒絕 $H_0$ | 錯誤判斷（偽陽性、型一錯誤）  發生機率：$\alpha$（顯著水準） | 正確判斷  發生機率：$1 - \beta$（檢定力） |
| 判斷結果  不拒絕 $H_0$ | 正確判斷  機率：$1 - \alpha$ | 錯誤判斷（偽陰性、型二錯誤）  發生機率：$\beta$ |


#### 檢定力

- 統計檢定力（英語：statistical power），或稱檢定力（power of a test），是指假說檢定中，當對立假說(Alternative Hypothesis $H_a$，或記作$H_1$）為真時正確地拒絕虛無假說（$H_0$）的機率，即 $power = Pr(reject H_0 | H_a)$ is true，換言之，檢定力也可以看作是當對立假說為真時將其接受的機率。當檢定力增加時，型二錯誤出現的機率（即偽陰性率$\beta$）減少。此時，檢定力可以表示為$(1-\beta)$。

- 在給定的顯著水準下，檢定力分析可以用於計算給定效果量時所需的最小樣本數；相反地，檢定力分析也可以用來計算給定樣本數時所能檢定到的最小效果量。


#### 顯著水準

- 統計學的假說檢定中，顯著性差異（或統計學意義，英語：statistical significance）是對數據差異性的評價，當某次實驗的結果在虛無假說下不大可能發生時，就認為該結果具有顯著性差異。更準確而言，譬如某項研究設定了一個數值$\alpha$（顯著水準），表示虛無假說本來正確但卻被拒絕的出錯機率（並非虛無假說為真的機率、對立假說為假的機率、實驗再現失敗率），然後用p值表示虛無假說條件為真時得到某結果或更極端結果的機率。當 $p \leq \alpha$ 時，就可以認為結果具有統計學意義，或數據之間具有了顯著性差異。顯著水準應當在開始數據收集前就設定，通常習慣設定為5%或更低，因研究的具體學科領域而異。


### 貝氏統計

#### 推論
貝氏統計的思想可用於貝氏推論中。貝氏推論，顧名思義，是指使用貝氏統計的思想進行統計推論，即利用樣本推論母體情況的過程。貝氏推論與頻率學派推論的一個最大不同是頻率學派認為母體的頻率是一定的，只是我們無法準確知道，但在樣本量足夠大時頻率會逐漸收斂於真實的機率值。因此頻率學派推論不會為假設或者模型的母數賦予一個機率。例如頻率學派推論中不會有「下次投硬幣正面朝上機率為1/2這種說法」，而是會認為，經過不斷大量實驗，（如果這枚硬幣是完美均勻的），那麼正面朝上的頻率會逐漸趨近於1/2。因此頻率學派推論一般是給出統計量以及其信賴區間。貝氏推論則會先基於經驗、先前的研究等先驗知識給假設賦予一個事前機率（例如實驗者基於經驗認為的硬幣朝上的機率）或者事前機率分布，再使用實驗得到的證據來修正這個事前機率，得到更契合證據的事後機率或事後機率分布。事後機率或事後機率分布即貝氏推論的輸出

#### 公式

$$
P(A|B) = \frac{P(B|A) \space P(A)} {P(B)}
$$

$B$的機率分布一般是連續的，這往往造成$P(B)$的計算涉及到複雜的積分。不過，使用變分貝氏方或馬可夫鏈蒙地卡羅等方法可在不涉及計算$P(B)$的情況下求得所需的最大事後機率，在這種情況下可以只考慮事前機率與概似函數對事後機率的影響（$\alpha$ 符號代表「成正比）：

$$
P(A|B) \space \alpha \space P(B|A) \space P(A)
$$


### Pearson Correlation Coefficients

The **Pearson correlation coefficient**, often denoted as **r**, is a statistical measure that quantifies the **strength and direction of a linear relationship** between two continuous variables.

#### Key Characteristics of Pearson's r

- **Range of Values**:  
  - **+1** → Perfect positive linear relationship  
  - **-1** → Perfect negative linear relationship  
  - **0** → No linear relationship  
  - Values between -1 and +1 indicate varying degrees of correlation

- **Direction**:  
  - **Positive r** → As one variable increases, the other tends to increase  
  - **Negative r** → As one variable increases, the other tends to decrease

- **Interpretation Examples**:  
  - **r = 0.8** → Strong positive correlation (e.g., more study time → higher test scores)  
  - **r = -0.75** → Strong negative correlation (e.g., higher temperature → lower heating costs)

- **Important Caveat**:  
  - **Correlation ≠ Causation**  
    A high correlation doesn't imply that one variable causes the other to change.

#### Formula

The formula for Pearson's r is:

$$
r = \frac{\sum (x_i - \bar{x})(y_i - \bar{y})}{\sqrt{\sum (x_i - \bar{x})^2 \sum (y_i - \bar{y})^2}}
$$

Where:
- $x_i, y_i$ are individual data points
- $\bar{x}, \bar{y}$ are the means of the respective variables

#### When to Use It

- When both variables are **continuous** and approximately **normally distributed**
- When you're interested in **linear relationships**
- Common in fields like psychology, economics, and data science


### 羅吉斯回歸

- 勝算（Odds）：定義為事件成功的機率除以失敗的機率，即 $Odds = \frac{p}{1-p}$
- 羅吉斯迴歸式：對勝算取自然對數(logit)，形成線性關係
- 係數解釋：每個 $\beta_i$表示該自變數每增加一單位，勝算如何改變。其指數值 $\exp(\beta_i)$ 又稱為OR值(Odds Ratio)。

$$
\log(\frac{p}{1-p}) = \beta_0 + \beta_1x_1 + \beta_2x_2 + ... + \beta_{n-1}x_{n-1} + \beta_nx_n
$$

- [time=Tue, Aug 12, 2025 8:12 PM]


### 損失函數 Loss Function

#### 均方誤差（Mean Squared Error, MSE）

- 用於迴歸任務，計算預測值與真實值之間平方誤差的平均值。 

$$
MSE = \frac{1}{n} \sum_{i=1}^{n}(y_i-\hat{y_i}^2)
$$


####  交叉熵損失（Cross-Entropy Loss）

- 用於分類任務，衡量預測概率分佈與真實分佈之間的差異。


### 支援向量機 (Support Vector Machine, SVM)

支援向量機是一種監督式學習模型，透過尋找可最大化類別間隔的超平面來完成分類與迴歸任務。它同時結合了線性與非線性技巧，能在高維空間中處理複雜資料。


#### 核心概念

- 最大間隔（Maximum Margin）  
  目標是在不同類別間尋找能使間隔最大的分割超平面  
- 支援向量（Support Vectors）  
  最靠近邊界的那些訓練樣本，決定了最優超平面的位置  
- 核技巧（Kernel Trick）  
  不顯式映射到高維空間，透過核函數計算內積完成非線性分割  


#### 數學原理

1. 定義超平面  
   $w^T x + b = 0$  
2. 最大化間隔對應的優化問題  
   Primal form:  
   $$
     \min_{w,b} \;\; \frac{1}{2}\|w\|^2
     \quad\text{s.t.}\quad y_i(w^T x_i + b) \ge 1, \;\; i=1,\dots,n
   $$  
3. 轉為對偶問題（Dual form）  
   $$
     \max_{\alpha}\;\; \sum_{i=1}^n \alpha_i - \tfrac{1}{2}\sum_{i,j}\alpha_i\alpha_j y_i y_j x_i^T x_j
     \quad\text{s.t.}\quad \sum_{i}\alpha_i y_i = 0,\;\alpha_i\ge0
   $$  
4. 支援向量對應 $\alpha_i > 0$  
   解出 $\alpha$ 後可重建 $w = \sum_i \alpha_i y_i x_i$，再求出 $b$


#### 常見核函數

| 核函數類型   | 表達式                                                         | 適用場景                           |
|------------|--------------------------------------------------------------|-----------------------------------|
| 線性核      | $K(x_i, x_j) = x_i^T x_j$                                  | 原始空間已線性可分                 |
| 多項式核    | $K(x_i, x_j) = (x_i^T x_j + 1)^d$                           | 特徵互動較多時                       |
| RBF（高斯核） | $K(x_i, x_j) = \exp\bigl(-\frac{\|x_i - x_j\|^2}{2\sigma^2}\bigr)$ | 無需預先選擇特徵映射，普適性強         |
| Sigmoid核   | $K(x_i, x_j) = \tanh(\kappa\,x_i^T x_j + \theta)$          | 類似神經網路激活函數                 |


#### 優點與缺點

| 優點                                   | 缺點                                 |
|--------------------------------------|--------------------------------------|
| 對高維特徵空間仍能保持良好表現             | 對大規模資料集訓練速度較慢             |
| 僅依賴部分支援向量，預測時效率相對穩定       | 需要仔細調校核函數與超參數             |
| 理論基礎堅實，可導出收斂與泛化界          | 模型可解釋性不如線性回歸等方法         |


#### 典型應用

- 文本分類（垃圾郵件偵測、情感分析）  
- 圖像識別（手寫字元、物體檢測）  
- 生物信息（基因表達資料分類）  
- 異常偵測（One-Class SVM 用於無標籤異常樣本識別） 


## Calculate
#### 泰勒展開式 Taylor Expansion

:::info
在數學上，對於一個在實數或複數$a$鄰域上，以實數作為變量或以複數作為變量的函數，並且是無窮可微的函數$f(x)$，它的泰勒級數是以下這種形式的冪級數
:::

![$y=e^{x}$](https://upload.wikimedia.org/wikipedia/commons/thumb/6/64/Taylorspolynomialexbig.svg/600px-Taylorspolynomialexbig.svg.png)

:::spoiler
$y=e^{x}$
:::

- 公式

$$
f(x) = f(a) + \frac{f'(a)}{1!}(x-a) + \frac{f^{(2)}(a)}{2!}(x-1)^2 + ... + \frac{f^{(n)}(a)}{n!}(x-a)^n + R_n{(x)}.
$$

$$
f(x) \approx \sum_{n=0}^{\infty}{\cfrac {f^{(n)}(a)}{n!}}(x-a)^{n}
$$

:::spoiler
其中的多項式稱為函數在a處的**泰勒展開式**，剩餘 $R_n{(x)}$ 是泰勒公式的餘項，是 $(x-a)^n$ 的高階無窮小
:::


- [time=Thu, Jun 26, 2025 9:25 AM]


#### 黎曼積分

![黎曼積分](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f2/Integral_as_region_under_curve.svg/500px-Integral_as_region_under_curve.svg.png =255x255)

![黎曼積分 維基百科](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ee/Riemann.gif/500px-Riemann.gif)

- [time=Sun, Jun 29, 2025 9:49 AM]


#### 傅立葉轉換

$$
F(f)(\mathbf{k}) = {\hat {f(\mathbf{k})}} = \int_{\mathbb{R}^d} f(\mathbf{x})\, e^{-2\pi i\, \mathbf{k} \cdot \mathbf{x}}\, d\mathbf{x}
$$

- [time=Tue, Jun 24, 2025 12:31 PM]


<!-- 零知識證明 -->
<!-- NP完全問題 -->


### 數學在生活方面的特殊意義

數學是門語言，透過再在這樣子的特殊意義的認定，從看清楚路燈與電線桿開始，大家都會做得不用計算，於普通計算，然後再一路結算。

- [time=Sat, Aug 23, 2025 11:31 AM]

## Acknowledge

- [《Crafting Interpreters》 Robert Nystrom](https://play.google.com/store/books/details?id=q0c6EAAAQBAJ)
- [Geogebra](https://www.geogebra.org/m/caxfuz9e)
- [各種平均數 - IT邦幫忙](https://ithelp.ithome.com.tw/articles/10229668)
- [虛無假說 - 維基百科](https://zh.wikipedia.org/zh-tw/%E9%9B%B6%E5%81%87%E8%AE%BE)
- [對立假說 - 維基百科](https://zh.wikipedia.org/wiki/%E5%B0%8D%E7%AB%8B%E5%81%87%E8%AA%AA)
- [假說檢定 - 維基百科](https://zh.wikipedia.org/wiki/%E5%81%87%E8%AA%AA%E6%AA%A2%E5%AE%9A)
- [標準偏差 - 維基百科](https://zh.wikipedia.org/zh-tw/%E6%A8%99%E6%BA%96%E5%81%8F%E5%B7%AE)
- [顯著性差異 - 維基百科](https://zh.wikipedia.org/wiki/%E6%98%BE%E8%91%97%E6%80%A7%E5%B7%AE%E5%BC%82)
- [檢定力 - 維基百科](https://zh.wikipedia.org/wiki/%E6%AA%A2%E5%AE%9A%E5%8A%9B)
- [貝氏統計 - 維基百科](https://zh.wikipedia.org/zh-tw/%E8%B4%9D%E5%8F%B6%E6%96%AF%E7%BB%9F%E8%AE%A1)
- [均方誤差 - 維基百科](https://zh.wikipedia.org/zh-tw/%E5%9D%87%E6%96%B9%E8%AF%AF%E5%B7%AE)
- [黎曼積分 維基百科](https://zh.wikipedia.org/wiki/%E9%BB%8E%E6%9B%BC%E7%A7%AF%E5%88%86)
- [泰勒展開式 維基百科](https://zh.wikipedia.org/zh-tw/%E6%B3%B0%E5%8B%92%E7%BA%A7%E6%95%B0) 
- [泰勒公式 維基百科](https://zh.m.wikipedia.org/wiki/%E6%B3%B0%E5%8B%92%E5%85%AC%E5%BC%8F)
- [傅立葉轉換 維基百科](https://zh.wikipedia.org/zh-tw/%E5%82%85%E9%87%8C%E5%8F%B6%E5%8F%98%E6%8D%A2)
- [零知識證明 - 維基百科](https://zh.wikipedia.org/zh-tw/%E9%9B%B6%E7%9F%A5%E8%AF%86%E8%AF%81%E6%98%8E)
- [NP完全_問題 - 維基百科](https://zh.wikipedia.org/zh-tw/NP%E5%AE%8C%E5%85%A8)## Math 數學

- Start time: [time=Tue, Jun 24, 2025 12:55 PM]
- Last Update: [time=Sat, Aug 23, 2025 11:31 AM]


### Mean 平均數

#### Arithmetirc Mean 算術平均數

$$
\bar{x} = \frac{x_1 + x_2 + x_3 + ... + x_{n-1} + x_n}{n} = \frac{1}{n}\sum{i}
$$


#### Geometric Mean 幾何平均數

$$
G = \sqrt[n]{x_1 \times x_2 \times x_3 \times ... \times x_n} = (\prod_{i=1}^{n}xi)^{\frac{1}{n}}
$$

<!-- 加權幾何平均數 -->


#### Harmonic Mean 調和平均數

$$
H = \frac{n}{\frac{1}{x_1} + \frac{1}{x_2} + \frac{1}{x_3} + ... + \frac{1}{x_{n-1}} + \frac{1}{x_{n}}} = \frac{n}{\sum_{i=1}^{n} \frac{1}{x_i}}
$$


### 歐幾里德距離

$\sqrt[2]{a^2 + b^2}$

$\sqrt[2]{a^2 + b^2 + c^2}$



#### 不等式 

![螢幕擷取畫面 2025-08-10 085713](https://hackmd.io/_uploads/H1C1yOr_xx.png)


#### 標準差

- 標準差（Standard Deviation）：標準差是衡量一組資料分散程度的統計量。當標準差較大時，表示資料點離平均值的距離較遠，也就是說，資料的分散程度較高。反之，若標準差較小，則表示資料點都聚集在平均值附近，資料的分散程度較低。在品質管理中，標準差常用來評估產品或過程的穩定性。標準差越大，表示產品品質越不穩定，良率越低。

> 偏差

$$
x_i - \bar{x}
$$

> 平方每個偏差

$$
(x_i-\bar{x})^2
$$

> 變異數 

$$
s^2 = \frac{1}{n-1}\sum_{i=1}^{n}(x_i-\bar{x})^2
$$

> 標準差 

$$
s = \sqrt{s^2}
$$


### 假說檢定

#### 虛無假說

- 虛無假說的內容一般是希望能證明為錯誤的假說，與虛無假說相對的是對立假說，即希望通過證偽虛無假說而證明正確的另一種假說。從數學上來看，虛無假說和對立假說的地位是相等的，但是在統計學的實際運用中，常常需要強調一類假說為應當或期望值實現的假說，例如在相關性檢定中，一般會取「兩者之間無關聯」作為虛無假說，而在獨立性檢定中，一般會取「兩者之間非獨立」作為虛無假說。


#### 對立假說

- 假說檢定依樣本證據判斷對統計假說的真偽。其中虛無假說（Null hypothesis，記作 $H_0$），通常由研究者決定，反映研究者對未知母數的看法，而站在虛無假說立場對立面的即為對立假說，需要透過統計檢定來證明對立假說為真，當有充足證據拒絕虛無假說時，即可接受對立假說，而若無充足證據證明對立假說為真時，則「不拒絕」虛無假說。


#### 假說檢定

- 假說檢定（英語：hypothesis testing）是推論統計中用於檢定現有數據是否足以支持特定假設的方法。一旦能估計未知母數，就會希望根據結果對未知的真正母數值做出適當的推論。

- 欲檢定統計上假設的正確性的為虛無假說（Null hypothesis，記為$H_0$)，虛無假說通常由研究者決定，反映研究者對未知母數的看法。相對於虛無假說的其他有關母數之論述是對立假說（Alternative hypothesis，記為 $H_{a}$），它通常反應了執行檢定的研究者對母數可能數值的另一種（對立的）看法（換句話說，對立假說通常才是研究者最想證明的）。

- 假說檢定的種類包括：t檢定，F檢定，Z檢定，卡方檢定等等。


#### 型一錯誤與型二錯誤

<!-- <table style="table-layout: fixed; width: 100%; border-collapse: collapse;">
  <thead>
    <tr>
      <th rowspan="2" colspan="2" style="text-align: center;">根據研究結果的判斷</th>
      <th colspan="2" style="text-align: center;">真實情況</th>
    </tr>
    <tr>
      <th style="text-align: center;">\\( H_0 \\)<br>（虛無假說）為真</th>
      <th style="text-align: center;">\\( H_a \\)<br>（對立假說）為真</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: center;">判斷結果</td>
      <td style="text-align: center;">拒絕 \\( H_0 \\)</td>
      <td style="text-align: left;">錯誤判斷（偽陽性、型一錯誤）<br>發生機率：\\( \\alpha \\)（顯著水準）</td>
      <td style="text-align: left;">正確判斷<br>發生機率：\\( 1 - \\beta \\)（檢定力）</td>
    </tr>
    <tr>
      <td style="text-align: center;">判斷結果</td>
      <td style="text-align: center;">不拒絕 \\( H_0 \\)</td>
      <td style="text-align: left;">正確判斷<br>機率：\\( 1 - \\alpha \\)</td>
      <td style="text-align: left;">錯誤判斷（偽陰性、型二錯誤）<br>發生機率：\\( \\beta \\)</td>
    </tr>
  </tbody>
</table> -->

| 根據研究結果的判斷 | 真實情況: $H_0$（虛無假說）為真 | 真實情況: $H_a$（對立假說）為真 |
|-|-|-|
| 判斷結果  拒絕 $H_0$ | 錯誤判斷（偽陽性、型一錯誤）  發生機率：$\alpha$（顯著水準） | 正確判斷  發生機率：$1 - \beta$（檢定力） |
| 判斷結果  不拒絕 $H_0$ | 正確判斷  機率：$1 - \alpha$ | 錯誤判斷（偽陰性、型二錯誤）  發生機率：$\beta$ |


#### 檢定力

- 統計檢定力（英語：statistical power），或稱檢定力（power of a test），是指假說檢定中，當對立假說(Alternative Hypothesis $H_a$，或記作$H_1$）為真時正確地拒絕虛無假說（$H_0$）的機率，即 $power = Pr(reject H_0 | H_a)$ is true，換言之，檢定力也可以看作是當對立假說為真時將其接受的機率。當檢定力增加時，型二錯誤出現的機率（即偽陰性率$\beta$）減少。此時，檢定力可以表示為$(1-\beta)$。

- 在給定的顯著水準下，檢定力分析可以用於計算給定效果量時所需的最小樣本數；相反地，檢定力分析也可以用來計算給定樣本數時所能檢定到的最小效果量。


#### 顯著水準

- 統計學的假說檢定中，顯著性差異（或統計學意義，英語：statistical significance）是對數據差異性的評價，當某次實驗的結果在虛無假說下不大可能發生時，就認為該結果具有顯著性差異。更準確而言，譬如某項研究設定了一個數值$\alpha$（顯著水準），表示虛無假說本來正確但卻被拒絕的出錯機率（並非虛無假說為真的機率、對立假說為假的機率、實驗再現失敗率），然後用p值表示虛無假說條件為真時得到某結果或更極端結果的機率。當 $p \leq \alpha$ 時，就可以認為結果具有統計學意義，或數據之間具有了顯著性差異。顯著水準應當在開始數據收集前就設定，通常習慣設定為5%或更低，因研究的具體學科領域而異。


### 貝氏統計

#### 推論
貝氏統計的思想可用於貝氏推論中。貝氏推論，顧名思義，是指使用貝氏統計的思想進行統計推論，即利用樣本推論母體情況的過程。貝氏推論與頻率學派推論的一個最大不同是頻率學派認為母體的頻率是一定的，只是我們無法準確知道，但在樣本量足夠大時頻率會逐漸收斂於真實的機率值。因此頻率學派推論不會為假設或者模型的母數賦予一個機率。例如頻率學派推論中不會有「下次投硬幣正面朝上機率為1/2這種說法」，而是會認為，經過不斷大量實驗，（如果這枚硬幣是完美均勻的），那麼正面朝上的頻率會逐漸趨近於1/2。因此頻率學派推論一般是給出統計量以及其信賴區間。貝氏推論則會先基於經驗、先前的研究等先驗知識給假設賦予一個事前機率（例如實驗者基於經驗認為的硬幣朝上的機率）或者事前機率分布，再使用實驗得到的證據來修正這個事前機率，得到更契合證據的事後機率或事後機率分布。事後機率或事後機率分布即貝氏推論的輸出

#### 公式

$$
P(A|B) = \frac{P(B|A) \space P(A)} {P(B)}
$$

$B$的機率分布一般是連續的，這往往造成$P(B)$的計算涉及到複雜的積分。不過，使用變分貝氏方或馬可夫鏈蒙地卡羅等方法可在不涉及計算$P(B)$的情況下求得所需的最大事後機率，在這種情況下可以只考慮事前機率與概似函數對事後機率的影響（$\alpha$ 符號代表「成正比）：

$$
P(A|B) \space \alpha \space P(B|A) \space P(A)
$$


### Pearson Correlation Coefficients

The **Pearson correlation coefficient**, often denoted as **r**, is a statistical measure that quantifies the **strength and direction of a linear relationship** between two continuous variables.

#### Key Characteristics of Pearson's r

- **Range of Values**:  
  - **+1** → Perfect positive linear relationship  
  - **-1** → Perfect negative linear relationship  
  - **0** → No linear relationship  
  - Values between -1 and +1 indicate varying degrees of correlation

- **Direction**:  
  - **Positive r** → As one variable increases, the other tends to increase  
  - **Negative r** → As one variable increases, the other tends to decrease

- **Interpretation Examples**:  
  - **r = 0.8** → Strong positive correlation (e.g., more study time → higher test scores)  
  - **r = -0.75** → Strong negative correlation (e.g., higher temperature → lower heating costs)

- **Important Caveat**:  
  - **Correlation ≠ Causation**  
    A high correlation doesn't imply that one variable causes the other to change.

#### Formula

The formula for Pearson's r is:

$$
r = \frac{\sum (x_i - \bar{x})(y_i - \bar{y})}{\sqrt{\sum (x_i - \bar{x})^2 \sum (y_i - \bar{y})^2}}
$$

Where:
- $x_i, y_i$ are individual data points
- $\bar{x}, \bar{y}$ are the means of the respective variables

#### When to Use It

- When both variables are **continuous** and approximately **normally distributed**
- When you're interested in **linear relationships**
- Common in fields like psychology, economics, and data science


### 羅吉斯回歸

- 勝算（Odds）：定義為事件成功的機率除以失敗的機率，即 $Odds = \frac{p}{1-p}$
- 羅吉斯迴歸式：對勝算取自然對數(logit)，形成線性關係
- 係數解釋：每個 $\beta_i$表示該自變數每增加一單位，勝算如何改變。其指數值 $\exp(\beta_i)$ 又稱為OR值(Odds Ratio)。

$$
\log(\frac{p}{1-p}) = \beta_0 + \beta_1x_1 + \beta_2x_2 + ... + \beta_{n-1}x_{n-1} + \beta_nx_n
$$

- [time=Tue, Aug 12, 2025 8:12 PM]


### 損失函數 Loss Function

#### 均方誤差（Mean Squared Error, MSE）

- 用於迴歸任務，計算預測值與真實值之間平方誤差的平均值。 

$$
MSE = \frac{1}{n} \sum_{i=1}^{n}(y_i-\hat{y_i}^2)
$$


####  交叉熵損失（Cross-Entropy Loss）

- 用於分類任務，衡量預測概率分佈與真實分佈之間的差異。


### 支援向量機 (Support Vector Machine, SVM)

支援向量機是一種監督式學習模型，透過尋找可最大化類別間隔的超平面來完成分類與迴歸任務。它同時結合了線性與非線性技巧，能在高維空間中處理複雜資料。


#### 核心概念

- 最大間隔（Maximum Margin）  
  目標是在不同類別間尋找能使間隔最大的分割超平面  
- 支援向量（Support Vectors）  
  最靠近邊界的那些訓練樣本，決定了最優超平面的位置  
- 核技巧（Kernel Trick）  
  不顯式映射到高維空間，透過核函數計算內積完成非線性分割  


#### 數學原理

1. 定義超平面  
   $w^T x + b = 0$  
2. 最大化間隔對應的優化問題  
   Primal form:  
   $$
     \min_{w,b} \;\; \frac{1}{2}\|w\|^2
     \quad\text{s.t.}\quad y_i(w^T x_i + b) \ge 1, \;\; i=1,\dots,n
   $$  
3. 轉為對偶問題（Dual form）  
   $$
     \max_{\alpha}\;\; \sum_{i=1}^n \alpha_i - \tfrac{1}{2}\sum_{i,j}\alpha_i\alpha_j y_i y_j x_i^T x_j
     \quad\text{s.t.}\quad \sum_{i}\alpha_i y_i = 0,\;\alpha_i\ge0
   $$  
4. 支援向量對應 $\alpha_i > 0$  
   解出 $\alpha$ 後可重建 $w = \sum_i \alpha_i y_i x_i$，再求出 $b$


#### 常見核函數

| 核函數類型   | 表達式                                                         | 適用場景                           |
|------------|--------------------------------------------------------------|-----------------------------------|
| 線性核      | $K(x_i, x_j) = x_i^T x_j$                                  | 原始空間已線性可分                 |
| 多項式核    | $K(x_i, x_j) = (x_i^T x_j + 1)^d$                           | 特徵互動較多時                       |
| RBF（高斯核） | $K(x_i, x_j) = \exp\bigl(-\frac{\|x_i - x_j\|^2}{2\sigma^2}\bigr)$ | 無需預先選擇特徵映射，普適性強         |
| Sigmoid核   | $K(x_i, x_j) = \tanh(\kappa\,x_i^T x_j + \theta)$          | 類似神經網路激活函數                 |


#### 優點與缺點

| 優點                                   | 缺點                                 |
|--------------------------------------|--------------------------------------|
| 對高維特徵空間仍能保持良好表現             | 對大規模資料集訓練速度較慢             |
| 僅依賴部分支援向量，預測時效率相對穩定       | 需要仔細調校核函數與超參數             |
| 理論基礎堅實，可導出收斂與泛化界          | 模型可解釋性不如線性回歸等方法         |


#### 典型應用

- 文本分類（垃圾郵件偵測、情感分析）  
- 圖像識別（手寫字元、物體檢測）  
- 生物信息（基因表達資料分類）  
- 異常偵測（One-Class SVM 用於無標籤異常樣本識別） 


## Calculate
#### 泰勒展開式 Taylor Expansion

:::info
在數學上，對於一個在實數或複數$a$鄰域上，以實數作為變量或以複數作為變量的函數，並且是無窮可微的函數$f(x)$，它的泰勒級數是以下這種形式的冪級數
:::

![$y=e^{x}$](https://upload.wikimedia.org/wikipedia/commons/thumb/6/64/Taylorspolynomialexbig.svg/600px-Taylorspolynomialexbig.svg.png)

:::spoiler
$y=e^{x}$
:::

- 公式

$$
f(x) = f(a) + \frac{f'(a)}{1!}(x-a) + \frac{f^{(2)}(a)}{2!}(x-1)^2 + ... + \frac{f^{(n)}(a)}{n!}(x-a)^n + R_n{(x)}.
$$

$$
f(x) \approx \sum_{n=0}^{\infty}{\cfrac {f^{(n)}(a)}{n!}}(x-a)^{n}
$$

:::spoiler
其中的多項式稱為函數在a處的**泰勒展開式**，剩餘 $R_n{(x)}$ 是泰勒公式的餘項，是 $(x-a)^n$ 的高階無窮小
:::


- [time=Thu, Jun 26, 2025 9:25 AM]


#### 黎曼積分

![黎曼積分](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f2/Integral_as_region_under_curve.svg/500px-Integral_as_region_under_curve.svg.png =255x255)

![黎曼積分 維基百科](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ee/Riemann.gif/500px-Riemann.gif)

- [time=Sun, Jun 29, 2025 9:49 AM]


#### 傅立葉轉換

$$
F(f)(\mathbf{k}) = {\hat {f(\mathbf{k})}} = \int_{\mathbb{R}^d} f(\mathbf{x})\, e^{-2\pi i\, \mathbf{k} \cdot \mathbf{x}}\, d\mathbf{x}
$$

- [time=Tue, Jun 24, 2025 12:31 PM]


<!-- 零知識證明 -->
<!-- NP完全問題 -->


### 數學在生活方面的特殊意義

數學是門語言，透過再在這樣子的特殊意義的認定，從看清楚路燈與電線桿開始，大家都會做得不用計算，於普通計算，然後再一路結算。

- [time=Sat, Aug 23, 2025 11:31 AM]

## Acknowledge

- [《Crafting Interpreters》 Robert Nystrom](https://play.google.com/store/books/details?id=q0c6EAAAQBAJ)
- [Geogebra](https://www.geogebra.org/m/caxfuz9e)
- [各種平均數 - IT邦幫忙](https://ithelp.ithome.com.tw/articles/10229668)
- [虛無假說 - 維基百科](https://zh.wikipedia.org/zh-tw/%E9%9B%B6%E5%81%87%E8%AE%BE)
- [對立假說 - 維基百科](https://zh.wikipedia.org/wiki/%E5%B0%8D%E7%AB%8B%E5%81%87%E8%AA%AA)
- [假說檢定 - 維基百科](https://zh.wikipedia.org/wiki/%E5%81%87%E8%AA%AA%E6%AA%A2%E5%AE%9A)
- [標準偏差 - 維基百科](https://zh.wikipedia.org/zh-tw/%E6%A8%99%E6%BA%96%E5%81%8F%E5%B7%AE)
- [顯著性差異 - 維基百科](https://zh.wikipedia.org/wiki/%E6%98%BE%E8%91%97%E6%80%A7%E5%B7%AE%E5%BC%82)
- [檢定力 - 維基百科](https://zh.wikipedia.org/wiki/%E6%AA%A2%E5%AE%9A%E5%8A%9B)
- [貝氏統計 - 維基百科](https://zh.wikipedia.org/zh-tw/%E8%B4%9D%E5%8F%B6%E6%96%AF%E7%BB%9F%E8%AE%A1)
- [均方誤差 - 維基百科](https://zh.wikipedia.org/zh-tw/%E5%9D%87%E6%96%B9%E8%AF%AF%E5%B7%AE)
- [黎曼積分 維基百科](https://zh.wikipedia.org/wiki/%E9%BB%8E%E6%9B%BC%E7%A7%AF%E5%88%86)
- [泰勒展開式 維基百科](https://zh.wikipedia.org/zh-tw/%E6%B3%B0%E5%8B%92%E7%BA%A7%E6%95%B0) 
- [泰勒公式 維基百科](https://zh.m.wikipedia.org/wiki/%E6%B3%B0%E5%8B%92%E5%85%AC%E5%BC%8F)
- [傅立葉轉換 維基百科](https://zh.wikipedia.org/zh-tw/%E5%82%85%E9%87%8C%E5%8F%B6%E5%8F%98%E6%8D%A2)
- [零知識證明 - 維基百科](https://zh.wikipedia.org/zh-tw/%E9%9B%B6%E7%9F%A5%E8%AF%86%E8%AF%81%E6%98%8E)
- [NP完全_問題 - 維基百科](https://zh.wikipedia.org/zh-tw/NP%E5%AE%8C%E5%85%A8)