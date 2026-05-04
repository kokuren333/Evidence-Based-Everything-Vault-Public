---
project: "Evidence Based Everything"
title: "計算論的精神医学を専門にするための学習分野と文献ロードマップ"
status: "published"
draft: false
publish_ready: true
review_status: "passed"
article_type: "textbook_learning_guide"
created: 2026-05-01
updated: 2026-05-01
last_verified: "2026-05-01"
freshness_ttl: "180 days"
question: "計算論的精神医学を専門にする上で学んでおきたい分野や文献の一覧"
question_type: "learning_roadmap"
claim_types:
  - "educational"
  - "methodological"
  - "bibliographic"
  - "clinical"
  - "technical"
category_id: "01"
category_name: "生命・健康・医学"
category_path: "10_Published/01_Life_Health_Medicine"
subfield_name: "精神医学"
subfield_path: "10_Published/01_Life_Health_Medicine/精神医学__psychiatry"
moc: "10_Published/01_Life_Health_Medicine/精神医学__psychiatry/_MOC.md"
domain_profile: "biomedical_health"
evidence_standard: "peer-reviewed reviews, textbooks, official research-framework documents, methodological standards"
confidence: "medium-high"
confidence_reason: "学習分野の選定は、計算論的精神医学の代表的レビュー、NIMH RDoC資料、計算論的神経科学・強化学習・ベイズ統計の標準教科書で広く支持される。一方、文献リストは専門化の目的や対象疾患によって更新されるため、完全な固定リストではない。"
has_infographic: true
infographic_path: "50_Assets/Infographics/computational-psychiatry-learning-roadmap_infographic.png"
source_count: 14
claim_count: 8
references_style: "numbered_url_accessed"
---

# 計算論的精神医学を専門にするための学習分野と文献ロードマップ

![[50_Assets/Infographics/computational-psychiatry-learning-roadmap_infographic.png]]

図1. 計算論的精神医学を専門にするには、臨床精神医学、認知神経科学、強化学習、ベイズ推論・予測処理、統計・機械学習、臨床研究・倫理を順に接続して学ぶ必要がある。入口文献としては、Montagueらの分野提案、HuysらとAdamsらのレビュー、Serièsの入門書が有用である。[1][2][3][4]

## 概要

計算論的精神医学を専門にするうえで必要なのは、「精神疾患を数式やAIで扱う技術」だけではない。中心にあるのは、精神症状、行動、脳・身体データ、生活背景を、学習、推論、予測、価値、不確実性、意思決定という計算過程の言葉でつなぐ力である。[1][2][3]

したがって、学習は六つの柱に分けると見通しがよい。第一に臨床精神医学と精神病理学、第二に認知神経科学、第三に強化学習と意思決定理論、第四にベイズ推論・予測処理・能動推論、第五に統計・機械学習・計算認知モデリング、第六に臨床研究法と倫理である。[1][2][5][6]

このロードマップは、研究を始める人、精神医学・心理学・神経科学・情報系から参入する人、将来的に論文を読み書きしたい人のために、分野と文献を体系的に並べたものである。すでに計算論的精神医学の定義を確認したい場合は、同じ小分野の「計算論的精神医学とは何か」と「理論駆動型の計算論的精神医学」を先に読むと全体像が掴みやすい。

## この記事の見取り図

- 計算論的精神医学を、臨床・神経科学・数理モデル・機械学習の交差領域として整理する。
- 学ぶべき分野を、基礎から専門応用まで六つの柱に分ける。
- 各分野ごとに、入口文献、標準文献、発展文献を示す。
- 最後に、読み進める順序、研究テーマの選び方、限界と注意点をまとめる。

## 定義と全体像

計算論的精神医学は、精神疾患や精神症状を、計算論的神経科学、認知科学、統計学、機械学習、臨床精神医学の方法で理解しようとする領域である。代表的レビューでは、精神症状を診断名だけで扱うのではなく、報酬学習、予測誤差、信念更新、不確実性推定、意思決定などの形式モデルで表現することが強調されている。[1][2][3]

学習上の重要点は、データ駆動型と理論駆動型の両方を理解することである。データ駆動型は、症状尺度、脳画像、電子カルテ、行動ログなどから診断、予後、治療反応を予測する。理論駆動型は、強化学習、ベイズ推論、予測符号化、能動推論などを使い、観察された行動や症状の背後にある潜在過程を推定する。[2][6]

