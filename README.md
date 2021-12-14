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