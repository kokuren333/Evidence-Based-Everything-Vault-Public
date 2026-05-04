---
project: "Evidence Based Everything"
title: "3Dプリンターフィラメント間の接着性比較"
status: "published"
draft: false
publish_ready: true
review_status: "passed"
article_type: "evidence_based_review"
created: 2026-05-02
updated: 2026-05-02
last_verified: 2026-05-02
freshness_ttl: "90 days"
question: "3Dプリンターの異なるフィラメント同士のくっつきやすさについて比較する"
question_type: "mixed"
claim_types:
  - definitional
  - technical
  - comparative
  - procedural
  - historical
category_id: "07"
category_name: "技術・工学・コンピューティング・AI"
category_path: "10_Published/07_Technology_Engineering_Computing_AI"
subfield_name: "3Dプリンティング材料"
subfield_path: "10_Published/07_Technology_Engineering_Computing_AI/3Dプリンティング材料__3d-printing-materials"
moc: "10_Published/07_Technology_Engineering_Computing_AI/3Dプリンティング材料__3d-printing-materials/_MOC.md"
domain_profile: "technology_engineering"
evidence_standard: "official documentation, specifications, reproducible examples, benchmarks"
confidence: "medium-high"
confidence_reason: "接着機構と一部材料ペアは査読論文で支えられるが、フィラメント銘柄、乾燥状態、温度、造形機、スライサー設定で結果が大きく変わるため、普遍順位ではなく実務的比較として扱う。"
has_infographic: true
infographic_path: "50_Assets/Infographics/filament-adhesion-compatibility_infographic.png"
source_count: 9
claim_count: 10
references_style: "numbered_url_accessed"
---

# 3Dプリンターフィラメント間の接着性比較

![[50_Assets/Infographics/filament-adhesion-compatibility_infographic.png]]

図1. FFF/MEX方式で異なるフィラメントを組み合わせるときは、「構造材として強く接着したい」のか「サポート界面として後で剥がしたい」のかで望ましい材料ペアが変わる。接着は温度履歴、相溶性、濡れ、分子拡散、収縮、水分、界面汚染に左右されるため、表は絶対順位ではなく設計上の見取り図として読む。[2][3][4][7][8][9]

## 概要

FFF、FDM、MEX系の3Dプリンターで異なるフィラメントを重ねるとき、最初に分けるべき問いは二つである。一つは、複合部品として界面を壊れにくくしたいのか。もう一つは、サポート材として印刷中だけ支え、造形後にきれいに剥がしたいのかである。[1][2][7]

構造材として見るなら、同じ樹脂同士が最も安定しやすく、異種材料では温度窓が重なり、濡れと分子拡散が起こり、冷却収縮差が小さい組み合わせほど有利になる。[2][3][5][6] 近年のマルチマテリアルFFF研究では、PETG-PC、PLA-PC、PLA-PETG、Nylon-PVAなどが比較的良好または実用可能な組み合わせとして扱われているが、これは特定材料・条件での結果であり、全メーカー品にそのまま外挿できる順位ではない。[3][4]

サポート界面として見るなら、むしろ「強すぎない接着」が有利である。PVA/BVOHは水溶性サポートとして、Breakawayは手で剥がすサポートとして設計され、PLA/PETGのような組み合わせも低接着界面として使われることがある。[7][8][9]

## この記事の見取り図

| 目的 | 望ましい界面 | 代表例 | 注意点 |
|---|---|---|---|
| 構造的に強くつなぐ | 高い界面強度、破壊が界面だけに集中しにくい | 同材同士、PLA/PETG、PETG/PC、PLA/PC、条件付きのNylon/PVA | 試験片で確認する。フィラメント銘柄差が大きい。[3][4] |
| サポートとして剥がす | 造形中は保持し、冷却後または水中で除去できる | PVA/BVOH、Breakaway、PLA/PETG界面 | 弱すぎるとサポート界面が印刷中に失敗する。[7][8][9] |
| 実験・試作として試す | 形状・温度・乾燥・チャンバー条件を固定して比較 | PLA/ABS、PLA/TPU、ASA/TPUなど | 収縮差、反り、界面汚染、ノズル切替残留が結果を変える。[5][6] |
| 避けるか要検証 | 低表面エネルギー、熱窓が遠い、収縮差が大きい | PP、PE、POM、特殊配合材 | 接着不良だけでなく造形安定性も問題になりやすい。[3][6] |

## 定義と全体像

ISO/ASTM 52900では、材料をノズル等から選択的に押し出す方式がmaterial extrusion、MEXとして整理される。[1] 一般的なデスクトップ機で使われるFFFは、熱可塑性フィラメントを加熱して押し出し、冷えながら層を積むMEX系の代表である。[2]

この方式の接着は、接着剤で貼るのではなく、溶けた樹脂が下の層や隣の材料に濡れ、十分な温度と時間のなかで分子鎖が界面をまたいで動き、冷却後に機械的・物理的につながる現象として理解できる。[2][3] したがって、材料名だけで「PLAとPETGは必ず付く」「ABSとTPUは必ず付かない」と言い切るのは危険である。

