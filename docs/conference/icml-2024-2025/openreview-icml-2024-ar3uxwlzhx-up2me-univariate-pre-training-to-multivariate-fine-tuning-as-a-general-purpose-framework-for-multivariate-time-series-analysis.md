---
title: "UP2ME: Univariate Pre-training to Multivariate Fine-tuning as a General-purpose Framework for Multivariate Time Series Analysis"
title_zh: UP2ME：从单变量预训练到多变量微调的通用多变量时间序列分析框架
authors: "Yunhao Zhang, Minghao Liu, Shengyang Zhou, Junchi Yan"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=aR3uxWlZhX"
tags: ["query:anomaly-id"]
score: 8.0
evidence: 时间序列异常检测通用预训练框架
tldr: UP2ME提出了一种用于多变量时间序列分析的通用预训练框架，采用单变量预训练到多变量微调的范式。该框架在预训练阶段不指定下游任务，支持因果分析、异常检测等多种任务。实验表明，在多个基准上，UP2ME的性能与专为特定任务设计的方法相当甚至更优，为时间序列分析提供了一个强大而通用的基础模型。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-ar3uxwlzhx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ar3uxwlzhx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1595, \"height\": 777, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ar3uxwlzhx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1735, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ar3uxwlzhx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1678, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ar3uxwlzhx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1604, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ar3uxwlzhx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 797, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ar3uxwlzhx/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1592, \"height\": 1959, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ar3uxwlzhx/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1661, \"height\": 1682, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ar3uxwlzhx/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1660, \"height\": 1683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ar3uxwlzhx/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1727, \"height\": 1571, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-ar3uxwlzhx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 412, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ar3uxwlzhx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1769, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ar3uxwlzhx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1763, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ar3uxwlzhx/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1762, \"height\": 432, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ar3uxwlzhx/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1771, \"height\": 1594, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ar3uxwlzhx/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1773, \"height\": 1436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ar3uxwlzhx/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1589, \"height\": 741, \"label\": \"Table\"}]"
motivation: 现有时间序列预训练方法在下游任务中落后于定制方法，且缺乏通用性。
method: 提出单变量预训练到多变量微调范式，通过任务无关预训练和冻结参数微调实现通用性。
result: 在多个时间序列任务上，UP2ME达到或超过定制方法的性能。
conclusion: UP2ME为时间序列分析提供了首个通用预训练框架，支持异常检测等任务。
---

## Abstract
Despite the success of self-supervised pre-training in texts and images, applying it to multivariate time series (MTS) falls behind tailored methods for tasks like forecasting, imputation and anomaly detection. We propose a general-purpose framework, named UP2ME (**U**nivariate **P**re-training to **M**ultivariate Fin**e**-tuning). It conducts task-agnostic pre-training when downstream tasks are unspecified. Once the task and setting (e.g. forecasting length) are determined, it gives sensible solutions with frozen pre-trained parameters, which has not been achieved before. UP2ME is further refined by fine-tuning. A univariate-to-multivariate paradigm is devised to address the heterogeneity of temporal and cross-channel dependencies. In univariate pre-training, univariate instances with diverse lengths are generated for Masked AutoEncoder (MAE) pre-training, discarding cross-channel dependency. The pre-trained model handles downstream tasks by formulating them into specific mask-reconstruction problems. In multivariate fine-tuning, it constructs a dependency graph among channels using the pre-trained encoder to enhance cross-channel dependency capture. Experiments on eight real-world datasets show its SOTA performance in forecasting and imputation, approaching task-specific performance in anomaly detection. Our code is available at https://github.com/Thinklab-SJTU/UP2ME.

---

## 论文详细总结（自动生成）

# UP2ME：从单变量预训练到多变量微调的通用多变量时间序列分析框架 —— 详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：虽然自监督预训练在自然语言处理和计算机视觉领域取得了巨大成功，但在多变量时间序列（MTS）分析中，预训练方法的效果仍落后于针对特定任务（如预测、插补、异常检测）精心设计的定制方法。现有预训练方法大多只能作为模型初始化器，无法在不修改参数或架构的情况下直接执行下游任务，且难以与任务专用方法竞争。
- **整体含义**：本文旨在提出一个**通用框架**，使得同一个预训练模型能够在不调整参数的情况下处理多种MTS任务（即时反应模式），并可通过微调进一步提升精度。该框架首次实现了“任务无关预训练 + 冻结参数直接推理”的能力，弥补了MTS领域通用预训练模型的空白。

