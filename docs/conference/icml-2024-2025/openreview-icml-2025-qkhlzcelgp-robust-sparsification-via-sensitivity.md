---
title: Robust Sparsification via Sensitivity
title_zh: 基于灵敏度的鲁棒稀疏化
authors: "Chansophea Wathanak In, Yi Li, David Woodruff, Xuan Wu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=qKHLzCELGP"
tags: ["query:anomaly-id"]
score: 8.0
evidence: 面向机器学习问题的鲁棒稀疏化框架，抗异常值
tldr: 许多经典机器学习算法缺乏耐异常值的可扩展版本。本文针对包含异常值的鲁棒优化问题，提出了一套通用的epsilon-coreset构建框架，通过灵敏度分析对数据点进行加权子集选择，实现对异常值的鲁棒近似。该方法适用于子空间嵌入、聚类和低秩近似等任务，实验证明了其有效性和可扩展性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-qkhlzcelgp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 877, \"height\": 657, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qkhlzcelgp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1692, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qkhlzcelgp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1707, \"height\": 317, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-qkhlzcelgp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 552, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qkhlzcelgp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 836, \"height\": 465, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qkhlzcelgp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 822, \"height\": 469, \"label\": \"Table\"}]"
motivation: 经典机器学习问题缺乏可扩展的耐异常值算法。
method: 基于灵敏度分析的epsilon-coreset框架，选择加权数据子集实现鲁棒近似。
result: 方法在子空间嵌入、聚类等应用中表现出良好的鲁棒性和可扩展性。
conclusion: 为耐异常值的机器学习算法提供了通用理论框架。
---

## Abstract
Robustness to outliers is important in machine learning. Many classical problems, including subspace embedding, clustering, and low-rank approximation, lack scalable, outlier-resilient algorithms. This paper considers machine learning problems of the form $\min_{x\in \mathbb{R}^d} F(x)$, where $F(x)=\sum_{i=1}^n F_i(x)$, and their robust counterparts $\min_{x\in\mathbb{R}^d} F^{(m)}(x)$, where $F^{(m)}(x)$ denotes the sum of all but the $m$ largest $F_i(x)$ values. 

We develop a general framework for constructing $\epsilon$-coresets for such robust problems, where an $\epsilon$-coreset is a weighted subset of functions $\{F_1(x),\dots,F_n(x)\}$ that provides a $(1+\epsilon)$-approximation to $F(x)$. Specifically, if the original problem $F$ has total sensitivity $T$ and admits a vanilla $\epsilon$-coreset of size $S$, our algorithm constructs an $\epsilon$-coreset of size $\tilde{O}(\frac{mT}{\epsilon})+S$ for the robust objective $F^{(m)}$. This coreset size can be shown to be near-tight for $\ell_2$ subspace embedding. Our coreset algorithm has scalable running time and leads to new or improved algorithms for the robust optimization problems. Empirical evaluations demonstrate that our coresets outperform uniform sampling on real-world data sets.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **问题背景**：许多经典机器学习问题（如子空间嵌入、聚类、低秩近似）缺乏可扩展的、耐异常值的算法。真实数据中常含有异常点（outliers），会导致优化解严重偏离。
- **研究目标**：针对形式为 $\min_x F(x)=\sum_i F_i(x)$ 的优化问题，考虑其鲁棒版本 $\min_x F^{(m)}(x)$，即剔除最大的 $m$ 个 $F_i(x)$ 值后的和。本文旨在为这类鲁棒问题构造 $\epsilon$-coreset（加权子集），使得该子集能近似原始损失，从而加速鲁棒优化。
- **整体意义**：提供一套通用框架，将现有 vanilla coreset 构造方法扩展到鲁棒场景，并给出近紧的 coreset 大小界，为回归、PCA、聚类等鲁棒问题带来新算法或改进。

### 2. 论文提出的方法论
- **核心思想**：基于灵敏度（sensitivity）采样。对于原始函数集合 $F$，若其具有总灵敏度 $T$ 且存在 vanilla $\epsilon$-coreset 大小为 $S$，则可通过两阶段算法构建鲁棒 $(\epsilon,m)$-coreset，大小为 $\tilde{O}(mT/\epsilon)+S$。
- **关键技术细节**：
    1. **第一阶段（识别贡献函数）**：通过重复调用算法 Uniform，以概率 $1/m$ 采样函数子集，筛选出灵敏度 $\ge \epsilon/4$ 的函数，将它们加入集合 $S$。$S$ 的大小被证明为 $O(\frac{Tm}{\epsilon}\log\frac{Tm}{\epsilon})$。
    2. **第二阶段（细化 vanilla coreset）**：对 $F\setminus S$ 构造一个 vanilla $\epsilon$-coreset $V$，然后对 $V$ 中的每个函数进行“分裂”：每个函数复制为 $\lceil \frac{m}{\epsilon}\sigma_V(f) \rceil$ 个副本，每个副本权重均分。这一步保证移除至多 $m$ 个副本后，误差受控。