専門家を目指す場合、どちらか片方だけでは不十分である。理論モデルだけでは臨床データの複雑さや予測性能を扱いにくく、機械学習だけでは症状を生む機構説明が弱くなりやすい。よい研究は、臨床的に意味のある問い、測定可能な行動・生理データ、反証可能なモデル、再現性のある統計解析を結びつける。[2][6][7]

## 歴史的背景・古典的理解

古典的な精神医学は、症状、経過、重症度、除外診断をもとに疾患カテゴリーを記述してきた。この方法は臨床実務、疫学、治療研究に不可欠だが、診断名だけでは同じ診断内の異質性や診断横断的な共通機構を十分に説明できない場合がある。[6][8]

計算論的精神医学の背景には、Marrの三水準分析がある。Marrは情報処理システムを、何を解いているかという計算論的水準、どの表現とアルゴリズムで解くかという水準、どの物理実装で実現するかという水準に分けて考えた。[9] 精神医学へ応用すると、症状を脳部位だけで説明するのではなく、患者がどのような推論・学習・意思決定問題をどのように解いているかを問う発想につながる。

2010年代には、Montague、Dolan、Friston、Dayanらのレビューが分野名としての計算論的精神医学を明確に提示し、Huys、Maia、Frankらが神経科学から臨床応用への橋渡しとして整理した。[1][2] NIMHのRDoCは、DSM/ICD診断カテゴリーだけではなく、陰性価、陽性価、認知、社会過程、覚醒・調節などの構成概念を複数の分析単位で研究する枠組みを提供した。[8]

## 現在の標準的理解

現在の標準的理解では、計算論的精神医学は診断名を直ちに置き換えるものではない。むしろ、診断カテゴリー、症状次元、認知課題、脳・身体データ、治療反応を、学習や推論の機構仮説で結びつける研究言語である。[1][2][6]

専門家に求められる力は三層に分けられる。第一は臨床現象を正確に読む力である。第二は、行動課題や神経データを数理モデルに落とし込む力である。第三は、モデルが臨床的に役立つか、再現性があるか、外部データで検証されるかを判断する力である。[6][7]

NIMH workshop reportは、計算論的精神医学には大きな機会がある一方で、課題設計、モデル選択、測定信頼性、再現性、臨床翻訳に課題があると整理している。[6] また精神医学の臨床予測モデルに関する系統的レビューでは、予測モデル研究が増えている一方、外的検証不足、過学習、バイアスリスク、臨床有用性評価不足がしばしば問題になると報告されている。[7]

## 詳細説明

### 1. 臨床精神医学・精神病理学

最初に学ぶべきなのは、精神疾患の症候学、診断体系、経過、治療、リスク評価である。計算モデルは、臨床現象を置き換えるものではなく、臨床現象をより精密に表すための道具である。うつ、不安、精神病症状、強迫、依存、自閉スペクトラム特性、摂食症、パーソナリティ、トラウマ関連症状などの基本を知らなければ、モデルの出力を臨床的に解釈できない。[2][6]

入口文献としては、計算論的精神医学のレビューと並行して、精神病理学・症候学の教科書を読むとよい。Jaspersの精神病理学は古典的背景として重要であり、現代的には症状面接、精神状態診察、DSM/ICDの使い方、臨床研究法を学ぶ必要がある。研究テーマを選ぶ段階では、「診断名」ではなく「どの症状・行動・認知過程をモデル化するのか」を明確にする。

### 2. 認知神経科学・システム神経科学

計算論的精神医学では、報酬系、ドーパミン、前頭前野、基底核、扁桃体、海馬、島皮質、注意、記憶、社会認知、情動制御などの基礎が重要である。強化学習モデルの報酬予測誤差はドーパミン系研究と深く関係し、予測処理・能動推論は知覚、身体感覚、行動制御の理解と結びつく。[1][3][5]

この段階では、神経画像や神経生理の手法も概観する。fMRI、EEG/MEG、瞳孔径、心拍変動、皮膚電気反応、スマートフォン由来のデジタル行動データは、モデルの潜在変数と臨床現象を接続する候補になる。ただし、脳画像や生理指標だけで精神疾患の機構が確定するわけではなく、行動課題、症状評価、縦断データとの組み合わせが必要である。[6][7]

