---
title: Towards a Unified Framework of Clustering-based Anomaly Detection
title_zh: 走向基于聚类的统一异常检测框架
authors: "Zeyu Fang, Ming Gu, Sheng Zhou, Jiawei Chen, Qiaoyu Tan, Haishuai Wang, Jiajun Bu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=1dd7q3Ktkz"
tags: ["query:anomaly-id"]
score: 8.0
evidence: 基于聚类的统一异常检测框架
tldr: 本文针对无监督异常检测中表示学习与聚类相互依赖关系未充分探索的问题；提出一种新颖的概率混合模型，从理论上统一了表示学习、聚类和异常检测；通过最大化异常感知的变分下界，模型联合学习嵌入和聚类结构；实验证明该方法在多个基准数据集上优于现有方法，为异常检测提供了统一的理论框架。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-1dd7q3ktkz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 831, \"height\": 291, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1dd7q3ktkz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 838, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1dd7q3ktkz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1708, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1dd7q3ktkz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1759, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1dd7q3ktkz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1768, \"height\": 459, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-1dd7q3ktkz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1786, \"height\": 1231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1dd7q3ktkz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 161, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1dd7q3ktkz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 785, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1dd7q3ktkz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1320, \"height\": 1392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1dd7q3ktkz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1778, \"height\": 838, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1dd7q3ktkz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1778, \"height\": 842, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1dd7q3ktkz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 728, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1dd7q3ktkz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 564, \"height\": 234, \"label\": \"Table\"}]"
motivation: 现有方法割裂了表示学习与聚类在异常检测中的协同作用，缺乏统一理论指导。
method: 提出概率混合模型，通过变分推断联合优化表示学习与聚类，实现端到端的异常检测。
result: 在多个异常检测基准上，该框架显著提升了检测性能，并提供了理论一致性。
conclusion: 统一表示学习与聚类可有效提升无监督异常检测的效果与可解释性。
---

## Abstract
Unsupervised Anomaly Detection (UAD) plays a crucial role in identifying abnormal patterns within data without labeled examples, holding significant practical implications across various domains. Although the individual contributions of representation learning and clustering to anomaly detection are well-established, their interdependencies remain under-explored due to the absence of a unified theoretical framework. Consequently, their collective potential to enhance anomaly detection performance remains largely untapped. To bridge this gap, in this paper, we propose a novel probabilistic mixture model for anomaly detection to establish a theoretical connection among representation learning, clustering, and anomaly detection. By maximizing a novel anomaly-aware data likelihood, representation learning and clustering can effectively reduce the adverse impact of anomalous data and collaboratively benefit anomaly detection. Meanwhile, a theoretically substantiated anomaly score is naturally derived from this framework. Lastly, drawing inspiration from gravitational analysis in physics, we have devised an improved anomaly score that more effectively harnesses the combined power of representation learning and clustering. Extensive experiments, involving 17 baseline methods across 30 diverse datasets, validate the effectiveness and generalization capability of the proposed method, surpassing state-of-the-art methods.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：无监督异常检测（UAD）中，表示学习与聚类各自已被证明能提升异常检测性能，但它们之间的相互依赖关系（如聚类需要排除异常样本、表示学习需避免保留异常模式）尚未被充分探索，缺乏统一的理论框架来协同优化三者，导致潜力未被充分利用。
- **背景**：现有方法多将表示学习、聚类和异常检测作为独立目标叠加（如 DAGMM、DCFOD），或仅关注两两交互（如KMeans--），没有从概率生成角度建模三者内在联系，因而无法有效抑制异常对表示学习和聚类的干扰。

## 2. 方法论
- **核心思想**：提出 **UniCAD**，通过最大化一个 **异常感知的数据似然** 来统一表示学习、聚类和异常检测。利用概率混合模型（Student-t分布）建模表示空间中样本与多个簇的关系，并引入可学习的指示函数 δ(x_i) 动态排除异常样本对似然估计的负面影响。
- **关键技术细节**：
  - **似然函数**：  
    `max log p(X|Θ,Φ) = max Σ_i δ(x_i) log Σ_k p(x_i, c_i=k|Θ,Φ)`  
    其中 δ(x_i) 由排序后低似然样本决定（`δ=0` 表示异常）。
  - **分布假设**：采用多元Student-t分布（ν=1）建模样本在嵌入空间中的分布，其重尾性对异常更鲁棒。
  - **异常分数**：自然导数 `o_i = 1 / p(x_i|Θ,Φ)`。进一步受万有引力启发，提出向量求和形式的分数 `o_i^V = 1 / || Σ_k F̃_ik · r̂_ik ||`，其中 `F̃_ik` 类比“力”，`r̂_ik` 为方向向量，能捕捉样本与多个簇之间的复杂关系（样本若被方向相反的多个簇吸引，分数更高）。
  - **迭代优化**：
    - 先根据当前分数剔除比例 l 的异常样本；
    - 使用 EM 算法更新混合模型参数（ω_k, μ_k, Σ_k）；
    - 使用 SGD 优化神经网络参数 Θ（含重建损失作为正则项）。
