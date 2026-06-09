---
title: Leveraging Diffusion Model as Pseudo-Anomalous Graph Generator for Graph-Level Anomaly Detection
title_zh: 利用扩散模型作为伪异常图生成器进行图级别异常检测
authors: "Jinyu Cai, Yunhe Zhang, Fusheng Liu, See-Kiong Ng"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Zm2M92TZyO"
tags: ["query:anomaly-id"]
score: 7.0
evidence: 提出了基于扩散模型的伪异常图生成方法用于异常检测
tldr: 针对图级别异常检测中异常样本稀缺的问题，提出AGDiff框架，利用潜扩散模型在图表征中引入微妙扰动生成逼真的伪异常图，通过联合训练分类器增强检测鲁棒性。该方法为异常检测提供了一种有效的数据增强策略。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-zm2m92tzyo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1645, \"height\": 926, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zm2m92tzyo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 758, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zm2m92tzyo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 717, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zm2m92tzyo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1591, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zm2m92tzyo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1592, \"height\": 838, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zm2m92tzyo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1569, \"height\": 886, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-zm2m92tzyo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1773, \"height\": 642, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zm2m92tzyo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1773, \"height\": 447, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zm2m92tzyo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 852, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zm2m92tzyo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1763, \"height\": 404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zm2m92tzyo/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1672, \"height\": 294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zm2m92tzyo/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1674, \"height\": 294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zm2m92tzyo/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1202, \"height\": 186, \"label\": \"Table\"}]"
motivation: 图级别异常检测面临异常样本稀缺的挑战，现有方法难以学习鲁棒检测模型。
method: 提出AGDiff框架，采用潜扩散模型对正常图表征添加微小扰动生成伪异常图，并与分类器联合训练。
result: 在多个基准数据集上，AGDiff显著提升了图级别异常检测的性能。
conclusion: 扩散模型可作为有效的数据增强工具，缓解异常检测中的样本不平衡问题。
---

## Abstract
A fundamental challenge in graph-level anomaly detection (GLAD) is the scarcity of anomalous graph data, as the training dataset typically contains only normal graphs or very few anomalies. This imbalance hinders the development of robust detection models. In this paper, we propose **A**nomalous **G**raph **Diff**usion (AGDiff), a framework that explores the potential of diffusion models in generating pseudo-anomalous graphs for GLAD. Unlike existing diffusion-based methods that focus on modeling data normality, AGDiff leverages the latent diffusion framework to incorporate subtle perturbations into graph representations, thereby generating pseudo-anomalous graphs that closely resemble normal ones. By jointly training a classifier to distinguish these generated graph anomalies from normal graphs, AGDiff learns more discriminative decision boundaries. The shift from solely modeling normality to explicitly generating and learning from pseudo graph anomalies enables AGDiff to effectively identify complex anomalous patterns that other approaches might overlook. Comprehensive experimental results demonstrate that the proposed AGDiff significantly outperforms several state-of-the-art GLAD baselines.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：图级别异常检测（GLAD）面临**异常样本极度稀缺**的挑战，训练集通常只包含正常图或极少量的异常图。这种数据不平衡导致模型难以学习鲁棒的决策边界，尤其难以识别那些与正常图边界模糊的细微异常。
- **研究动机**：现有方法要么仅建模正常分布（无监督），要么依赖有限的标签异常（半监督），但均受限于异常样本的多样性和可获取性。作者希望利用生成模型主动生成“伪异常图”，从而为检测器提供显式的监督信号，增强其对复杂异常模式的识别能力。
- **整体意义**：提出 AGDiff 框架，首次将**扩散模型**用于图级别异常检测的数据增强，通过生成逼真的伪异常图来缓解数据稀缺问题，为GLAD提供了一种新的生成式学习范式。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：利用潜扩散模型在正常图的潜在表示中引入**可控的微小扰动**，生成与正常图高度相似但存在微妙偏差的伪异常图；然后与一个图神经网络（GNN）分类器联合训练，使分类器能更好地区分正常与异常。
- **关键技术细节**：
  1. **预训练阶段**：使用变分图自编码器（VGAE）对正常图进行重构学习，得到结构化的潜在空间，该空间能够捕捉正常图的分布特性。
  2. **条件潜扩散过程**：
     - 在潜在空间上执行前向扩散，逐步添加高斯噪声。
     - 设计一个**可学习的扰动条件向量** \( c = \tau_\omega(z_0) \)：对初始潜在表示 \( z_0 \) 添加噪声 \( \eta \) 并经过MLP变换，作为反向去噪过程中的条件，以引导生成偏离正常但保持结构的伪异常表示。
     - 反向去噪网络 \( \epsilon_\theta(z_t, t, c) \) 接收条件 \( c \)，从而生成受控的扰动潜在表示 \( \tilde{z}_0 \)。
  3. **解码与分类器联合训练**：
     - 将生成的伪异常潜在表示 \( \tilde{z}_0 \) 解码为伪异常图 \( \tilde{G} \)。
     - 使用一个基于GIN的分类器 \( h_\phi \) 对正常图 \( G \) 和伪异常图 \( \tilde{G} \) 进行二分类（正常为1，伪异常为0）。
     - 总损失 \( \mathcal{L} = \mathcal{L}_{\text{cls}} + \lambda \mathcal{L}_{\text{diff}} \)，同时优化分类器和扩散模型。
  4. **推理阶段**：直接用训练好的分类器 \( h_\phi \) 对测试图计算异常分数。