### 3. 強化学習・意思決定理論

強化学習は、報酬や罰から学び、将来の行動を選ぶ過程を形式化する。中心概念は、価値、報酬予測誤差、学習率、割引率、探索と搾取、モデルフリー学習、モデルベース学習、習慣化である。[10]

精神医学では、依存、うつ、強迫、衝動性、無快感、社会的意思決定、リスク選好などの研究で重要になる。MaiaとFrankのレビューは、強化学習モデルを精神・神経疾患へ応用する入口として有用である。[5] SuttonとBartoの教科書は、強化学習そのものの標準的基礎を学ぶための中心文献である。[10]

### 4. ベイズ推論・予測処理・能動推論

ベイズ推論は、事前信念と観察データを統合して不確実な世界を推定する枠組みである。精神医学では、幻覚、妄想、不安、身体症状、自閉スペクトラム特性、うつにおける信念更新や精度重みづけを考えるときに重要になる。[3][11]

予測処理は、脳が感覚入力をただ受け取るのではなく、予測を作り、予測誤差を使って世界モデルを更新するという考え方である。能動推論は、知覚だけでなく行動も予測誤差を減らす過程として捉える。FristonらのレビューやAdamsらの総説は、この方向の入口として有用である。[3][11]

ただし、予測処理や能動推論は説明範囲が広いため、研究では具体的な課題、測定可能なパラメータ、反証可能な予測に落とす必要がある。広い理論を「何でも説明できる物語」として使わないことが重要である。[6]

### 5. 統計・機械学習・計算認知モデリング

計算論的精神医学では、回帰、階層モデル、ベイズ統計、MCMC、モデル比較、交差検証、外的検証、校正、欠測、測定誤差、再現性を扱う力が必須である。臨床データはサンプルサイズが限られ、症状評価はノイズを含み、施設差や選択バイアスも大きい。[7][12]

機械学習は、診断補助、予後予測、治療反応予測、サブタイプ化、normative modelingなどで使われる。ただし、精神医学の予測モデル研究では、内部検証だけで高性能に見えるモデルが、外部データでは性能低下する危険がある。予測研究を読むときは、外的検証、データ漏洩、校正、臨床有用性、バイアスリスクを必ず確認する。[7]

計算認知モデリングとしては、強化学習モデル、drift diffusion model、信号検出理論、階層ベイズモデル、状態空間モデル、潜在変数モデルを学ぶとよい。Gelmanらのベイズ統計、LeeとWagenmakersのベイズ認知モデリング、WilsonとCollinsの計算モデリング入門は、実装に近い学習に向く。[12][13]

### 6. 臨床研究法・倫理・実装科学

専門家として重要なのは、モデルを作ることだけではない。モデルが患者の利益につながるか、誤分類で害を生まないか、治療選択を改善するか、プライバシーや公平性を守るかを検証する必要がある。[6][7]

精神医学データは、症状、生活史、薬物使用、対人関係、デジタル行動、希死念慮など、非常に機微性が高い。研究では、同意、匿名化、二次利用、バイアス、説明責任、臨床導入時の安全性を扱う必要がある。臨床応用を目指すなら、前向き研究、外部施設での検証、実装研究、患者・臨床家への説明可能性まで学ぶべきである。[6][7]

## 文献ロードマップ

### 最初に読む入口文献

- Montague, Dolan, Friston, Dayan, "Computational psychiatry"。分野の代表的な初期レビューで、精神疾患を計算論的に扱う構想を示す。[1]
- Huys, Maia, Frank, "Computational psychiatry as a bridge from neuroscience to clinical applications"。神経科学と臨床応用をつなぐ総説として、データ駆動型と理論駆動型の見取り図を得やすい。[2]
- Adams, Huys, Roiser, "Computational Psychiatry: towards a mathematically informed understanding of mental illness"。数学的に精神疾患を理解する発想を、比較的読みやすく整理している。[3]
- Seriès, "Computational Psychiatry: A Primer"。入門書として、分野横断的な学習の足場になる。[4]

### 強化学習・意思決定を学ぶ文献

- Sutton and Barto, "Reinforcement Learning: An Introduction"。強化学習の標準教科書であり、報酬予測誤差、価値関数、方策、探索などの基礎を学べる。[10]
- Maia and Frank, "From reinforcement learning models to psychiatric and neurological disorders"。精神・神経疾患への強化学習応用の入口になる。[5]
- Daw系のmodel-free/model-based学習、habit、探索・搾取に関する文献を、対象疾患に合わせて読む。