- **算法流程**：初始化 → 每轮排序异常并去除 → 更新 Θ → EM 更新 Φ → 计算新分数 → 重复至收敛。

## 3. 实验设计
- **数据集**：30 个表格数据集，覆盖 16 个领域（医疗、金融、图像、网络等），全部采用 **自然异常**（非合成），与 ADBench 设置一致。
- **Benchmark**：使用 **inductive setting**（预测新数据），评估指标为 AUC-ROC 和 AUC-PR，报告平均排名（Avg. Rank）。
- **对比方法**：17 种基线，包括：
  - 传统：SOD、HBOS
  - 线性：PCA、OCSVM
  - 密度：LOF、KNN
  - 集成：LODA、IForest
  - 概率：DAGMM、ECOD、COPOD
  - 聚类：DBSCAN、CBLOF、DCOD、KMeans--
  - 表示：DeepSVDD、DIF
- **消融实验**：替换t分布为高斯、去掉似然项、去掉指示函数、比较标量与向量分数。

## 4. 资源与算力
- **文中未明确说明使用的 GPU 型号、数量及训练时长**。仅提到：
  - 使用 Adam 优化器，学习率 1e-4，训练 100 epochs；
  - EM 最大迭代 100 次，容差 1e-3；
  - 运行时间对比中（表2），在 backdoor 数据集上 UniCAD 的 Fit 时间为 246.113 秒，Infer 为 0.079 秒，介于传统方法（如 IForest）和深度方法（如 DAGMM）之间。
- **未提供具体硬件配置**。

## 5. 实验数量与充分性
- **数量**：**30个数据集 × 17个基线 + 消融实验 + 超参数分析 + 运行时间比较**，所有实验重复3次取均值，结果丰富。
- **充分性**：
  - 统计显著性检验：Friedman 检验（p=4.657e-19）及 Nemenyi CD 图，明确显示 UniCAD 向量版本显著优于大部分方法。
  - 消融实验验证了每个模块（t分布、似然项、指示函数）的贡献。
  - 超参数分析（k 和 l）展示了模型对参数具有一定鲁棒性。
  - 实验设计公平：所有方法使用默认或统一超参数，数据集来源公开。
- **客观评价**：尽管在部分数据上不如特定方法（如 IForest 在 http 上更高），但整体平均排名最优，说明泛化能力强。

## 6. 主要结论与发现
- **UniCAD 在 30 个数据集上的平均 AUC-ROC 排名第 1（Avg. Rank 2.6），超越所有 17 个基线**，验证了统一理论框架的有效性。
- **向量求和形式的异常分数显著优于标量分数**（平均排名 2.6 vs 3.7），证明了捕捉多簇间方向关系的优势。
- **消融结果表明**：Student-t 分布优于高斯分布，似然最大化项和指示函数均对性能有正面贡献。
- **模型对超参数 k（簇数）和 l（异常比例）具有一定敏感性**，但存在较优区间（一般情况下 k=10, l=1% 表现良好）。

## 7. 优点
- **理论统一**：首次从概率生成角度将表示学习、聚类和异常检测纳入单一框架，提供了理论支持的异常分数，而非启发式设计。
- **异常抑制机制**：通过指示函数动态剔除异常样本，保护表示学习和聚类免受污染。
- **新颖评分**：受万有引力启发的向量和评分，能区分“夹在多个不同簇之间”的复杂异常模式。
- **实验全面**：30 个数据集、17 个基线、统计检验、消融与调参分析，结果可靠。
- **效率兼顾**：运行时在深度方法中较快，且开源代码，可复现。

## 8. 不足与局限
- **实验范围**：仅针对**表格数据**，未在图像、文本、图数据或序列数据上验证，这些领域的特征可能对混合模型带来不同挑战。
- **超参数依赖**：簇数 k 和异常比例 l 需要人工设定，虽然对一定范围鲁棒，但最佳值仍需针对数据集调优；无自动选择方法。
- **计算复杂度**：迭代优化（神经网络+EM）复杂度为 O(tN(log N + T d(D+K)))，对于大规模超高维数据（如 >1M 样本）可能仍存在可扩展性问题。
- **部分数据集表现欠佳**：如 WPBC、vertebral、landsat 上 AUC 较低，说明模型对某些噪声模式或低分离度数据适应性有限。
- **未分析收敛性**：虽然展示了迭代过程中性能稳定，但对 EM 和网络优化的收敛理论保证未深入讨论。
- **未提及工业级部署**：缺乏对模型鲁棒性（如对抗样本、概念漂移）的讨论。

（完）
