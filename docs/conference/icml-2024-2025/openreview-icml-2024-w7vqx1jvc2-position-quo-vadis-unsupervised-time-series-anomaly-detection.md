---
title: "Position: Quo Vadis, Unsupervised Time Series Anomaly Detection?"
title_zh: 立场论文：无监督时间序列异常检测何去何从？
authors: "M. Saquib Sarfraz, Mei-Yen Chen, Lukas Layer, Kunyu Peng, Marios Koulakis"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=W7Vqx1Jvc2"
tags: ["query:anomaly-id"]
score: 6.0
evidence: 对时间序列异常检测基准和评估的批判性分析
tldr: 无监督时间序列异常检测研究长期使用有缺陷的评估指标和不一致的基准。本文系统批判了现状，揭示了当前模型设计中的问题，并呼吁转向更严格的基准、非平凡数据集以及简单基线比较。该立场论文为社区提供了重要反思。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-w7vqx1jvc2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1306, \"height\": 557, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-w7vqx1jvc2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 857, \"height\": 777, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-w7vqx1jvc2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 798, \"height\": 418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-w7vqx1jvc2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 815, \"height\": 723, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-w7vqx1jvc2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 816, \"height\": 721, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-w7vqx1jvc2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 799, \"height\": 425, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-w7vqx1jvc2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 844, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-w7vqx1jvc2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1744, \"height\": 616, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-w7vqx1jvc2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1685, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-w7vqx1jvc2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 823, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-w7vqx1jvc2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1680, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-w7vqx1jvc2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1758, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-w7vqx1jvc2/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1714, \"height\": 152, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-w7vqx1jvc2/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 961, \"height\": 434, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-w7vqx1jvc2/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1773, \"height\": 536, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-w7vqx1jvc2/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1770, \"height\": 536, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-w7vqx1jvc2/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1723, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-w7vqx1jvc2/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1723, \"height\": 295, \"label\": \"Table\"}]"
motivation: 时间序列异常检测领域存在评估指标和基准的严重缺陷。
method: 通过系统分析揭示问题，倡导改进评估实践。
result: 指出了当前研究中的误导性实践和改进方向。
conclusion: 应重新审视评估标准，避免追求复杂模型而忽视严谨评估。
---

## Abstract
The current state of machine learning scholarship in Timeseries Anomaly Detection (TAD) is plagued by the persistent use of flawed evaluation metrics, inconsistent benchmarking practices, and a lack of proper justification for the choices made in novel deep learning-based model designs. Our paper presents a critical analysis of the status quo in TAD, revealing the misleading track of current research and highlighting problematic methods, and evaluation practices. ***Our position advocates for a shift in focus from solely pursuing novel model designs to improving benchmarking practices, creating non-trivial datasets, and critically evaluating the utility of complex methods against simpler baselines***. Our findings demonstrate the need for rigorous evaluation protocols, the creation of simple baselines, and the revelation that state-of-the-art deep anomaly detection models effectively learn linear mappings. These findings suggest the need for more exploration and development of simple and interpretable TAD methods. The increment of model complexity in the state-of-the-art deep-learning based models unfortunately offers very little improvement. We offer insights and suggestions for the field to move forward.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：当前无监督时间序列异常检测（TAD）领域存在严重的评估指标缺陷、基准测试不一致以及模型设计缺乏合理依据等问题。许多基于深度学习的最新方法使用了有问题的评价协议（如点调整F1分数）和不合适的基准数据集，导致看似进展实则误导。
- **整体含义**：论文旨在引导TAD社区关注更严格的评估实践、创建非平凡数据集，并批判性地评估复杂方法相对于简单基线的效用。作者通过实验揭示：最先进的深度学习模型实际上学习的是线性映射，模型复杂度的增加几乎未带来性能提升，这挑战了当前研究的主流方向。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：主张回归基础，采用简单、可解释的基线方法，并建立严格评估准则。无需复杂模型即可取得与甚至超越SOTA的结果。
- **关键技术细节（提出的一组简单基线）**：
  - **传感器范围偏差**：检查测试点是否超出训练数据中每个传感器的取值区间。
  - **L2范数**：以测试时间步向量的L2范数作为异常分数。
  - **1-NN距离**：计算每个测试时间步到训练数据的最近邻距离。
  - **PCA重建误差**：对训练数据特征进行PCA降维（前30个或10个主成分），然后计算测试数据投影后的重建误差，等价于线性自编码器。
  - **神经网络基线**：采用最简单的网络结构（1层线性MLP作为自编码器、单块MLP-Mixer、单头Transformer块、1层GCN-LSTM块）训练为预测或重建模式。