## 歴史的背景・古典的理解

初期のFFF/FDM的な使い方では、単一材料を層状に積むことが中心だった。異なる色の同じ樹脂を切り替える用途や、モデル材とサポート材を分ける用途は比較的早く普及したが、異なる工学材料を一体の構造材として扱うには、界面強度、収縮、ノズル切替、材料乾燥、熱履歴の問題が残った。[2][6]

古典的な実務理解では、「同じ材料同士は付きやすく、違う材料はサポート向き」と単純化されがちだった。しかし、マルチマテリアル機や多材料研究が進むにつれ、界面強度は材料カテゴリだけでなく、設計、層構成、温度、速度、チャンバー、試験方法に強く依存することが明確になっている。[3][5][6]

## 現在の標準的理解

現在の標準的な見方は、異種フィラメント接着を「材料相性」と「プロセス相性」の積として扱うことである。材料相性には、極性、相溶性、Hansen溶解度パラメータの近さ、ガラス転移温度や融点、熱膨張率、吸湿性が含まれる。[3][6] プロセス相性には、ノズル温度、ベッド温度、チャンバー温度、印刷速度、層高、接触時間、冷却、乾燥、表面汚染、パージ不足が含まれる。[2][3][5]

実務上は、次のように読むのが最も安全である。

| 材料ペア | 構造接着の期待 | サポート界面としての適性 | 根拠と解釈 |
|---|---:|---:|---|
| 同材同士 | 高 | 低 | 最も単純で、材料・温度・収縮が揃いやすい。[2][3] |
| PLA/PETG | 中 | 中-高 | 研究上は多材料構造として成立しうる一方、低接着界面として使われることもある。[4][9] |
| PETG/PC | 中-高 | 低-中 | 良好なペア例として扱われるが、PC側の高温条件に注意する。[3] |
| PLA/PC | 中-高 | 低-中 | 良好なペア例として扱われるが、PLAの熱限界とPCの温度要求が衝突しやすい。[3] |
| Nylon/PVA | 中 | 高 | 研究上の良好ペア例と、サポート材としてのPVA利用を区別する必要がある。[3][7] |
| PLA/PVA・PLA/BVOH | 構造用途は低 | 高 | 水溶性サポートとして有用。PLAと温度窓が近い点が実務上重要。[7][8] |
| ABS/Breakaway、Nylon/Breakaway | 構造用途は低 | 高 | 剥離前提のサポート材で、強接着の証拠ではない。[7] |
| PLA/ABS | 低-中 | 低-中 | 造形・研究は可能だが、収縮差と設計依存性が大きい。[5] |
| TPU/PLA、TPU/ASA | 低-中 | 低-中 | 柔軟材は濡れ・変形・押出安定性が効く。機種と銘柄依存が大きい。[6] |
| PP/PE/POM系 | 低 | 低-中 | 低表面エネルギーや熱窓の違いから要検証。接着目的では難材として扱う。[3][6] |

## 詳細説明

### 強く接着したい場合

強い界面を狙うときは、まず同材同士を基準にする。異種材料が必要な場合は、温度窓が重なること、下層が完全に冷え切る前に次材料が濡れること、冷却収縮で界面に大きな残留応力が残らないことが重要になる。[2][3][5]

PETG/PC、PLA/PC、PLA/PETGのような組み合わせは、特定研究で好ましい組み合わせとして検討されている。[3][4] ただし、PCは高温側、PLAは低温側に制約があるため、同じ「PLA/PC」でもノズル温度、チャンバー、形状、銘柄で界面破壊にも本体破壊にも振れる。ランキング表は出発点であって、設計値ではない。[3][6]

### 剥がしたいサポートの場合

サポート材では評価軸が逆になる。良いサポート界面は、印刷中に落ちない程度に接着し、造形後には水で溶けるか、手で剥がれる必要がある。[7][8] PVA/BVOHは水溶性サポートであり、PrusaはPLAとの温度相性を実用上の理由として挙げる。[8] UltiMakerはPVAをPLA、Nylon、CPE向け、BreakawayをABS、Nylon、PLA、CPE、CPE+向けとして説明している。[7]

Bambu LabのSupport for PLA/PETGのように、PLAやPETGのサポート界面用に調整された材料もある。[9] これは「PLA/PETGが常に弱い」という意味ではなく、サポート用の距離、界面層、温度、材料配合を含めて、剥離しやすい条件を作っていると理解するほうがよい。

### なぜ同じ組み合わせで結果が割れるのか

同じ材料名でも、実際のフィラメントは添加剤、顔料、強化繊維、耐熱改質、吸湿状態が異なる。さらに、マルチマテリアル印刷ではノズル内の残留樹脂をどれだけパージしたか、切替直後の温度が安定しているか、界面の小さな島が十分に定着するかが結果に直結する。[3][5][6]

そのため、「この組み合わせはくっつくか」という問いに対する実務的な答えは、最終部品と同じ向き、同じ層高、同じ温度、同じ乾燥条件、同じサポート設定で小さな試験片を作り、界面で剥がれるか、母材側で壊れるかを観察することである。[3][5]

## 応用・実践上の含意

