---
project: "Evidence Based Everything"
title: "NumPyにおける主要な構文や関数"
status: "published"
draft: false
publish_ready: true
review_status: "passed"
article_type: "textbook_reference_review"
created: 2026-05-01
updated: 2026-05-01
last_verified: "2026-05-01"
freshness_ttl: "12 months"
question: "Numpyにおける主要な構文や関数について記事にまとめて"
question_type: "how_to"
claim_types:
  - "definitional"
  - "procedural"
  - "technical"
  - "historical"
  - "comparative"
category_id: "07"
category_name: "技術・工学・コンピューティング・AI"
category_path: "10_Published/07_Technology_Engineering_Computing_AI"
subfield_name: "数値計算・科学技術計算"
subfield_path: "10_Published/07_Technology_Engineering_Computing_AI/数値計算・科学技術計算__numerical-scientific-computing"
moc: "10_Published/07_Technology_Engineering_Computing_AI/数値計算・科学技術計算__numerical-scientific-computing/_MOC.md"
domain_profile: "technology_engineering_computing"
evidence_standard: "official documentation, stable API reference, peer-reviewed ecosystem overview, current release notes"
confidence: "high"
confidence_reason: "主要な構文と関数分類はNumPy公式v2.4 Manual、公式News、NatureのNumPy論文に基づく。"
has_infographic: true
infographic_path: "50_Assets/Infographics/numpy-main-syntax-functions_infographic.png"
source_count: 12
claim_count: 11
references_style: "numbered_urls_accessed_date"
tags:
  - "EBE"
  - "NumPy"
  - "Python"
  - "数値計算"
  - "科学技術計算"
---

# NumPyにおける主要な構文や関数

![[50_Assets/Infographics/numpy-main-syntax-functions_infographic.png]]

*図1. NumPyの中心概念は `ndarray` であり、`shape`、`dtype`、indexing、broadcasting、ufunc、axis指定の集約を理解すると、主要な構文と関数を体系的に整理できる。図の概念はNumPy公式ドキュメント、公式News、NatureのNumPy論文に基づく [1][2][5][6][10][11][12]。*

## 概要

NumPyは、Pythonで数値計算や科学技術計算を行うときの基盤的な配列ライブラリである。中心にあるのは、同じ型・固定サイズの要素を持つ多次元配列 `ndarray` であり、配列の形を表す `shape`、要素型を表す `dtype`、軸の数を表す `ndim`、要素数を表す `size` が基本語彙になる [1][2]。

NumPyの主要構文は、単なる関数一覧ではなく、配列を「作る」「見る」「選ぶ」「形を変える」「まとめる」「要素ごとに計算する」「乱数や線形代数へ広げる」という流れで理解するとよい。NumPy公式ドキュメントは、配列作成、indexing、broadcasting、ufunc、array manipulation、statistics、linear algebra、random samplingを別領域として整理している [3][4][5][6][7][8][9][10]。

2026-05-01時点で、NumPy公式NewsはNumPy 2.4.4を2026-03-29のリリースとして掲載している。本記事はNumPy v2.4 Manualを基準に、主要構文と関数を実用的な参照表としてまとめる [12]。

## この記事の要点

- `np.array` でPythonのlistやtupleから配列を作り、`np.zeros`、`np.ones`、`np.arange`、`np.linspace` で典型的な初期配列を作る [1][3]。
- 配列の基本情報は `a.shape`、`a.dtype`、`a.ndim`、`a.size` で確認する [1][2]。
- 添字指定は `a[i]`、`a[i, j]`、`a[:, 0]`、boolean maskなどで行う。スライスはviewを返すことがあり、advanced indexingはcopyになり得る [2][4]。
- `axis` は「どの軸に沿って処理するか」を指定する重要概念で、`sum`、`mean`、`max`、`argmax` などで頻出する [1][8]。
- `ufunc` は `np.sin`、`np.exp`、`np.add` のような要素ごとの関数群で、broadcastingや型変換と組み合わせて使う [5][6]。
- 乱数は新しい `np.random.default_rng()` と `Generator` を使うのが現代的な書き方である [10]。