### ベイズ・予測処理・能動推論を学ぶ文献

- Fristonらの計算論的精神医学レビュー。予測処理、能動推論、生成モデルの方向を掴む。[11]
- Adamsらの精神病症状に関する予測処理モデル。幻覚・妄想・精度重みづけの入口になる。[3]
- Clark, "Surfing Uncertainty" や Hohwy, "The Predictive Mind" は、哲学・認知科学側から予測処理を理解する補助線になる。

### 統計・モデリング・機械学習を学ぶ文献

- Gelman et al., "Bayesian Data Analysis"。階層モデル、事後推論、モデルチェックの基礎として重要である。[12]
- Lee and Wagenmakers, "Bayesian Cognitive Modeling"。認知モデルをベイズ的に扱う入口になる。[13]
- Wilson and Collins, "Ten simple rules for the computational modeling of behavioral data"。行動データを計算モデル化するときの実践的注意点を短く学べる。[14]
- Meehan, Lewis, Fazelの精神医学臨床予測モデル系統的レビュー。機械学習・予測モデルの限界を読むために重要である。[7]

### 臨床・診断横断研究を学ぶ文献

- NIMH RDoC公式資料。診断カテゴリーを超えた構成概念、分析単位、研究枠組みを理解するために読む。[8]
- RedishらのNIMH workshop report。計算論的精神医学の機会と課題、臨床翻訳上の論点を整理する。[6]
- DSM/ICD、精神病理学、対象疾患別ガイドライン、症候学の教科書を、研究テーマに合わせて読む。

## 応用・実践上の含意

学習は、最初から全分野を完全に網羅しようとしないほうがよい。実践的には、対象疾患または症状次元を一つ選び、それに対応する計算モデルを一つ選ぶのがよい。たとえば、うつ病なら報酬学習と無快感、統合失調症なら予測誤差と精度重みづけ、強迫症ならhabitとmodel-based control、依存症なら報酬学習と割引、不安症なら不確実性推定と脅威予測が入口になりやすい。[2][3][5]

研究を始める順序としては、まず臨床現象を定義し、次に行動課題を選び、モデルを事前に候補化し、シミュレーションで識別可能性を確認し、データを取り、モデル比較と外的検証を行う。この順序を守ると、単に後からもっともらしいモデルを当てはめる危険を減らせる。[6][14]

実装面では、PythonまたはRで、ベイズ統計、最尤推定、階層モデル、交差検証、可視化、再現可能な解析環境を扱えるようにする。臨床研究として発表する場合は、事前登録、解析コード公開、データ共有の範囲、倫理審査、患者への説明可能性も早い段階で考える必要がある。[6][7]

## 限界・論争点・未解決事項

第一に、この文献リストは固定的な正解ではない。計算論的精神医学は成長中の領域であり、対象疾患、使うデータ、理論的立場、臨床応用の目的によって読むべき文献は変わる。[6]

第二に、魅力的な理論ほど過剰解釈に注意が必要である。予測処理、能動推論、強化学習モデルは多くの症状を説明できるように見えるが、研究としては具体的な予測、モデル比較、再現性、外部検証が必要である。[6][14]

第三に、機械学習モデルの性能評価には注意が必要である。精神医学の臨床予測モデルでは、データ漏洩、過学習、外的検証不足、校正不足、臨床有用性評価不足が問題になりやすい。高いAUCや正解率だけでは、患者に有益なモデルとは言えない。[7]

第四に、計算論的精神医学は臨床の語りを消すものではない。患者の主観経験、生活背景、社会的文脈、治療関係、倫理的判断は、数理モデルだけでは扱いきれない。よい専門家は、モデルを臨床現象に従属させ、モデルで見えるものと見えないものを区別する。[2][6]

## まとめ

計算論的精神医学を専門にするには、臨床精神医学、認知神経科学、強化学習、ベイズ推論・予測処理、統計・機械学習、臨床研究・倫理を横断して学ぶ必要がある。入口文献としては、Montagueら、Huysら、Adamsら、Serièsを読み、そこから強化学習、予測処理、ベイズ統計、臨床予測モデル、RDoCへ広げるのがよい。[1][2][3][4][8]