## 2. 方法论：核心思想、关键技术细节

### 2.1 核心思想

- **单变量到多变量（Univariate-to-Multivariate）范式**：利用时间依赖与跨通道依赖的异质性，在预训练阶段完全丢弃跨通道依赖，仅聚焦于时间依赖；在微调阶段再引入跨通道依赖。
- **任务无关预训练**：使用掩码自编码器（MAE），生成不同长度的单变量实例，使模型学会重构被掩码的序列，从而具备处理多种下游任务（预测、插补、异常检测）的能力。

### 2.2 关键技术细节

#### （1）单变量预训练（Univariate Pre-training）

- **实例生成**：
  - **可变窗口长度**：预训练时随机采样窗口长度 L = nP（P为补丁大小，n ∈ [N_min, N_max]），以适应下游任务中不同的序列长度需求。
  - **通道解耦**：对每个样本独立采样时间戳 t 和通道索引 c，得到单变量子序列 (X_{t+1:t+L,c}, c)，完全丢弃跨通道依赖。这对于高维数据集（如Traffic有862个通道）可显著降低计算开销。
- **MAE预训练**：
  - 将单变量序列分割为不重叠的补丁（patch），对部分补丁进行随机掩码（掩码比例α=50%）。
  - 使用标准Transformer编码器处理未掩码补丁，解码器重构掩码补丁，损失为MSE。
  - 引入通道嵌入和位置嵌入，以及RevIN归一化。
- **即时反应模式（IR）**：
  - 预训练后，编码器和解码器参数冻结，通过将不同任务构造为特定的掩码-重构问题直接执行：
    - **预测**：将历史序列视为未掩码，未来序列视为掩码。
    - **插补**：将包含缺失值的补丁视为掩码，完整补丁视为未掩码。
    - **异常检测**：逐个掩码每个补丁，用其他补丁重构，以重构误差作为异常分数。

#### （2）多变量微调（Multivariate Fine-tuning）

- **稀疏依赖图构建**：
  - 将多变量实例的每个通道独立输入冻结的编码器，得到潜在标记。
  - 对每个通道进行最大池化得到通道表示，计算余弦相似度矩阵A。
  - 取每个通道的top-k个邻居与top-rC个最大元素的交集作为稀疏图E（r为超参数，设为 min(10, ⌈0.5C⌉)）。
- **时间-通道层（Temporal-Channel Layer）**：
  - 在冻结的编码器和解码器之间插入K个可学习的TC层（实验中K=1）。
  - 每个TC层包含一个标准Transformer层（处理时间依赖）和一个标准图Transformer层（根据稀疏图E处理跨通道依赖）。
  - 计算复杂度为O(CN²)，与通道数C成线性关系，可扩展到高维数据。
- **微调过程**：保持编码器和解码器冻结，仅训练TC层，使用相应任务的损失函数（预测/插补为MSE，异常检测为无监督学习）。

## 3. 实验设计

### 3.1 数据集与场景

- **8个真实世界数据集**：ETTm1（7通道）、Weather（21通道）、Electricity（321通道）、Traffic（862通道）、SMD（38通道）、PSM（25通道）、SWaT（51通道）、GECCO（9通道）。
- **三个下游任务**：预测（4种预测长度）、插补（4种缺失率范围）、异常检测（F1分数和平均精度AP）。

### 3.2 对比方法

- **任务专用方法**：预测任务用PatchTST、DLinear、Crossformer、FEDformer；插补用SAITS、GRIN、线性插值、样条插值；异常检测用DCdetector、AnomalyTrans、iForest、OCSVM。
- **通用方法**：TimesNet。
- **预训练方法**：TS2Vec、SimMTM。
- **本文模式**：UP2ME(IR)（即时反应模式）、UP2ME(FT)（微调模式）。

### 3.3 评估指标

- 预测和插补：均方误差（mSE）和平均绝对误差（mAE）。
- 异常检测：F1分数（选定阈值）和平均精度（AP，无阈值依赖），并使用分段调整策略。

## 4. 资源与算力

- **文中明确说明**：所有深度学习方法使用PyTorch，在**2块NVIDIA GeForce RTX 3090 GPU（24GB显存）** 上运行。
- 预训练最大训练步数500,000步，使用早停（验证损失连续10次不下降则终止）。
- 微调最大20个epoch，早停（3次验证损失不下降）。
- **未明确说明**：具体训练时长（小时数）、总计算量（FLOPs）或能耗等细节。

