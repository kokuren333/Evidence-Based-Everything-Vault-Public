---
project: "Evidence Based Everything"
title: "GPUとは何か"
status: "published"
draft: false
publish_ready: true
review_status: "passed"
article_type: "reference"
created: 2026-05-04
updated: 2026-05-04
last_verified: 2026-05-04
freshness_ttl: "90 days"
question: "GPUとはなにか"
question_type: "what"
claim_types:
  - definitional
  - technical
  - historical
  - comparative
  - procedural
category_id: "07"
category_name: "技術・工学・コンピューティング・AI"
category_path: "10_Published/07_Technology_Engineering_Computing_AI"
subfield_name: "GPU・並列計算"
subfield_path: "10_Published/07_Technology_Engineering_Computing_AI/GPU・並列計算__gpu-parallel-computing"
moc: "10_Published/07_Technology_Engineering_Computing_AI/GPU・並列計算__gpu-parallel-computing/_MOC.md"
domain_profile: "technology_engineering"
evidence_standard: "official documentation, specifications, reproducible examples, benchmarks"
confidence: "high"
confidence_reason: "GPUの定義、歴史、プログラミングモデル、現在の用途は、NVIDIA CUDA文書、Khronos OpenCL/Vulkan仕様、Microsoft Direct3D文書、AMD ROCm文書、Intel oneAPI GPU最適化文書などの一次・公式資料で相互確認できる。性能比較は機種・ワークロード依存なので限定付きで述べる。"
has_infographic: true
infographic_path: "50_Assets/Infographics/gpu-overview-2026-05-04.png"
source_count: 8
claim_count: 14
references_style: "numbered"
---

![[50_Assets/Infographics/gpu-overview-2026-05-04.png]]

図1. GPUは、多数の小さな実行器と広いメモリ帯域を使って、同じ種類の処理を大量データへ並列に適用するプロセッサとして理解できる。画像処理だけでなく、CUDA、OpenCL、ROCm、Vulkanなどを通じてAI、科学技術計算、映像処理にも使われる。[1][2][3][4][6]

# 概要

GPUとは、Graphics Processing Unit、すなわち本来は画像や3Dグラフィックスを高速に処理するために発展したプロセッサである。現代的には、GPUは「大量のデータに似た計算を同時に行う」ための並列計算アクセラレータでもある。[1][2][3]

CPUが少数の高機能なコアで分岐、OS処理、逐次処理、複雑な制御を幅広く担当するのに対し、GPUは多数の実行器、広いメモリ帯域、スレッド群を束ねる実行モデルを使って、画像の各ピクセル、行列演算の各要素、ニューラルネットワークのテンソル演算などを高スループットで処理する。[2][5][6]

# この記事の見取り図

GPUを理解する要点は三つである。第一に、GPUは「画面表示用の部品」だけではなく、データ並列計算のためのプロセッサである。第二に、GPUが速いのは万能に速いからではなく、同じ処理を多数のデータに適用する問題に合わせて設計されているからである。第三に、GPUを活用するには、CPU、GPU、メモリ、API、ライブラリの役割分担を意識する必要がある。[2][3][6]

# 定義と全体像

狭い意味のGPUは、画像生成、3D描画、シェーダ実行、ラスタライズ、テクスチャ処理など、グラフィックス処理を担うプロセッサである。Vulkan仕様では、グラフィックスパイプラインと計算パイプラインが区別され、シェーダは頂点、フラグメント、ワークグループなどの段階で実行されるプログラムとして扱われる。[6]

広い意味のGPUは、汎用計算にも使われる並列プロセッサである。CUDAはGPUを使った並列計算プラットフォームであり、NVIDIAの公式文書は、GPUが同等の価格・電力枠でCPUより高い命令スループットとメモリ帯域を提供しうると説明している。[2] OpenCLは、CPU、GPU、DSP、FPGAなど多様なアクセラレータを対象にするクロスプラットフォームの並列プログラミング標準である。[3]

