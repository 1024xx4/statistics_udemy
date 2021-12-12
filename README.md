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