## 定義と全体像

NumPyの配列 `ndarray` は、通常、同じ型とサイズの要素を持つ多次元コンテナである。配列の次元ごとの長さは `shape`、要素型は `dtype` で定まる [2]。この設計により、Pythonのlistより制約は強くなるが、大量の同型データをCPU上で効率よく扱いやすくなる [1]。

NumPyを使う典型的な流れは次の通りである。

```python
import numpy as np

a = np.array([[1, 2, 3],
              [4, 5, 6]])

print(a.shape)  # (2, 3)
print(a.dtype)  # int64 など環境依存
print(a[0, 1])  # 2
print(a.sum(axis=0))  # [5 7 9]
```

この短い例だけでも、import慣習、配列作成、属性参照、添字指定、axis指定の集約が出てくる。NumPyの学習では、この5点を先に固定すると、その後の関数群を見通しやすい。

## 歴史的背景・古典的理解

NumPyは、Python科学技術計算の配列プログラミング基盤として発展してきた。2020年のNature論文は、NumPyをPythonにおける主要な配列プログラミングライブラリとして位置付け、indexing、演算子、array-awareな関数を通じて高水準APIと高速な低水準実装をつなぐものとして説明している [11]。

歴史的には、Python数値計算の初期にはNumericやNumarrayなどの配列ライブラリが存在し、その後NumPyが統合的な基盤として普及した。現在のNumPyは、単独の便利ライブラリというより、SciPy、pandas、scikit-learn、画像処理、機械学習、可視化など多数のPython科学計算パッケージが共有する配列APIの中核として使われる [11]。

また、NumPy 2.0は2006年以来の大きなメジャーリリースとして2024年に公開され、Python API、C API、ABI、型昇格などに互換性上の注意点を含んだ。公式Newsは、2.4.0ではfree-threaded Python対応、user dtypes、annotationsなどの改善が継続されたことを示している [12]。

## 現在の標準的理解

現在のNumPyの標準的理解は、「配列をPythonのfor文で1要素ずつ処理する」のではなく、「配列全体、軸、shape、broadcasting、ufuncを組み合わせて処理を記述する」ことである。Broadcastingは、形が異なる配列同士を一定の規則で互換化し、C側のループを使ってベクトル化された演算を可能にする。ただし、不必要に大きな中間配列やメモリ圧迫を招く場合もある [5]。

たとえば、100個の値すべてに10を足す処理は次のように書ける。

```python
x = np.arange(100)
y = x + 10
```

ここで `+` はPythonのlist結合ではなく、NumPy配列に対する要素ごとの演算として働く。`np.add(x, 10)` と同じ方向の考え方であり、NumPyの多くの数学関数はufuncとして実装されている [6]。

## 詳説

### 1. importと命名慣習

NumPyは通常、次のようにimportする [1]。

```python
import numpy as np
```

`np` は公式ドキュメントでも使われる広く共有された慣習である。記事、教材、ライブラリコードを読むときにも、`np.array`、`np.zeros`、`np.mean` のような形がほぼ標準語彙になっている。

### 2. 配列作成

配列作成には複数の入口がある。公式ドキュメントは、Python構造からの変換、NumPy固有の作成関数、既存配列の複製・結合・変更、ファイル、バッファ、乱数などを一般的な作成方法として挙げている [3]。

```python
np.array([1, 2, 3])
np.zeros((2, 3))
np.ones((2, 3), dtype=np.int64)
np.empty((2, 3))       # 初期値は未定なので、後で必ず上書きする
np.arange(0, 10, 2)
np.linspace(0, 1, 5)
```

実務上は、連番なら `arange`、指定区間を指定個数で分割するなら `linspace`、ゼロ初期化なら `zeros`、単位的な初期値なら `ones` を使い分ける。`empty` は高速だが、メモリ上の未初期化値を含むため、すぐ全要素を上書きする場合に限って使うのが安全である [1]。

### 3. 配列属性

配列の状態確認では、次の属性が基本になる [1][2]。