## 5. 实验数量与充分性

### 5.1 实验数量

- **主要结果**：在8个数据集上，每个任务（预测4种长度、插补4种缺失率、异常检测）均报告平均结果，共生成3张主表（Table 1-3），涵盖大量基线。
- **消融与分析**：
  - 预训练消融（图3a）：移除可变窗口长度、移除通道解耦。
  - 掩码比例影响（图3b）：从10%到90%共9个水平。
  - 图构建方法对比（图3c）：独立、随机、皮尔逊、欧氏距离、全连接。
  - 超参数r的影响（图3d）：从1到21共7个水平，同时报告显存占用。
  - 变长过去窗口（图4b）：120到1440共12个长度。
  - 有限数据场景（图4c）：0%到100%共8个比例。
  - 计算开销分析（附录C）：通道解耦前后显存与速度对比（图5），以及r对显存影响（图6）。
- **可视化**（附录D）：展示多个通道的掩码重构、预测、插补、异常检测案例。

### 5.2 充分性与公平性

- **充分性**：实验覆盖了不同领域、不同维度的数据集，对比了任务专用、通用、预训练三大类方法，并进行了全面的消融研究。IR模式和FT模式均被评估。
- **客观与公平**：采用标准协议进行数据划分和评估（如预测中使用相同的历史窗口搜索策略，异常检测使用统一的分段调整策略）。对比方法的超参数通过网格搜索确定。所有实验重复3次取平均。
- **潜在偏差**：所有模型在同一数据集上预训练和微调，并未进行跨数据集零样本测试（作者指出这是未来工作）。对于异常检测任务，UP2ME(FT)在GECCO上表现优异，但在SMD上F1略低于AnomalyTrans，表明仍存在提升空间。

## 6. 主要结论与发现

1. **通用性**：UP2ME(IR)在预测、插补上可与许多任务专用方法匹敌，甚至超过部分预训练方法，且无需修改参数。这是此前未实现的。
2. **性能提升**：UP2ME(FT)在预测和插补上全面超越所有对比方法（包括任务专用SOTA）；在异常检测中接近或超过任务专用方法（GECCO上大幅领先）。
3. **预训练有效性**：与从头训练相比，预训练+微调显著提升性能；可变窗口长度和通道解耦是关键设计。
4. **图构建合理性**：基于预训练编码器构建的稀疏图能有效捕捉跨通道依赖，接近全连接的理论上限且计算开销小。
5. **数据效率**：在数据有限场景（≤10%训练数据）下，UP2ME(IR)在不微调时即达到最佳性能，展示了良好的迁移能力。

## 7. 优点

- **方法创新**：提出了“单变量预训练→多变量微调”的范式，巧妙分离时间依赖与跨通道依赖，既保证通用性又降低预训练复杂度。
- **即时反应能力**：首次实现不修改参数即可处理多种下游任务，这对于实际部署（无需为每个任务重新训练）具有重大意义。
- **高维可扩展**：通道解耦使预训练复杂度与通道数无关；稀疏图使微调复杂度与通道数线性相关，可扩展到数百通道。
- **实验全面**：覆盖8个数据集、3个任务、多个设置，消融实验深入，对比基线丰富，且提供了可视化案例和计算开销分析。
- **代码开源**：提供了完整的实现代码，便于复现和进一步研究。

## 8. 不足与局限

- **不支持分类**：目前无法在不修改参数的情况下进行时间序列分类（IR模式），限制了适用场景（作者承认这一点）。
- **单数据集预训练**：每个模型仅在单个数据集上预训练，无法像NLP基础模型那样在多数据集上预训练并零样本泛化到未见数据。作者指出“构建跨数据集的基础模型仍是未来开放问题”。
- **异常检测性能仍有差距**：尽管UP2ME(FT)接近任务专用方法，但在SMD等数据集上F1分数仍低于AnomalyTrans（90.98 vs 83.31），说明在特定任务上仍有优化空间。
- **计算资源未详细报告**：缺乏训练总时间、能耗等详细数据，不利于完全复现和比较计算效率。
- **超参数敏感性**：图构建中的r需要针对不同数据集调节（文中设为min(10, ⌈0.5C⌉)），但未提供自动化调优方案。
- **实验局限**：所有实验集中在同一个数据集内，未评估跨数据集迁移能力；对于极长序列（如超720步）的性能未涉及。

（完）