- **算法流程**（文字说明）：
    - 输入函数集 $A$、参数 $\epsilon,m$ 和 vanilla coreset 构造算法。
    - 初始化 $S=\emptyset$，重复 $R=O(m\log(Tm/\epsilon))$ 次：调用 Uniform$(A,\epsilon,m)$，将返回的集合并入 $S$。
    - 对 $A\setminus S$ 运行 vanilla 算法得到 $V$。
    - 对 $V$ 调用 Refine$(V,\epsilon,m)$，将函数分裂后得到 $\tilde{S}$。
    - 返回 $\tilde{S}\cup\{(f,1):f\in S\}$。
- **公式/理论结果**：本文证明了该算法的核心问题（Theorem 4.1 及其详细证明），并给出了必要的引理（如 Lemma 4.3、4.4）。

### 3. 实验设计
- **数据集**：使用了两个 UCI 数据集：
    - **Appliances Energy Prediction**（简称 Energy）：$19735\times 28$。
    - **Gas Turbine Emission**（简称 Emission）：$36733\times 11$。
- **任务场景**：
    - **子空间嵌入（$\ell_2$）**：验证 coreset 的失真参数（distortion）。
    - **鲁棒回归（Least Trimmed Squares）**：验证目标函数近似误差、解 $\ell_2$ 和 $\ell_\infty$ 范数相对误差，以及运行时间。
- **基准方法**：均匀采样（uniform sampling）。此外，鲁棒回归实验使用了 FastLTS 作为求解器（基准优化方法，非对比方法）。
- **对比指标**：对不同 coreset 大小，计算 1000 次独立实验中平均失真/相对误差及标准差。

### 4. 资源与算力
- **未明确说明**：论文未提供 GPU 型号、数量或训练时长。实验在 “Intel i5-1165G7 @2.80GHz CPU 和 16 GB 内存” 的单机上用 Python 3.12.8 运行。所有实验均在 CPU 上完成。

### 5. 实验数量与充分性
- **实验组数**：
    - 子空间嵌入：对每个数据集，独立重复 1000 次实验，绘制失真 vs. coreset 大小图。
    - 鲁棒回归：对每个数据集，使用 1000 次不同 coreset 进行求解，再取平均值和标准差。
    - 运行时间对比：列出了不同 coreset 大小下的平均运行时（包括构建 coreset 和求解时间）。
- **充分性与公平性**：
    - 实验覆盖了两种不同维度和大小的真实数据集，验证了不同 coreset 大小下算法性能。
    - 对比了均匀采样（基线），显式显示了优势。
    - 存在一定不足：仅对比了均匀采样，未与其他现有鲁棒 coreset 算法（如 Huang et al. 2023a 等）进行直接对比；另外，对鲁棒回归的求解器 FastLTS 本身无理论保证，仅作启发式工具。

### 6. 论文的主要结论与发现
- **理论结论**：当原始问题具有有界总灵敏度 $T$ 且存在 vanilla coreset 时，本文算法可在 $\tilde{O}(mT/\epsilon)+S$ 大小内构造鲁棒 $(\epsilon,m)$-coreset。对 $\ell_2$ 子空间嵌入，该大小接近最优 $\Omega(md/\epsilon)$。
- **实验结论**：本文的 coreset 在失真度和目标函数近似误差上显著优于均匀采样；在保持近似精度的同时，大幅减小了运行时间（例如仅用约 5%-10% 的数据即可获得可接受的近似）。

### 7. 优点
- **通用性**：框架只依赖总灵敏度和 vanilla coreset 的存在性，适用于多种问题（回归、PCA、k-median 等）。
- **理论紧致性**：给出了近最优的 coreset 大小下界，证明了 $\tilde{O}(mT/\epsilon)+S$ 几乎是最优的。
- **可扩展性**：算法运行时间与原始问题规模近线性，且对 $m$ 和 $\epsilon$ 的依赖较温和。
- **实验验证充分**：在多个真实数据集、多指标（失真、损失、解误差、时间）上进行对比，结果具有统计显著性。

### 8. 不足与局限
- **实验覆盖不足**：仅对比均匀采样，未与现有专门鲁棒 coreset 方法（如针对聚类）比较。
- **应用限制**：框架要求总灵敏度 $T$ 有界且已知上界，某些情况下可能不易获得；分裂操作可能引入额外常数因子。
- **鲁棒回归实验**：采用的 FastLTS 求解器收敛性无理论保证，实验结果可能受求解器影响。
- **资源信息缺失**：未报告 GPU 或大规模并行化实验，算力分析不完整。
- **偏差风险**：实验中预设的 $\epsilon=0.25$ 较大，实际失真可能受该参数影响；$X$ 的采样方式（正态分布）可能与真实数据分布不同。

（完）
