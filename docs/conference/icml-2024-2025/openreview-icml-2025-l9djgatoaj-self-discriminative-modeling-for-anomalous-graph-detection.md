---
title: Self-Discriminative Modeling for Anomalous Graph Detection
title_zh: 自判别建模用于异常图检测
authors: "Jinyu Cai, Yunhe Zhang, Jicong Fan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=l9DJGAtoAj"
tags: ["query:anomaly-id"]
score: 6.0
evidence: 图数据上的自判别建模用于异常检测
tldr: 图异常检测在实际中很重要，但异常样本通常稀缺。本文提出自判别建模（SDM）框架，仅用正常图训练深度网络。网络同时学习从正常图构造伪异常图以及识别这些伪异常图的检测器，从而建立可靠决策边界。实验表明，SDM在分子图和社会网络图异常检测中均取得优异性能，为无监督图异常检测提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-l9djgatoaj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-l9djgatoaj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1712, \"height\": 717, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-l9djgatoaj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 847, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-l9djgatoaj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 847, \"height\": 496, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-l9djgatoaj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1760, \"height\": 972, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-l9djgatoaj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 881, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-l9djgatoaj/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1569, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-l9djgatoaj/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1571, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-l9djgatoaj/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1574, \"height\": 720, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-l9djgatoaj/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1571, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-l9djgatoaj/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1556, \"height\": 871, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-l9djgatoaj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 1065, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-l9djgatoaj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 773, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-l9djgatoaj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1775, \"height\": 595, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-l9djgatoaj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1768, \"height\": 657, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-l9djgatoaj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 795, \"height\": 434, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-l9djgatoaj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1772, \"height\": 1408, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-l9djgatoaj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1268, \"height\": 400, \"label\": \"Table\"}]"
motivation: 异常图样本稀缺，仅用正常图检测时边界不清晰。
method: 自我判别建模框架，从正常图生成伪异常图，同时学习检测器。
result: 在多个图数据集上实现了可靠的异常检测。
conclusion: 生成的伪异常图有助于建立可靠决策边界。
---

## Abstract
Identifying anomalous graphs is essential in real-world scenarios such as molecular and social network analysis, yet anomalous samples are generally scarce and unavailable. This paper proposes a Self-Discriminative Modeling (SDM) framework that trains a deep neural network only on normal graphs to detect anomalous graphs. The neural network simultaneously learns to construct pseudo-anomalous graphs from normal graphs and learns an anomaly detector to recognize these pseudo-anomalous graphs. As a result, these pseudo-anomalous graphs interpolate between normal graphs and real anomalous graphs, which leads to a reliable decision boundary of anomaly detection. In this framework, we develop three algorithms with different computational efficiencies and stabilities for anomalous graph detection. Extensive experiments on 12 different graph benchmarks demonstrated that the three variants of SDM consistently outperform the state-of-the-art GLAD baselines. The success of our methods stems from the integration of the discriminative classifier and the well-posed pseudo-anomalous graphs, which provided new insights for graph-level anomaly detection.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究动机**：图级异常检测（GLAD）在分子、生物学、社交网络等实际应用中至关重要，但异常样本通常稀缺且难以获取。现有方法依赖强假设（如 hypersphere 分布）或需要显式定义异常分数，半监督方法受限于标注异常样本的多样性。
- **核心问题**：如何在仅使用正常图数据（ unsupervised 设置）的条件下，学习可靠的决策边界以检测未知异常图。
- **整体含义**：本文提出自判别建模（Self-Discriminative Modeling, SDM）框架，通过从正常图自身生成“伪异常图”，使检测器能够区分正常与异常模式，从而在无监督场景下取得与有监督方法相当甚至更优的性能，为 GLAD 提供了新思路。

### 2. 方法论

- **核心思想**：同时训练一个生成器 \(g_\phi\) 和一个判别器/分类器 \(f_\theta\)。生成器从正常图构造伪异常图 \(\tilde{G}\)，要求这些伪异常图“插值”于正常图与真实异常图之间；分类器则学习区分正常图和伪异常图。通过最小化联合损失，使决策边界紧致包围正常数据。
- **关键技术细节**：
  - **SDM-ATI**：基于 GAN 的方法。生成器为 MLP，从随机噪声 \(\tilde{Z} \sim \mathcal{N}(0,1)\) 生成节点属性 \(\tilde{X}\) 和邻接矩阵 \(\tilde{A}\)；判别器为 GIN（图同构网络），区分正常图与生成图。优化目标为 min-max 对抗损失（式(9)）。
  - **SDM-ATII**：基于 VGAE 的对抗变体。生成器包含节点生成器和边生成器，以正常图 \(\mathbf{G}\) 作为输入，通过 GIN 编码为隐变量 \(Z_G\)（服从高斯分布，使用重参数化技巧），再解码得到伪异常图的节点属性与邻接矩阵。损失函数包括对抗损失、重构损失（式(14)）和 KL 散度正则项（式(15)）。
  - **SDM-NAT**：非对抗变体。去除对抗训练，直接使用分类器 \(f_\theta\) 对正常图和生成图进行二分类（正常标签为 1，伪异常标签为 0），联合优化生成器和分类器（式(16)）。损失同样包含重构损失和 KL 散度。