構造部品では、候補ペアを決める前に「界面が荷重を受ける設計か」を確認する。界面に引張や剥離が集中するなら、異種材料の接着性に頼るより、形状ロック、ねじ、溝、アンダーカット、オーバーモールド的な機械的拘束を併用するほうが堅い。[5][6]

サポート目的では、モデル材とサポート界面材を分け、界面だけ高価なPVA/BVOHや専用サポート材にする設計が現実的である。[7][8][9] ただし、サポート島が小さい、接触面積が少ない、切替後の最初のラインが冷える、といった条件では、低接着の長所がそのまま失敗原因になる。

現場での最小チェックリストは次の通りである。

1. 目的を「強接着」か「剥離」かに分ける。
2. フィラメントを乾燥し、同一ロットまたは同一ブランド内で試す。
3. 温度窓が重なる範囲で、界面側の温度と速度を保守的に設定する。
4. パージ不足による混色・混材を観察する。
5. 小型クーポンで、界面剥離か母材破壊かを記録する。
6. 本番形状では、界面に剥離荷重が集中しないようにする。

## 限界・論争点・未解決事項

この記事の比較は、フィラメントの一般名から得られる実務的な見取り図であり、材料データシートの代替ではない。PLA、PETG、ABS、ASA、PC、Nylon、TPUはいずれもグレード、添加剤、顔料、繊維、乾燥状態で性質が変わる。[3][6]

研究論文の結果は、試験片形状、積層方向、材料メーカー、温度、速度、測定方法に依存する。メーカー資料は実務上有用だが、自社材料・自社プリンター・自社プロファイルに最適化されていることが多い。[7][8][9] したがって、荷重を受ける部品では、一般表だけで採用せず、少なくとも実機試験と破壊モード確認を行うべきである。

未解決の点として、消費者向けフィラメントの配合が非公開であること、マルチマテリアル切替時の残留樹脂が界面に与える影響を標準化して比較しにくいこと、サポートとして良い弱接着と構造材として悪い弱接着が同じ語で語られやすいことがある。[3][5][6]

## まとめ

異種フィラメントの接着性は、材料名だけの暗記表ではなく、目的別に判断する。強くつなぎたいなら、同材同士を基準に、温度窓、相溶性、収縮差、乾燥、界面設計を確認する。剥がしたいなら、PVA/BVOH、Breakaway、PLA/PETG系のサポート界面のように、印刷中の保持と造形後の除去を両立する材料を選ぶ。[3][7][8][9]

最も重要な実務原則は、ランキングを設計値として使わないことである。最終部品と同じプリンター、同じフィラメント、同じスライサー設定、同じ向きで試験片を出し、界面で剥がれるのか、母材で壊れるのかを観察する。この一手間が、異種材料マルチマテリアル印刷の失敗を大きく減らす。[3][5][6]

## 参考ソース

[1] ISO. "ISO/ASTM 52900:2021 Additive manufacturing - General principles - Fundamentals and vocabulary." URL: https://www.iso.org/standard/74514.html Accessed: 2026-05-02.

[2] Cantore, S. et al. "Thermo-Mechanical Approach to Material Extrusion Process During Fused Filament Fabrication of Polymeric Samples." URL: https://pmc.ncbi.nlm.nih.gov/articles/PMC12525860/ Accessed: 2026-05-02.

[3] "Investigation of Polymer Adhesion of Materials in Multimaterial FFF Process." URL: https://pmc.ncbi.nlm.nih.gov/articles/PMC13075148/ Accessed: 2026-05-02.

[4] "The Mechanical Properties of 3D-Printed Polylactic Acid/Polyethylene Terephthalate Glycol Multi-Material Structures Manufactured by Material Extrusion." URL: https://pmc.ncbi.nlm.nih.gov/articles/PMC10880662/ Accessed: 2026-05-02.

[5] "Material Extrusion of Multi-Polymer Structures Utilizing Design and Shrinkage Behaviors: A Design of Experiment Study." URL: https://pmc.ncbi.nlm.nih.gov/articles/PMC10302934/ Accessed: 2026-05-02.

[6] "Modeling Materials Coextrusion in Polymers Additive Manufacturing." URL: https://pmc.ncbi.nlm.nih.gov/articles/PMC9863070/ Accessed: 2026-05-02.

[7] UltiMaker. "Which 3D printing supports to use: PLA, PVA or Breakaway." URL: https://ultimaker.com/learn/which-3d-printing-supports-to-use-pla-pva-or-breakaway/ Accessed: 2026-05-02.

[8] Prusa Knowledge Base. "Water soluble (BVOH/PVA)." URL: https://help.prusa3d.com/article/water-soluble-bvoh-pva_167012 Accessed: 2026-05-02.

[9] Bambu Lab. "Support for PLA/PETG." URL: https://us.store.bambulab.com/products/support-for-pla-petg Accessed: 2026-05-02.

## 更新履歴

- 2026-05-02: 新規作成。マルチマテリアルFFF/MEXの接着機構、材料ペア比較、サポート界面としての解釈、実務チェックリストを追加。

## 更新日付

2026-05-02