| 属性 | 意味 | 例 |
|---|---|---|
| `a.shape` | 各軸の長さ | `(3, 4)` |
| `a.ndim` | 軸の数 | `2` |
| `a.size` | 全要素数 | `12` |
| `a.dtype` | 要素型 | `float64`, `int64` |
| `a.T` | 転置view | 2次元なら行列の転置に近い |

`shape` と `dtype` は、NumPyのエラーを読むときにも重要である。たとえば「shapeが合わない」「dtype変換できない」というエラーは、配列計算の設計が崩れていることを示す代表的な手掛かりである。

### 4. indexing、slicing、mask

NumPy配列は `x[obj]` 形式で添字指定でき、基本添字、advanced indexing、field accessなどがある [4]。

```python
a = np.array([[10, 20, 30],
              [40, 50, 60]])

a[0, 1]      # 20
a[:, 0]      # array([10, 40])
a[1, :]      # array([40, 50, 60])
a[a > 30]    # array([40, 50, 60])
```

重要なのは、スライスがcopyではなくviewを返す場合があることだ。viewは元配列と同じデータを参照するため、view側の変更が元配列に反映されることがある [2][4]。

```python
x = np.array([1, 2, 3, 4])
y = x[1:3]
y[0] = 99
print(x)  # [ 1 99  3  4]
```

一方、integer array indexingやboolean indexingなどのadvanced indexingはcopyを返す場合がある。NumPyで予期しない代入結果やメモリ使用量に悩むときは、viewかcopyかを確認する必要がある [4]。

### 5. shape操作

配列の形を変える関数群は、NumPyの読み書きで頻出する [7]。

```python
x = np.arange(6)
x.reshape(2, 3)
x.reshape(3, 2)
x.ravel()
x[:, np.newaxis]
np.expand_dims(x, axis=0)
np.squeeze(np.zeros((1, 3, 1)))
```

主な関数は次の通りである。

| 関数・属性 | 用途 |
|---|---|
| `reshape` | 要素数を保ったままshapeを変える |
| `ravel` | 1次元化する |
| `flatten` | 1次元のcopyを作る |
| `transpose`, `T` | 軸を入れ替える |
| `swapaxes`, `moveaxis` | 特定の軸を入れ替える・移動する |
| `expand_dims`, `np.newaxis` | 長さ1の軸を追加する |
| `squeeze` | 長さ1の軸を削除する |

`reshape` はデータ数を変えない。したがって、6個の要素を `(2, 3)` や `(3, 2)` にはできるが、通常 `(4, 2)` にはできない [1][7]。

### 6. 結合、分割、並べ替え

複数配列をつなぐには `concatenate`、`stack`、`vstack`、`hstack` などを使う。既存配列の並べ替えでは `sort`、条件抽出では `where`、位置取得では `argmax`、`argmin`、`nonzero` がよく使われる [1][7]。

```python
a = np.array([1, 2])
b = np.array([3, 4])

np.concatenate([a, b])  # [1 2 3 4]
np.stack([a, b])        # [[1 2], [3 4]]
np.where(a > 1, a, 0)   # [0 2]
```

結合ではshapeを強く意識する。`concatenate` は既存軸に沿ってつなぎ、`stack` は新しい軸を作って積む、と考えると整理しやすい。

### 7. ufuncと要素ごとの演算

ufuncは、ndarrayに要素ごとの演算を行う関数であり、broadcasting、型変換、`out`などの機能を持つ [6]。

```python
x = np.array([0, 1, 2, 3])

np.add(x, 10)
np.sqrt(x)
np.exp(x)
np.sin(x)
np.maximum(x, 2)
```

`+`、`-`、`*`、`/`、`**` などの演算子も、NumPy配列に対しては要素ごとの演算として働く。行列積には `@` または `np.matmul` を使う。配列の `*` は行列積ではなく要素ごとの積である点に注意する [1][9]。

### 8. broadcasting

Broadcastingは、shapeが異なる配列を演算可能にする仕組みである。小さい配列を大きい配列に論理的に広げ、不要なcopyを避けながらベクトル化演算を記述できる [5]。

```python
a = np.array([[1, 2, 3],
              [4, 5, 6]])
b = np.array([10, 20, 30])

a + b
# [[11, 22, 33],
#  [14, 25, 36]]
```