- **公式/算法流程**：详细训练步骤见附录 Algorithms 1–3。核心是交替更新生成器与判别器（ATI/ATII）或联合更新（NAT），使用 RMSprop/Adam 优化器，学习率 0.001，训练 300 epoch。

### 3. 实验设计

- **数据集**：共 12 个图基准，分为三类：
  - 小/中等规模分子、生物学、社交网络：PROTEINS, DD, ENZYMES, IMDB-BINARY, ER MD, MUTAG, AIDS, COX2。
  - 大规模不平衡分子：SW-620, MOLT-4, PC-3, MCF-7（异常比例为 5.95%–9.34%）。
- **评估场景**：
  - 一类分类（One-class GLAD）：将每个类别依次作为正常类，其余为异常。
  - 多类异常检测（Multi-class GLAD）：将 ENZYMES 中 {0,1,2,3} 视为正常，{4,5} 视为异常。
  - 大规模不平衡 GLAD：将少类样本视为异常。
- **对比方法**：
  - 图核：SP, WL, NH, RW（与 OCSVM 结合）。
  - 基于 GNN 的 GLAD：VGAE-AD, OCGIN, GLocalKD, OCGTL, SIGNET, MUSE, DO2HSC 等。
  - 监督方法：GCN, GIN, SOPOOL, RWGNN, iGAD（仅用于不平衡场景）。
- **评估指标**：AUC 和 F1-Score，均报告 10 次重复实验的均值和标准差。

### 4. 资源与算力

- 文中仅说明：所有实验运行于 **NVIDIA Tesla A100 GPU**（搭配 AMD EPYC 7532 CPU），使用 PyTorch Geometric 实现。**未明确给出 GPU 数量、训练耗时或总计算量**。推测为单卡训练，因数据集规模适中（最大 40k 图），训练时间应在数小时内。

### 5. 实验数量与充分性

- **实验组数**：涵盖 8 个中小型数据集 × 每个数据集的多个类别（通常 2 类）、4 个大尺度不平衡数据集、1 个多类场景；另外包含：
  - 模拟分析（2D 合成数据验证决策边界，图3）。
  - 可视图嵌入可视化（t-SNE，图7-8）。
  - 参数敏感性分析（λ, γ 在 [1e-3, 1e2] 范围内变化，图9-10）。
  - 生成器 backbone 消融（VGAE vs. GIN，图11）。
  - 鲁棒性测试（数据污染 0%–30%，表7）。
- **充分性与公平性**：实验覆盖多种数据类型和异常比例，对比了 15+ 种先进方法，且所有 GNN 基线使用相同的 GIN backbone，确保了公平性。消融和参数分析验证了设计选择。整体实验充分、客观，结论有说服力。

### 6. 主要结论与发现

- **三个 SDM 变体均一致优于所有对比方法**，尤其在类不平衡和数据污染场景下优势显著。
- **SDM-NAT 表现最佳且最稳定**（14/14 数据集标准差 ≤5%），避免了 GAN 的不稳定问题。
- **生成的伪异常图能够有效包围正常数据**，学习到紧致的决策边界，可视化结果验证了这一特性。
- **无监督方法超越了部分半监督/监督方法**（如 iGAD），体现了 SDM 在缺乏标签时的强大泛化能力。

### 7. 优点

- **方法创新**：通过自判别生成伪异常图，避免了对数据分布形状的假设，提高了适用范围。
- **三个变体**：兼顾不同需求（ATI 简单、ATII 具可解释性、NAT 稳定精准），并提供详细训练流程。
- **实验全面**：涉及多种图类型、异常比例，以及鲁棒性、参数灵敏度等验证，结果可靠。
- **可视化突出**：t-SNE 分布图和模拟分析直观展示了决策边界的学习过程。
- **代码开源**：便于复现和后续研究。

### 8. 不足与局限

- **未利用可用异常样本**：作者自承未在训练阶段使用任何真实异常图，这在某些场景下可能不是最优（若少量异常可获取）。
- **算力开销未详述**：未报告训练时间或 GPU 总耗时，难以评估大规模部署成本。
- **超参数敏感范围有限**：尽管参数分析显示在 [1e-3, 1e2] 内性能稳定，但未测试极端值或更多场景。
- **实验未涵盖节点/边级别异常检测**：仅针对图级异常，泛化性未验证。
- **潜在偏差风险**：数据集来自 TUDataset，类别相对简单；未在真实工业级大规模图上测试（如 DGraph 金融图）。
- **应用限制**：分子/生物图可能受限于特定领域特征，方法在图像或文本图数据上的效果未讨论。

（完）
