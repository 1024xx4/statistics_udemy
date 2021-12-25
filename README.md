# statistics_udemy

米国データサイエンティストが教える統計学超入門講座【Python で実践】の演習

# 分布（distribution)

どの値にどれくらい Data が存在するかを表したもの

## Histogram

- １つの連続変数の分布を表すのに使用する。
- 各棒の区間に感覚がない
- 横軸は Data の**区間**で切られている
- bin を使ってその区間の度数（frequency）を表す。

### Histgram で連続変数の分布を描画する

```python
sns.displot(a, kde=Flase)
# a: Data array
```

## 棒 Group（bar chart）

- 棒を使った Graph の総称
- Category 変数の分布を表すのに使用する。
- 各棒の区間には間隔がある。
- 横軸は Category 変数のとりうる値
- 棒を使ってその値の度数（frequency）を表す

### 棒 Graph で Category 変数の分布を描画する

```python
sns.catplot(x, data, kind='count')
# x: x 軸にする Category 変数の名前
# data: Category 変数を含む DataFrame
```

# 記述統計と推測統計

## 記述統計

Data の特徴を記述する（例: 平均値, 中央値）

- 記述統計は、標本（sample）に興味がある。  
  <small>
  例). アンケート調査を実施した結果、「人生幸せだ」と回答をした人は70%だった。
  </small>

## 推測統計

標本（sample）から母集団（population）の特徴を推測する

- 推測統計は、母集団（population）に興味がある。  
  <small>
  例). アンケートの結果をもとに、成人男性の平均年収はいくらか考える
  </small>

## 代表値

Data を一つの値で表したい

### 平均（mean）

[平均値（mean）| Udemy](https://boostnote.io/shared/e8b90994-1365-4402-b5fe-d2ae81a1a25b)  
<small>※ 数式が発生するので Boostnote に整理する</small>

## 中央値（median）

- Data の大きさ順に並べた際の真ん中の値
- 平均値より外れ値の影響を受けにくい  
  <small>※ 金融では代表値として中央値をとることが多い。</small>
- 真ん中の値がない場合は、真ん中の２つの中間を取る
- 平均値の計算より時間がかかることに注意  
  <small>※ 全ての値を Sort する必要があるため</small>

## 最頻値（mode）
- Data の中で最も多く観測される値（最も頻繁）
- 極端に特定の値に集中している場合、最頻値を代表値として使う
- 分布の山を modal と呼ぶ  
  - １つの山を持つ分布: unimodal
  - ２つの山を持つ分布: bimodal
  - ３つ以上の山を持つ分布: multimodal

## 散布度
Data のばらつき
### 範囲（range）
- 最大値 - 最小値
- 外れの値に弱い
- 全体のばらつき度を示すには不十分

「範囲」だけでは両者の違いを表すことができない  
  => 最小、最大以外の値も使う

### 四分位数（quartile）
- Data を並べて４分割した時の 25%, 50%, 75% の値
- 「範囲」よりは外れ値に強い
- 全体のばらつき度を示すにはまだ不十分

#### 四分位範囲（IQR: Inter quartile range）と 四分位偏差（QD: quartile deviation）
[四分位範囲と四分位偏差 | Udemy](https://boostnote.io/shared/28b7b3a6-8e3e-46e1-8df0-91c75170c22b)

#### 箱ひげ図
四分位数範囲を図で表すのに便利な図。

### 平均偏差（MD: mean deviation）
- 平均（もしくは中央値）からの偏差の絶対値の平均
- 全ての Data を使うので、範囲や四分位数より散布度としては適している
- 絶対値が扱いにくい
#### 数式
https://boostnote.io/shared/7bd21032-186a-4aff-bbd2-28a5c18dac8c

### [分散（variance）](https://boostnote.io/shared/b499ea1e-9798-4fe6-8051-0cf6a0c55b7c)

### [標準偏差（標準偏差（standard deviation））](https://boostnote.io/shared/8fe0055c-b794-4751-838e-8d1f9ad27f1a)

## 記述統計のまとめ
- 記述統計は標本に興味がある
- 分布を描画することで値の偏りや散らばり具合を視覚的に理解する
- 代表値と散布度を使って Data を記述することができる

「統計学」というと母集団に興味がある**推測統計**のことを指すが、まず記述統計で Data の見方を理解する必要があった。

### 代表値の整理
| 種類  | 説明                   |
|-----|----------------------|
| 平均値 | Data の平均的な値          |
| 中央値 | Data を順番に並べた場合の真ん中の値 |
| 最頻値 | Data の中で最も観察される値     |

### 散布度
Data の散らばり具合を確認する

| 種類   | 説明                         | Story                  |
|------|----------------------------|------------------------|
| 範囲   | Data の範囲、最小値~最大値           | はずれ値の影響を大きく受けてしまう。     |
| 四分位数 | Data を Sort して４分割した時の値     | 全ての Data を指標の計算にいれれない。 |
| 平均偏差 | 平均値（また中央値）からの偏差の平均（絶対値を使う） | 絶対値を利用するのだが、絶対値は扱いずらい。 |
| 分散   | 偏差の２乗の平均                   | ２乗すると尺度がずれてしまう。        |
| 標準偏差 | 分散の平方根                     | 分散の幣後根をとることで尺度を合わせた。   |

統計学は、Story を理解しながら学ぶことが大事。１つ１つを理解することができる、飛ばして分散とかにいくと何故、そうなっているのか理解できない。

# ２変数間の記述統計
## 共分散(covariance)
連続変数間の相関関係の強さ

## 相関係数
連続変数間の相関関係の強さを標準化したもの

## 連関係数
Category 変数間の相関

## 確率とは（probability）とは
ある試行を同じ条件で何度も繰り返した時にある事象が起こる相対頻度の極限値  
https://boostnote.io/shared/b59c773c-b33d-4b32-b96b-b15f633883b3


## 確率変数（random variable）
https://boostnote.io/shared/47b8d481-aa33-4d41-b9ea-94e95d6fac39

## 確率分布（probability 
https://boostnote.io/shared/47b8d481-aa33-4d41-b9ea-94e95d6fac39）

## 確率密度と確率
https://boostnote.io/shared/2b8fbd20-26f7-48f6-b550-e622ffeeef1c

## 累積分布関数（CDF: Cumulative Distribution Function）
https://boostnote.io/shared/0b44086b-ade0-4b4a-b336-c40db72e64b4