この例では、`b` が各行に対応するように扱われる。ただし、broadcastingは万能ではない。巨大な中間結果を暗黙に作る計算設計では、メモリ効率が悪化する可能性がある [5]。

### 9. axis指定と集約

`axis` は、NumPyで最も重要な引数の一つである。`axis=None` なら全体、`axis=0` なら0番目の軸に沿った処理、`axis=1` なら1番目の軸に沿った処理を意味する。

```python
a = np.array([[1, 2, 3],
              [4, 5, 6]])

a.sum()        # 21
a.sum(axis=0) # [5 7 9]
a.sum(axis=1) # [ 6 15]
a.mean(axis=0)
a.max(axis=1)
```

統計関数では、`mean`、`median`、`average`、`std`、`var`、`percentile`、`quantile`、`histogram` などが主要である。NaNを無視する `nanmean`、`nanmedian`、`nanstd` なども用意されている [8]。

### 10. 乱数

現代のNumPyでは、乱数生成に `np.random.default_rng()` から作る `Generator` を使うのが推奨される。公式ドキュメントは、古い `RandomState` は残るが、より速く柔軟で今後の改善対象になる `Generator` への移行を推奨している [10]。

```python
rng = np.random.default_rng(seed=42)

rng.integers(0, 10, size=5)
rng.normal(loc=0.0, scale=1.0, size=(2, 3))
rng.choice(["A", "B", "C"], size=4)
```

再現性が必要な分析やシミュレーションでは、seedを明示する。ただし、seedの扱いは「同じ環境・同じアルゴリズムで再現する」ための実務上の設定であり、乱数の統計品質や並列生成の設計は別途考える必要がある [10]。

### 11. 線形代数

`numpy.linalg` は、BLAS/LAPACKに依存して標準的な線形代数アルゴリズムを提供する [9]。

```python
A = np.array([[3.0, 1.0],
              [1.0, 2.0]])
b = np.array([9.0, 8.0])

np.linalg.solve(A, b)
np.linalg.det(A)
np.linalg.eig(A)
np.linalg.svd(A)
A @ b
```

線形代数では、`numpy.matrix` ではなく通常の2次元 `ndarray` を使うのが現在の標準である。公式ドキュメントも、線形代数ページでいうmatrixは2次元 `numpy.array` を指し、`numpy.matrix` オブジェクトは推奨されないと説明している [9]。

### 12. 入出力

配列を保存・読み込みする基本関数として、NumPy専用形式の `save`、`load`、複数配列用の `savez`、テキスト用の `loadtxt`、`genfromtxt` などが使われる。CSVや表形式データではpandasの方が適する場面も多いが、純粋な数値配列の保存ではNumPy形式が扱いやすい。

```python
np.save("arr.npy", a)
loaded = np.load("arr.npy")
```

ファイル入出力はデータの型、欠損、列名、文字コード、圧縮形式に依存するため、単純な配列保存と表データ処理を区別するのが実務上重要である。

## 応用・実践上の含意

NumPyを実務で使うときは、次の順で考えると失敗が少ない。

1. データを `ndarray` として表せるか確認する。
2. `shape` と `dtype` を確認する。
3. Pythonのfor文ではなく、ufunc、broadcasting、axis集約で書けるか検討する。
4. viewとcopyの違いが結果に影響しないか確認する。
5. 中間配列が巨大にならないか確認する。
6. 線形代数・統計・乱数では、公式に推奨される関数と新しいAPIを使う。

たとえば標準化は次のように書ける。

```python
X = np.array([[1.0, 2.0, 3.0],
              [4.0, 5.0, 6.0],
              [7.0, 8.0, 9.0]])

mu = X.mean(axis=0)
sigma = X.std(axis=0)
Z = (X - mu) / sigma
```

ここでは `mean(axis=0)` と `std(axis=0)` で列ごとの統計量を出し、broadcastingによって各行から平均を引き、標準偏差で割っている。NumPyらしいコードは、このように「shapeが合うように設計する」ことが中心になる [5][8]。