GPUの本質は「たくさんの小さな計算を同時に進める設計」にある。IntelのGPU最適化文書は、GPGPU計算ではホストプログラムとGPU上で実行されるカーネルがあり、ワークグループが同じカーネルを多数の項目に対して実行する考え方がデータ並列計算の中核だと説明している。[5]

# 歴史的背景・古典的理解

GPUという言葉は、1990年代末のPC向け3Dグラフィックス競争の中で一般化した。NVIDIAはGeForce 256を1999年に「世界初のGPU」として導入したと説明しており、当時の文脈では、変換、ライティング、三角形処理、レンダリングなどを単一チップで担うグラフィックス用プロセッサという意味合いが強かった。[1]

古典的な理解では、GPUは「画面を描くための専用チップ」だった。固定機能パイプラインの時代には、描画処理の多くがあらかじめハードウェアに組み込まれていた。その後、Direct3DやVulkanなどのグラフィックスAPIが発展し、シェーダによるプログラム可能なパイプラインが一般化した。[6][7]

2000年代以降、GPUはグラフィックス専用から汎用並列計算へ拡張された。CUDA、OpenCL、のちのROCmやoneAPI系の道具立ては、GPUを科学技術計算、機械学習、画像・映像処理、シミュレーションに使うためのプログラミングモデルとライブラリを整備した。[2][3][4][5]

# 現在の標準的理解

現在の標準的理解では、GPUはCPUに置き換わる部品ではなく、CPUと協調するアクセラレータである。CUDA文書は、CPU側のホストプログラムとGPU側のデバイス上で動くカーネルを分けて説明し、ホストメモリとデバイスメモリが別空間であること、必要に応じてデータ転送や管理メモリを扱うことを前提にしている。[2]

GPUは、画像処理、深層学習、線形代数、物理シミュレーション、動画エンコード、科学技術計算などに適している。理由は、これらの多くが行列、ベクトル、ピクセル、粒子、格子点のような大量の要素に似た処理を適用するからである。[2][3][4]

一方で、GPUは何でも速くする魔法の部品ではない。分岐が多い処理、データ依存で逐次的に進む処理、GPUへ送るデータ量に比べて計算が少ない処理、メモリアクセスが不規則な処理では、CPUのほうが適する場合がある。GPU性能は、演算器数だけでなく、メモリ階層、メモリ帯域、データ転送、カーネル設計、APIとライブラリの成熟度に左右される。[2][5]

# 詳細説明

## CPUとGPUの違い

CPUは、OS、ブラウザ、データベース、アプリケーション制御、条件分岐の多い処理など、幅広い仕事を低遅延でこなす汎用プロセッサである。GPUは、個々の処理の柔軟性よりも、同種の処理を大量に並べるスループットに寄せたプロセッサである。[2][5]

たとえば100万個の画素に同じ色変換を行う、巨大な行列同士を掛ける、ニューラルネットワークの層を一括計算する、粒子シミュレーションで各粒子の位置を更新する、といった処理ではGPUの設計が合いやすい。[2][3][4]

## GPUの内部モデル

GPUプログラミングでは、CPU側のプログラムがGPUへ仕事を投入し、GPU側でカーネルと呼ばれる関数が多数のスレッドとして実行される、という見方をすることが多い。CUDAでは、スレッド、スレッドブロック、グリッド、共有メモリ、グローバルメモリなどの階層が明示される。[2]

この階層は性能理解に直結する。GPUは多数の演算器を遊ばせないように大量のスレッドを走らせるが、メモリからデータが届かなければ演算器は待たされる。したがって、GPU最適化では「演算回数」だけでなく「データをどの順序で、どのメモリ階層から読むか」が重要になる。[2][5]

## グラフィックスと汎用計算

グラフィックス用途では、GPUは頂点処理、ラスタライズ、フラグメント処理、テクスチャ参照、出力合成などを通じて画像を生成する。Vulkan仕様やDirect3D 12文書は、GPUへ渡すパイプライン状態やシェーダを明示的に扱う現代的なグラフィックスAPIの構造を示している。[6][7]