- **公式或算法流程**：无新算法，但定义了异常检测任务形式：训练数据仅含正常样本，模型输出异常分数，通过阈值化得到预测标签。使用L∞规范聚合多传感器误差。对于单变量数据，采用滑动窗口（窗口大小w=4）构造特征向量。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - 多元：SWaT（51传感器）、WADI（127传感器及子集112传感器）、SMD（38传感器×28台机器）、SMAP和MSL（NASA数据集，附录中用）。
  - 单变量：UCR/InternalBleeding（4条迹线，分别为IB-16至19）。
- **基准与评估协议**：
  - 使用三种指标：点调整F1（F1_PA，常见但有缺陷）、标准点级F1（F1）、时间序列范围级F1（F1_T，基于Tatbul等人和Wagner等人的定义）。
  - 同时报告AUPRC（附录中）。
- **对比方法**：
  - SOTA深度学习方法：MERLIN、DAGMM、OmniAnomaly、USAD、GDN、TranAD、AnomalyTransformer。
  - 随机预测基线（用作下界）。
  - 自身提出的简单基线（上述5种）及神经网络基线（4种）。
- **实验设置**：所有深度SOTA方法使用原始论文推荐超参数或官方实现；神经网络基线使用统一超参数（学习率0.001，batch size 512，验证集早停）；PCA使用固定主成分数（>50传感器用30，否则10）。

## 4. 资源与算力

- **未明确说明**：论文未提及使用的GPU型号、数量、训练时长或总计算资源消耗。只提到所有模型都在相同机器上训练，但未提供具体配置。因此无法评估算力耗费。

## 5. 实验数量与充分性

- **实验数量**：论文进行了大量实验，覆盖：
  - 3个多元数据集（SWaT、WADI两种版本、SMD）加上附录中2个数据集（SMAP、MSL）。
  - 4个单变量数据集（UCR/IB）。
  - 7种SOTA方法和多种简单基线对比。
  - 消融实验：归一化方法（None vs Mean-STD vs Median-IQR）对性能影响（表5）；PCA投影维度影响（图3）；单变量滑动窗口大小影响（附录图5）；预测模式 vs 重建模式（附录表6）。
  - 线性近似实验：将复杂模型（MLPMixer、Transformer、GCN-LSTM、TranAD、GDN）蒸馏为线性模型，比较性能（表4）。
  - 模型预测一致性分析：计算不同方法在异常区间上的IOU（附录图4）。
- **充分性与客观性**：实验设计较为充分，同时评估了点级和范围级指标，并指出点调整指标的误导性。对比方法使用官方实现或推荐超参数，公平性好。然而，实验仅在有限数据集上进行，且部分数据集（如SWaT）已被指出存在问题，可能影响结论泛化性。

## 6. 论文的主要结论与发现

- **点调整F1指标具有欺骗性**：随机预测在该指标上甚至超过SOTA，导致虚假进步。
- **简单基线优于或匹敌SOTA**：PCA重建误差、1-NN距离等简单方法在所有数据集上取得最佳或次佳性能。
- **复杂深度学习模型可被线性近似**：通过蒸馏，线性模型性能与原模型几乎相同，表明这些模型学到的是线性映射。
- **模型间预测一致性高**：不同方法检测到的异常高度重合，且与真值偏差大，说明当前数据集可能同时包含“太难”和“太易”的异常，缺乏难度梯度。
- **规范化方法和子传感器选择影响大**：WADI数据集因使用不同传感器子集导致性能结果不一致，呼吁应公开完整设置。
- **未来方向**：应放弃点调整指标，采用点级和范围级双重评价；创建更有挑战性的数据集；重视简单可解释基线。

## 7. 优点

- **深刻批判**：系统指出了领域内长期存在的评估和基准问题，具有重要警示意义。
- **提供实用基线**：提出了多个计算简单且效果优异的基线方法，便于社区复现和比较。
- **实验设计严谨**：涵盖多种指标、消融实验和线性近似分析，增强了结论可信度。
- **开放代码**：提供GitHub代码，促进可重复性。

## 8. 不足与局限

- **未提出新方法**：作为立场论文，主要贡献是批判和建议，没有提出创新算法，可能对希望直接应用的读者帮助有限。
- **数据集限制**：部分实验使用的数据集（如SWaT、SMAP、MSL）本身被指出有缺陷，可能影响结论稳健性。论文虽已讨论但仍依赖它们。
- **未评估实际部署场景**：实验使用离线最优阈值（已知测试集标签），未模拟在线阈值选择，AUPRC指标在附录中虽提供，但正文重点在F1。
- **算力消耗未提及**：无法评估复现成本。
- **基线选择范围有限**：未覆盖所有经典方法（如孤立森林、ARIMA等），仅选取了部分。
- **理论分析缺失**：为何复杂模型可被线性近似缺乏理论解释，仅凭实验现象。

（完）