- **算法流程**（文本说明）：
  1. 预训练图表示模型（VGAE）。
  2. 冻结预训练编码器，初始化扩散模型和分类器。
  3. 每轮迭代：采样正常图 → 获取潜在表示 \( Z \) → 前向扩散 → 计算条件向量 → 反向去噪得到伪异常潜在表示 → 解码得到伪异常图 → 分类器输出分数 → 联合更新参数。
  4. 返回训练好的分类器用于测试。

## 3. 实验设计
- **数据集**：共8个，分为两类：
  - **中等规模**：MUTAG、DD、COX2、ER_MD（分子图或生物网络）。
  - **大规模不平衡**：SW-620、MOLT-4、PC-3、MCF-7（抗癌活性化合物，异常比例约25-30%）。
- **基准与对比方法**：
  - 图核方法：SP、WL、NH、RW。
  - GNN方法：OCGIN、OCGTL、GLocalKD、iGAD、SIGNET、MUSE、DO2HSC。
- **评估指标**：AUC和F1-Score，均报告10次独立运行的平均值和标准差。

## 4. 资源与算力
- 论文附录 C 中明确说明：所有实验在 **NVIDIA Tesla H100 GPU (80GB)** 上进行，CPU 为 Intel Xeon Platinum 8480CL。
- 未明确说明使用的 GPU 数量、训练总时长等详细算力信息。仅提及预训练100轮，联合训练200轮，批大小依数据集规模而定（中等16，大512）。

## 5. 实验数量与充分性
- **实验数量**：非常充分。
  - 8个数据集上的完整性能对比（表1、表2）。
  - 评分分布分析（图2）、参数敏感性分析（λ、噪声幅度η、扩散步数T）。
  - 消融实验：去除预训练、去除条件、去除潜扩散（表3）。
  - 可视化：t-SNE 嵌入对比、生成图结构对比、理论分析（附录A）。  
  - 额外分析：不同异常比例r的影响、算法分析实验等。
- **充分性与客观性**：
  - 所有方法均使用官方代码复现或统一平台运行，数据分割策略一致。
  - 多次独立运行（10次）并报告均值与标准差，结果可靠。
  - 消融实验系统性地验证了每个组件的贡献。
  - 但部分基线（如MUSE）在大数据集上结果为N/A，可能由于内存限制，不影响整体公平性。

## 6. 主要结论与发现
- AGDiff 在所有8个数据集上均**显著优于**所有对比方法，包括半监督方法iGAD（尽管AGDiff为无监督方法）。
- 生成伪异常图的策略有效：使检测器学习到更精细的决策边界，尤其在细微异常和大规模不平衡场景下表现突出。
- 消融实验证明，预训练、条件向量和潜扩散模块均为关键组件，缺失任何一个都会导致性能大幅下降。
- 参数分析表明，适度噪声幅度、平衡的伪异常图数量（与正常图相等）以及合适的扩散步数对最佳性能至关重要。
- 理论分析（附录A）和实证分析表明，基于伪异常图的分类策略优于传统的重构式异常检测。

## 7. 优点
- **方法创新**：首次将扩散模型作为伪异常图生成器用于GLAD，不同于以往仅用扩散模型建模正常分布。
- **生成质量高**：通过可学习的条件扰动机理，生成的伪异常图既接近正常图又具有可辨识的细微偏差，有效增强分类器。
- **联合训练机制**：生成器与检测器互相促进，检测器梯度反馈引导生成更难的伪异常，形成迭代优化。
- **理论支撑**：提供了算法分析（附录A）证明伪异常图辅助分类的优越性。
- **实验全面**：多数据集、多基线、多视角分析（性能、分布、可视化、参数），且结果复现规范。

## 8. 不足与局限
- **假设强**：依赖“正常图分布充分代表”的假设，在数据分布漂移或高度异质的环境中可能失效。
- **仅限静态图**：当前框架无法处理动态图或时变图。
- **计算资源消耗较大**：需要预训练、潜扩散过程（T=1000步），且需联合训练全模型，对于大规模图数据集可能时间开销较高（文中未直接报告训练时长）。
- **生成图质量评估不够精细**：仅用拉普拉斯谱距离粗略衡量，缺乏对语义保真度的系统分析。
- **实验偏差风险**：所有数据集均为生物/化学分子图，未涉及社交网络、交通图等其他领域，泛化性有待进一步验证。

（完）