汎用計算用途では、GPUは画像を描くためではなく、配列やテンソルを処理するために使われる。CUDAはNVIDIA GPU向け、ROCm/HIPはAMD GPU向け、OpenCLは複数ベンダー・複数アクセラレータ向けの代表的な道具である。[2][3][4]

# 応用・実践上の含意

GPUを使うべきかどうかは、問題が十分に並列化できるか、計算量がデータ転送コストを上回るか、既存ライブラリがあるかで判断する。深層学習ならPyTorchやTensorFlowなどのフレームワーク、数値計算ならBLAS、FFT、線形代数、画像処理ライブラリを使うほうが、低レベルカーネルを最初から書くより実用的である。[2][4]

GPU選定では、単純な「コア数」よりも、対象ワークロードに必要なメモリ容量、メモリ帯域、対応精度、ソフトウェアエコシステム、ドライバ、ライブラリ対応を確認する必要がある。AI用途ではテンソル演算支援や対応フレームワーク、科学計算では倍精度性能や通信、グラフィックス用途ではAPI対応と表示・描画性能が重要になる。[2][4][6]

# 限界・論争点・未解決事項

第一に、GPU性能は移植性が難しい。OpenCLはクロスプラットフォーム標準だが、実際の性能はベンダー、ドライバ、メモリ階層、コンパイラ、ワークロードに左右される。[3][5]

第二に、GPUは電力、発熱、メモリ容量、データ移動の制約を受ける。大規模AIではGPUの演算性能だけでなく、GPU間通信、メモリ容量、データセンター電力、ソフトウェアスタックの安定性がボトルネックになる。[4]

第三に、「GPUがCPUより速い」という一般化は危険である。GPUは大量のデータ並列処理に強いが、逐次制御、低遅延の単発処理、分岐の多い処理、小さすぎる処理ではCPUが有利な場合がある。[2][5]

# まとめ

GPUとは、もともと画像・3Dグラフィックスのために発展し、現在ではAIや科学技術計算にも広く使われる並列プロセッサである。GPUの強みは、多数のデータ要素に似た計算を同時に適用できることにある。CPUとGPUは競合するというより、CPUが制御し、GPUが大量並列計算を加速する役割分担で理解するとよい。[2][3][5]

# 参考ソース

[1] NVIDIA Blog. "Game-Changer: How the World's First GPU Leveled Up Gaming and Ignited the AI Era." Published 2024-08-31. Accessed 2026-05-04. URL: https://blogs.nvidia.com/blog/first-gpu-gaming-ai/

[2] NVIDIA Documentation. "CUDA C++ Programming Guide." CUDA Toolkit Documentation. Accessed 2026-05-04. URL: https://docs.nvidia.com/cuda/cuda-c-programming-guide/index.html

[3] The Khronos Group. "OpenCL - The Open Standard for Parallel Programming of Heterogeneous Systems." Accessed 2026-05-04. URL: https://www.khronos.org/opencl/

[4] AMD. "AMD ROCm Software." Accessed 2026-05-04. URL: https://www.amd.com/en/products/software/rocm.html

[5] Intel. "oneAPI GPU Optimization Guide: Execution Model Overview." Accessed 2026-05-04. URL: https://www.intel.com/content/www/us/en/docs/oneapi/optimization-guide-gpu/2024-1/execution-model.html

[6] Khronos Vulkan Documentation Project. "Shaders." Vulkan Specification. Accessed 2026-05-04. URL: https://docs.vulkan.org/spec/latest/chapters/shaders.html

[7] Microsoft Learn. "Direct3D 12 graphics." Published 2021-12-30. Accessed 2026-05-04. URL: https://learn.microsoft.com/en-us/windows/win32/direct3d12/direct3d-12-graphics

[8] Intel. "What Is a GPU? Graphics Processing Units Defined." Accessed 2026-05-04. URL: https://www.intel.com/content/www/us/en/products/docs/processors/what-is-a-gpu.html

# 更新履歴

- 2026-05-04: 新規作成。GPUの定義、歴史、CPUとの違い、現在の用途、限界を公式資料ベースで整理した。

# 更新日付

2026-05-04
