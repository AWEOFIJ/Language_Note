# Math 數學

- Start time: [time=Tue, Jun 24, 2025 12:55 PM]
- Last Update: [time=Mon, Aug 11, 2025 1:48 PM]

### 歐幾里德距離

$\sqrt[2]{a^2 + b^2}$

$\sqrt[2]{a^2 + b^2 + c^2}$

### Mean 平均數
#### Arithmetirc Mean 算術平均數

$$
\bar{x} = \frac{x_1 + x_2 + x_3 + ... + x_{n-1} + x_n}{n} = \frac{1}{n}\sum{i}
$$

#### Geometric Mean 幾何平均數

$$
G = \sqrt[n]{x_1 \times x_2 \times x_3 \times ... \times x_n} = \exp\left( \frac{1}{n} \sum_{i=1}^{n} \ln x_i \right)
$$

#### Harmonic Mean 調和平均數

$$
H = \frac{n}{\frac{1}{x_1} + \frac{1}{x_2} + \frac{1}{x_3} + ... + \frac{1}{x_{n-1}} + \frac{1}{x_{n}}} = \frac{n}{\sum_{i=1}^{n} \frac{1}{x_i}}
$$

#### 不等式 

![螢幕擷取畫面 2025-08-10 085713](https://hackmd.io/_uploads/H1C1yOr_xx.png)

#### 標準差

- 標準差（Standard Deviation）：標準差是衡量一組資料分散程度的統計量。當標準差較大時，表示資料點離平均值的距離較遠，也就是說，資料的分散程度較高。反之，若標準差較小，則表示資料點都聚集在平均值附近，資料的分散程度較低。在品質管理中，標準差常用來評估產品或過程的穩定性。標準差越大，表示產品品質越不穩定，良率越低。

> 偏差

$$
x_i - x
$$

> 平方每個偏差

$$
(x_i-x)^2
$$

> 變異數 

$$
s^2 = \frac{1}{n-1}\sum_{i=1}^{n}(x_i-x)^2
$$

> 標準差 

$$s = \sqrt{s^2}$$

### 假說檢定
#### 虛無假說

- 虛無假說的內容一般是希望能證明為錯誤的假說，與虛無假說相對的是對立假說，即希望通過證偽虛無假說而證明正確的另一種假說。從數學上來看，虛無假說和對立假說的地位是相等的，但是在統計學的實際運用中，常常需要強調一類假說為應當或期望值實現的假說，例如在相關性檢定中，一般會取「兩者之間無關聯」作為虛無假說，而在獨立性檢定中，一般會取「兩者之間非獨立」作為虛無假說。

#### 對立假說

- 假說檢定依樣本證據判斷對統計假說的真偽。其中虛無假說（Null hypothesis，記作
H
0
{\displaystyle H_{0}}），通常由研究者決定，反映研究者對未知母數的看法，而站在虛無假說立場對立面的即為對立假說，需要透過統計檢定來證明對立假說為真，當有充足證據拒絕虛無假說時，即可接受對立假說，而若無充足證據證明對立假說為真時，則「不拒絕」虛無假說。

#### 假說檢定



#### 檢定力



#### 型一錯誤與型二錯誤

| 根據研究結果的判斷 | 真實情況：$H_0$ (虛無假說)為真 | 真實情況：$H_a$ (對立假說)為真 |
|-|-|-|
| 拒絕 $H_0$ | 錯誤判斷（偽陽性、型一錯誤），發生機率 $\alpha$ (顯著水準) | 正確判斷，發生機率 $1 - \beta$ (檢定立) |
| 不拒絕 $H_0$ | 正確判斷，機率 $1 - \alpha$ | 錯誤判斷（偽陰性、型二錯誤），發生機率 $\beta$ |

#### 羅吉斯回歸

- 勝算（Odds）：定義為事件成功的機率除以失敗的機率，即 $Odds = \frac{p}{1-p}$
- 羅吉斯迴歸式：對勝算取自然對數(logit)，形成線性關係：
- 係數解釋：每個 $\beta_i$表示該自變數每增加一單位，勝算如何改變。其指數值 $\exp(\beta_i)$ 又稱為OR值(Odds Ratio)。

$$\log(\frac{p}{1-p}) = \beta_0 + \beta_1x_1 + \beta_2x_2 + ... + \beta_{n-1}x_{n-1} + \beta_nx_n$$

## Calculate
#### 泰勒展開式 Taylor Expansion

:::info
在數學上，對於一個在實數或複數$a$鄰域上，以實數作為變量或以複數作為變量的函數，並且是無窮可微的函數$f(x)$，它的泰勒級數是以下這種形式的冪級數
:::

![$y=e^{x}$](https://upload.wikimedia.org/wikipedia/commons/thumb/6/64/Taylorspolynomialexbig.svg/600px-Taylorspolynomialexbig.svg.png)

<!-- ![多元函數的展開](https://wikimedia.org/api/rest_v1/media/math/render/svg/c429bf7c3300745b302d2906cb24577a309ec9f5) -->

:::spoiler
$y=e^{x}$
:::

$$
\sum_{n=0}^{\infty}{\cfrac {f^{(n)}(a)}{n!}}(x-a)^{n}
$$

- [泰勒展開式 維基百科](https://zh.wikipedia.org/zh-tw/%E6%B3%B0%E5%8B%92%E7%BA%A7%E6%95%B0) 
- [泰勒公式 維基百科](https://zh.m.wikipedia.org/wiki/%E6%B3%B0%E5%8B%92%E5%85%AC%E5%BC%8F)
- [time=Thu, Jun 26, 2025 9:25 AM]


#### 黎曼積分

![黎曼積分](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f2/Integral_as_region_under_curve.svg/500px-Integral_as_region_under_curve.svg.png =255x255)

![黎曼積分 維基百科](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ee/Riemann.gif/500px-Riemann.gif)

- [黎曼積分 維基百科](https://zh.wikipedia.org/wiki/%E9%BB%8E%E6%9B%BC%E7%A7%AF%E5%88%86)
- [time=Sun, Jun 29, 2025 9:49 AM]


#### 傅立葉轉換

$$
F(f)(\mathbf{k}) = {\hat {f(\mathbf{k})}} = \int_{\mathbb{R}^d} f(\mathbf{x})\, e^{-2\pi i\, \mathbf{k} \cdot \mathbf{x}}\, d\mathbf{x}
$$

- [傅立葉轉換 維基百科](https://zh.wikipedia.org/zh-tw/%E5%82%85%E9%87%8C%E5%8F%B6%E5%8F%98%E6%8D%A2)
- [time=Tue, Jun 24, 2025 12:31 PM]


#### 數學在生活方面的特殊意義

數學是門語言，透過再在這樣子的特殊意義的認定，從看清楚路燈與電線桿開始，小時候大家都會做得不用計算，普通計算，然後再一路結算，到是的，到嘴巴裡面。
有溫度，有感情，有心，理解足夠，到位的事情，萬丈高樓平地起，深淵允遠煖看齊。

- [time=Tue, Jul 8, 2025 9:40 AM]

#### Acknowledge

- [《Crafting Interpreters》 Robert Nystrom](https://play.google.com/store/books/details?id=q0c6EAAAQBAJ)
- [Geogebra](https://www.geogebra.org/m/caxfuz9e)
- [各種平均數 - IT邦幫忙](https://ithelp.ithome.com.tw/articles/10229668)
- [虛無假說 - 維基百科](https://zh.wikipedia.org/zh-tw/%E9%9B%B6%E5%81%87%E8%AE%BE)
- [對立假說 - 維基百科](https://zh.wikipedia.org/wiki/%E5%B0%8D%E7%AB%8B%E5%81%87%E8%AA%AA)
- [檢定力 - 維基百科](https://zh.wikipedia.org/wiki/%E6%AA%A2%E5%AE%9A%E5%8A%9B)