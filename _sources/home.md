# 講義の狙いと資料の概要

[原子核三者若手夏の学校 2025](https://www2.yukawa.kyoto-u.ac.jp/~sansha.wakate/school2025/index.html)の原子核パート「Julia言語による原子核構造計算入門」の資料です。

## 講義の狙い


原子核物理の構造計算は、昔から量子化学や物性物理学、ひろく計算物理など、周辺分野と多くの共通点を持ち、ときにアイデアを相互に輸入したりしながら発展してきた経緯があります。
原子核は、核子間に働く核力の複雑さに由来して、最も計算が泥臭い量子多体系と言えるかもしれません。
ただし、それ故に陽子や中性子の数が一つ変わるだけで、あるいは同じ原子核の異なる状態を見るだけで、全く異なる構造や反応を示すこともある、非常にリッチで魅力的な研究対象です。
特に顕著な例としては、クラスター構造やハロー核など、一つの原子核の一つの状態であっても、複数の手法・視点が不可欠となる面白い構造があります。

近年の原子核構造の理論計算は、手法が多様化・細分化しており、一人の研究者がすべての手法を網羅することは困難とも言えます。
本講義では、比較的シンプル(かつ奥の深い)なpairing Hamiltonianを題材として、
現代的な核構造計算で用いられる多様な多体計算手法を、時間の許す限りできるだけ誤魔化しをせずに説明・実装することを目指します。

これにより、原子核構造計算の基礎的な理解を深めるとともに、新たな手法の開発や既存手法の改良にも役立つ知識を身につけることを目指します。

| 手法  | 対応する章 | 
| -- | -- | 
| Configuration Interaction (CI) | [2章](notebooks/FullCI.html) | 
| Hatree-Fock (HF) | [3章](notebooks/HartreeFock.html) |
| Bardeen-Cooper-Schrieffer (BCS) |  [4章](notebooks/BCS.html)   | 
| Many-Body Perturbation Theory (MBPT) | [5章](notebooks/MBPT.html)  |
| Coupled Cluster (CC)|  [6章](notebooks/CoupledCluster.html)  | 
| In-Medium Similarity Renormalization Group (IM-SRG) | [7章](notebooks/IMSRG.html) | 
| Eigenvector Continuation | [8章](notebooks/EC.html)  |  
| Quantum Computing | [9章](notebooks/QuantumComputing.html) [10章](notebooks/Pairing_QC_pennylane.html) [11章](notebooks/Pairing_QC_pytket.html) |  


## PairingHamiltonian.jl

こうした手法を扱う数値計算コードは、様々な言語で書かれ(たまにオープンソースとして公開されていることもありますが)、
その多くは研究室・グループの秘伝コードであったり、特定の研究目的に特化していたりすることが多いです。
もちろんそのことは、非難されるべきことではありませんが、初学者が核構造計算の手法を学んだり、他者とアイデアを共有・交換しながら新たな手法を開発するためには、
できるだけ多くの人がアクセスしやすい形でコードを公開することもまた分野にとって望ましいことであると筆者は考えています。
機械学習の分野があれほどまでに急速に発展したのも、多くの人がアクセスしやすい形でコードを公開し、共有したことが大きな要因であると考えられ、
こうした文化から学べることも多いと考えています(もちろん、全てのコードがオープンソースであるべきだとは考えていませんので悪しからず)。

このような個人的な信念から、本講義で使用するコードはJulia言語で実装し、GitHub上で公開するとともにJuliaのパッケージとして公開することにしました。
[PairingHamiltonian.jl](https://github.com/sotayoshida/pairinghamiltonian.jl)
Pairing Hamiltonianというシンプルなモデルを題材にしているとはいえ、単一のコード(プロジェクト)で、
CI, HF, BCS, MBPT, CC, IM-SRG, Quantum Computingといった多様な手法を実装/解説したコード&資料は、筆者の知る限り他にはないと自負しています。

筆者はこの他にも

- カイラル核力
- HF, MBPT
- IM-SRG
- 殻模型
- Surrogate model

などを扱う原子核構造計算に関するコード群をJulia言語で実装し、パッケージとして公開しています。
気になった方は[NuclearToolkit.jl](https://github.com/sotayoshida/nucleartoolkit.jl)をご覧ください。


## 関連する講義資料

- [計算物理春の学校2024: NuclearToolkit.jlによる原子核構造計算入門](https://sotayoshida.github.io/Lecture_CompPhys_SpSchool24/home.html)  
  カイラル核力から、IM-SRG, 殻模型, 代理モデルまでを扱った講義資料です。この講義のあとであれば、よりスムーズに理解できるかも。


