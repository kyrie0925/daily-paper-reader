---
title: Online Isolation Forest
title_zh: 在线孤立森林
authors: "Filippo Leveni, Guilherme Weigert Cassales, Bernhard Pfahringer, Albert Bifet, Giacomo Boracchi"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=CbIZatwz9z"
tags: ["query:anomaly-id"]
score: 9.0
evidence: 用于流式异常检测的在线孤立森林
tldr: 现有流式异常检测方法依赖周期性重训练，不适应动态数据。本文提出在线孤立森林（Online-iForest），专为流式环境设计，能无缝追踪数据生成过程的变化。在真实数据集上实验表明，其性能与在线方法相当，接近最优离线方法且效率更高。为流式异常检测提供了高效实用的方案。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-cbizatwz9z/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1740, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-cbizatwz9z/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1771, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-cbizatwz9z/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-cbizatwz9z/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 849, \"height\": 715, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-cbizatwz9z/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 836, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-cbizatwz9z/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1562, \"height\": 286, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-cbizatwz9z/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1498, \"height\": 630, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-cbizatwz9z/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 848, \"height\": 694, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-cbizatwz9z/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 794, \"height\": 618, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-cbizatwz9z/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 849, \"height\": 715, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-cbizatwz9z/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 760, \"height\": 201, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-cbizatwz9z/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 491, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-cbizatwz9z/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 820, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-cbizatwz9z/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1751, \"height\": 629, \"label\": \"Table\"}]"
motivation: 离线异常检测方法不适用于流式数据，现有在线方法需要周期性重训练。
method: 提出Online-iForest方法，通过增量更新跟踪数据分布变化，适应流式环境。
result: 在真实数据集上性能与最优离线方法相当，且效率领先。
conclusion: 为流式异常检测提供了一种高效且可扩展的方法。
---

## Abstract
The anomaly detection literature is abundant with offline methods, which require repeated access to data in memory, and impose impractical assumptions when applied to a streaming context. Existing online anomaly detection methods also generally fail to address these constraints, resorting to periodic retraining to adapt to the online context. We propose Online-iForest, a novel method explicitly designed for streaming conditions that seamlessly tracks the data generating process as it evolves over time. Experimental validation on real-world datasets demonstrated that Online-iForest is on par with online alternatives and closely rivals state-of-the-art offline anomaly detection techniques that undergo periodic retraining. Notably, Online-iForest consistently outperforms all competitors in terms of efficiency, making it a promising solution in applications where fast identification of anomalies is of primary importance such as cybersecurity, fraud and fault detection.

---

## 论文详细总结（自动生成）

### 论文详细中文总结

#### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究背景**：异常检测在金融欺诈、网络安全、健康监控等领域有广泛应用。传统的孤立森林（Isolation Forest, iForest）等离线方法需要反复访问完整数据集，不适用于流式场景（数据无限、动态变化、单次处理、内存有限）。
- **核心问题**：现有在线异常检测方法（如Isolation Forest ASD、Half Space Trees等）通常依赖于周期性重训练来适应流式环境，这导致处理开销大、适应性延迟，无法满足高速流数据的要求。
- **研究目标**：提出一种专为流式数据设计的在线异常检测方法Online-iForest，能够实时、高效地跟踪数据生成过程的变化，无需周期性重训练。

#### 2. 论文提出的方法论
- **核心思想**：Online-iForest是基于集成学习的在线异常检测方法。每个基模型（Online-iTree）是一个动态的多分辨率直方图，通过滑动窗口机制不断学习新样本、遗忘旧样本，自适应调整数据空间的分辨率，从而高效建模数据分布。
- **关键技术细节**：
  - **Online-iTree结构**：每个节点存储两个信息：bin高度（落入该区域的样本计数）和bin支持（最小包围超矩形）。树结构随着学习新样本而扩展（分裂密度高的区域），随着遗忘旧样本而收缩（合并稀疏区域）。
  - **学习过程（Learn point）**：每当处理一个新样本，更新路径上所有节点的高度和支持；当叶子节点的高度达到阈值 \( \eta \cdot 2^k \)（k为深度），则对该节点进行分裂：随机选择一个维度q和分割值p，从当前bin的支持区域均匀采样bh个点，根据分割值分为左右子节点，初始化子节点的高度和支持。
  - **遗忘过程（Forget point）**：当滑动窗口满时，移除最旧的样本，并更新路径上节点的高度；若某个内部节点的高度低于阈值 \( \eta \cdot 2^k \)，则合并其两个子节点，丢弃分裂信息，更新父节点支持为子节点的最小包围矩形。
  - **异常得分计算**：对于每个新样本，计算其在所有树中的平均深度E(D)，并通过调整因子 \( c(\omega, \eta) = \log_2(\omega/\eta) \) 归一化得到 \( s = 2^{-E(D)/c(\omega,\eta)} \)，接近1表示异常。
  - **关键参数**：滑动窗口大小ω（控制适应速度与建模精度的折衷）、树个数τ、分裂所需最小样本数η（默认32）、最大深度δ=log₂(ω/η)。