## 限界・論争点・未解決事項

NumPyは万能の高速化装置ではない。Pythonのfor文をNumPy関数へ置き換えると速くなることは多いが、小さすぎる配列、過剰な一時配列、メモリ帯域が支配的な処理、GPUが必要な処理では、期待通りの性能にならない場合がある。Broadcastingも便利だが、計算の見た目より大きなメモリ負荷を生む場合がある [5]。

また、NumPy 2.xではAPIやABIの移行が重要である。通常の配列利用者には影響が小さい場合もあるが、C拡張、古い依存パッケージ、型昇格の挙動に依存したコードでは注意が必要である。公式Newsは、NumPy 2.0がPython API、C API、ABIに破壊的変更を含んだことを明示している [12]。

統計・最適化・信号処理・疎行列・高度な線形代数では、NumPyだけでなくSciPy、pandas、xarray、PyTorch、JAX、CuPyなどの専門ライブラリが適する場合もある。NumPyは基盤であり、すべての高水準分析機能を単独で担うものではない [9][11]。

## まとめ

NumPyの主要構文は、`ndarray`、`shape`、`dtype`、indexing、slicing、broadcasting、ufunc、axis指定を中心に整理できる。関数名を暗記するよりも、配列を作る、形を見る、選ぶ、形を変える、要素ごとに計算する、軸方向に集約する、乱数や線形代数に進む、という流れを身につける方が実践的である。

特に重要なのは、配列計算を「値の集まり」ではなく「shapeを持つデータ構造の変換」として読むことである。この見方を持つと、`reshape`、`axis`、broadcasting、ufuncの挙動が一つの体系として理解できる。

## 参考ソース

1. NumPy Developers. "NumPy: the absolute basics for beginners." NumPy v2.4 Manual. URL: https://numpy.org/doc/stable/user/absolute_beginners.html. Accessed: 2026-05-01.
2. NumPy Developers. "The N-dimensional array (ndarray)." NumPy v2.4 Manual. URL: https://numpy.org/doc/stable/reference/arrays.ndarray.html. Accessed: 2026-05-01.
3. NumPy Developers. "Array creation." NumPy v2.4 Manual. URL: https://numpy.org/doc/stable/user/basics.creation.html. Accessed: 2026-05-01.
4. NumPy Developers. "Indexing on ndarrays." NumPy v2.4 Manual. URL: https://numpy.org/doc/stable/user/basics.indexing.html. Accessed: 2026-05-01.
5. NumPy Developers. "Broadcasting." NumPy v2.4 Manual. URL: https://numpy.org/doc/stable/user/basics.broadcasting.html. Accessed: 2026-05-01.
6. NumPy Developers. "Universal functions (ufunc)." NumPy v2.4 Manual. URL: https://numpy.org/doc/stable/reference/ufuncs.html. Accessed: 2026-05-01.
7. NumPy Developers. "Array manipulation routines." NumPy v2.4 Manual. URL: https://numpy.org/doc/stable/reference/routines.array-manipulation.html. Accessed: 2026-05-01.
8. NumPy Developers. "Statistics." NumPy v2.4 Manual. URL: https://numpy.org/doc/stable/reference/routines.statistics.html. Accessed: 2026-05-01.
9. NumPy Developers. "Linear algebra." NumPy v2.4 Manual. URL: https://numpy.org/doc/stable/reference/routines.linalg.html. Accessed: 2026-05-01.
10. NumPy Developers. "Random sampling." NumPy v2.4 Manual. URL: https://numpy.org/doc/stable/reference/random/index.html. Accessed: 2026-05-01.
11. Harris, C. R. et al. "Array programming with NumPy." Nature 585, 357-362 (2020). URL: https://www.nature.com/articles/s41586-020-2649-2. DOI: 10.1038/s41586-020-2649-2. Accessed: 2026-05-01.
12. NumPy Developers. "NumPy - News." URL: https://numpy.org/news/. Accessed: 2026-05-01.

## 更新履歴

- 2026-05-01: NumPy v2.4 Manual、公式News、Nature論文を基に初版作成。

## 更新日付

2026-05-01