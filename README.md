# statistics_udemy

米国データサイエンティストが教える統計学超入門講座【Python で実践】の演習

---
## 分布の描画
### Histogram で連続変数の分布を描画する
```python
import seaborn as sns
sns.displot(a, kde=False)
```
- a: Data, array

### 棒Graph で Category変数の分布を描画する
```python
import seaborn as sns
sns.catplot(x, data, kind='count')
```
- x: x軸にする Category変数
- data: Category変数を含む DataFrame

---
## 平均値（mean）
### 平均を求める
```python
import numpy as np
np.mean()
```
```python
import pandas as pd
df = pd.DataFrame()
df['column'].mean()
df.groupby('column').mean()
```
### 平均値を描画する
```python
import seaborn as sns
sns.barplot(x, y, data)
```