- **算法流程**：
  1. 初始化空滑动窗口W和τ棵空树。
  2. 对于每个新样本 \( x_t \)：
     - 将 \( x_t \) 加入W。
     - 对每棵树执行 `learn point`（更新路径节点，可能分裂）。
     - 如果W已满，则弹出最旧样本 \( x_{t-\omega} \)，对每棵树执行 `forget point`（更新路径节点，可能合并）。
     - 计算 \( x_t \) 的异常得分。

#### 3. 实验设计
- **数据集**：
  - **静态数据流（stationary）**：采用8个经典异常检测数据集（Http, Smtp, Annthyroid, Forest Cover Type, Satellite, Shuttle, Mammography, Mulcross）以及2个Kaggle数据集（Donors, Fraud）和一个NYC Taxi shingle数据集。数据特点见Table 2（n从6832到619326，d从2到29，异常比例从0.17%到97%）。
  - **非静态数据流（non-stationary）**：使用INSECTS数据集，包含5次真实概念漂移（温度变化影响昆虫飞行行为），选择两个最丰富类作为正常数据，最稀疏类作为异常数据，共212514个样本，异常比例5.50%。
- **Benchmark方法**：iForestASD（asdIFOR）、Half Space Trees（HST）、Robust Random Cut Forest（RRCF）、LODA。使用PySAD库实现。
- **实验设置**：树个数τ=32，滑动窗口ω=2048（oIFOR和asdIFOR），HST默认ω=250，asdIFOR子采样大小ψ=256，LODA桶数b=100。每个算法运行30次，每次随机打乱数据集。由于数据量大，将数据集按100个样本分批传递给算法。
- **评价指标**：ROC AUC和总运行时间（秒）。使用临界差异图（Critical Difference Diagram）进行统计分析（Nemenyi后验检验）。

#### 4. 资源与算力
- 论文未明确说明使用的GPU型号、数量或训练时长。所有实验均在CPU上运行（因为异常检测算法设计为轻量级），仅报告了总执行时间（秒）。未提及任何GPU资源。

#### 5. 实验数量与充分性
- **实验数量**：
  - 静态数据集共11个，每个算法运行30次，总330次执行。
  - 非静态数据集1个（INSECTS），30次执行。
  - 还进行了早期学习阶段（前1000个样本）的性能分析。
- **充分性**：
  - 覆盖了多种数据规模（几千到几十万样本）、不同异常比例（0.17%~97%）、不同维度（2~33）。
  - 对比了4种代表性在线方法，实验设置公平（统一τ、ω等参数）。
  - 使用统计检验（Nemenyi）比较多个算法在多个数据集上的排名，避免单一数据集偏差。
  - 非静态实验验证了应对概念漂移的能力。
- **客观性**：代码已公开，结果可复现。各方法使用官方或标准实现。

#### 6. 论文的主要结论与发现
- **效率优势**：Online-iForest在所有数据集上运行时间显著短于其他方法（如比asdIFOR快数倍至数十倍），临界差异图显示其时间表现统计显著优于所有对比方法。
- **检测效果**：在静态数据流上，Online-iForest的AUC中位数（0.866）略高于asdIFOR（0.863），但统计检验显示asdIFOR排名第一（平均秩1.583），Online-iForest（2.167）与RRCF（2.5）无显著差异。在多数数据集上，Online-iForest与最优方法差距很小。
- **学习速度**：Online-iForest在初始阶段（前1000样本）快速收敛，且处理时间增长缓慢（线性复杂度，与样本数无关，仅与窗口大小和树深度相关）。
- **应对漂移**：在INSECTS数据集上，所有方法均受概念漂移影响，但没有一种方法能持续保持高性能；Online-iForest表现与其他方法类似，但始终最快。

#### 7. 优点
- **创新性**：首次提出完全在线的孤立森林变体，通过分裂/合并机制实现无缝增量更新，避免了周期性重训练。
- **效率极高**：平均时间复杂度O(n τ log₂(ω/η))，空间复杂度O(τ √(ω/η) + ω)，与数据流长度无关，适合高速流。
- **内存友好**：仅维护滑动窗口和树节点，不存储历史数据。
- **自适应分辨率**：根据数据分布自动调整bin大小，在密集区域细粒度建模，稀疏区域粗粒度，避免了HST等方法的无效内存占用。
- **代码公开**，易于复现和扩展。

#### 8. 不足与局限
- **实验覆盖**：
  - 未在高维数据集（>100维）上进行测试，实际高维流数据（如网络流量）可能面临挑战。
  - 非静态实验只使用了一个数据集（INSECTS），且所有方法性能都下降明显，缺乏对更广泛漂移类型的评估。
  - 未与深度学习方法（如Deep SVDD, DevNet）对比（但后者通常需要GPU且离线训练，不适合在线场景）。
- **参数敏感性**：滑动窗口ω和分裂参数η需手动设置，论文未提供自适应调优策略。
- **局限性**：
  - 假设异常“稀少且不同”，若异常形成密集簇（如Mulcross对HST的影响），性能可能下降。
  - 仅跟踪数据分布变化，无法显式区分概念漂移（正常分布变化）与异常分布变化。
  - 滑动窗口大小固定，无法动态调整以适应不同变化率。
- **统计检测**：尽管AUC排名不如asdIFOR，但差距很小，且效率优势显著；但某些数据集（如NYC Taxi Shingle）上AUC低于RRCF和asdIFOR，可能因数据特征所致。

（完）