最も実践的な学び方は、対象疾患または症状次元を一つ選び、対応する行動課題とモデルを実装し、臨床的な問いに戻して検証することである。計算論的精神医学は、精神医学をAIに置き換える道具ではなく、精神症状をより機構的、定量的、反証可能に理解するための研究言語である。[2][6][7]

## 参考ソース

[1] Montague, P. R., Dolan, R. J., Friston, K. J., & Dayan, P. "Computational psychiatry." Trends in Cognitive Sciences, 2012. DOI: 10.1016/j.tics.2012.08.010. Accessed 2026-05-01. URL: https://pubmed.ncbi.nlm.nih.gov/23079560/

[2] Huys, Q. J. M., Maia, T. V., & Frank, M. J. "Computational psychiatry as a bridge from neuroscience to clinical applications." Nature Neuroscience, 2016. DOI: 10.1038/nn.4238. Accessed 2026-05-01. URL: https://pubmed.ncbi.nlm.nih.gov/26906507/

[3] Adams, R. A., Huys, Q. J. M., & Roiser, J. P. "Computational Psychiatry: towards a mathematically informed understanding of mental illness." Journal of Neurology, Neurosurgery & Psychiatry, 2016. DOI: 10.1136/jnnp-2015-310737. Accessed 2026-05-01. URL: https://pmc.ncbi.nlm.nih.gov/articles/PMC4717449/

[4] Seriès, P. "Computational Psychiatry: A Primer." MIT Press, 2020. Accessed 2026-05-01. URL: https://mitpress.mit.edu/9780262044592/computational-psychiatry/

[5] Maia, T. V., & Frank, M. J. "From reinforcement learning models to psychiatric and neurological disorders." Nature Neuroscience, 2011. DOI: 10.1038/nn.2723. Accessed 2026-05-01. URL: https://www.nature.com/articles/nn.2723

[6] Redish, A. D., et al. "Computational psychiatry: a report from the 2017 NIMH workshop on opportunities and challenges." Molecular Psychiatry, 2018. DOI: 10.1038/s41380-018-0063-z. Accessed 2026-05-01. URL: https://pubmed.ncbi.nlm.nih.gov/29703948/

[7] Meehan, A. J., Lewis, S. J., & Fazel, S. "Clinical prediction models in psychiatry: a systematic review of two decades of progress and challenges." Molecular Psychiatry, 2022. DOI: 10.1038/s41380-022-01528-4. Accessed 2026-05-01. URL: https://pmc.ncbi.nlm.nih.gov/articles/PMC9156409/

[8] National Institute of Mental Health. "About RDoC." Accessed 2026-05-01. URL: https://www.nimh.nih.gov/research/research-funded-by-nimh/rdoc/about-rdoc/

[9] Marr, D. "Vision: A Computational Investigation into the Human Representation and Processing of Visual Information." MIT Press, 1982. Accessed 2026-05-01. URL: https://mitpress.mit.edu/9780262514620/vision/

[10] Sutton, R. S., & Barto, A. G. "Reinforcement Learning: An Introduction, second edition." MIT Press, 2018. Accessed 2026-05-01. URL: http://incompleteideas.net/book/the-book-2nd.html

[11] Friston, K. J., et al. "Computational psychiatry: from synapses to sentience." Molecular Psychiatry, 2022. DOI: 10.1038/s41380-022-01743-z. Accessed 2026-05-01. URL: https://pubmed.ncbi.nlm.nih.gov/36056173/

[12] Gelman, A., et al. "Bayesian Data Analysis, third edition." CRC Press, 2013. Accessed 2026-05-01. URL: http://www.stat.columbia.edu/~gelman/book/

[13] Lee, M. D., & Wagenmakers, E.-J. "Bayesian Cognitive Modeling: A Practical Course." Cambridge University Press, 2014. Accessed 2026-05-01. URL: https://bayesmodels.com/

[14] Wilson, R. C., & Collins, A. G. E. "Ten simple rules for the computational modeling of behavioral data." eLife, 2019. DOI: 10.7554/eLife.49547. Accessed 2026-05-01. URL: https://elifesciences.org/articles/49547

## 更新履歴

- 2026-05-01: 初版公開。計算論的精神医学を専門にするための学習分野、文献ロードマップ、応用上の注意、限界、インフォグラフィックを追加。

## 更新日付

2026-05-01
