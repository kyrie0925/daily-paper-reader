---
title: Beyond Individual Input for Deep Anomaly Detection on Tabular Data
title_zh: 超越单个输入：表格数据的深度异常检测
authors: "Hugo Thimonier, Fabrice Popineau, Arpad Rimmel, Bich-Liên DOAN"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=chDpBp2P6b"
tags: ["query:anomaly-id"]
score: 7.0
evidence: 基于Transformer的表格数据异常检测
tldr: 表格数据异常检测难以同时利用特征间和样本间依赖。本文采用非参数Transformer（NPT）在重建框架下训练正常样本的掩码特征重建，推理时利用整个训练集计算异常分数。该方法首次成功结合两种依赖关系，在多个表格基准上超过现有方法。该工作为表格数据异常检测提供了新思路，可推广到海洋表格数据。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-chdpbp2p6b/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1482, \"height\": 561, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-chdpbp2p6b/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1743, \"height\": 594, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-chdpbp2p6b/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1670, \"height\": 792, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-chdpbp2p6b/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 802, \"height\": 501, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-chdpbp2p6b/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 805, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-chdpbp2p6b/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 828, \"height\": 1438, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-chdpbp2p6b/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1172, \"height\": 1438, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-chdpbp2p6b/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1437, \"height\": 1635, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-chdpbp2p6b/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1423, \"height\": 1585, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-chdpbp2p6b/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1750, \"height\": 1635, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-chdpbp2p6b/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1586, \"height\": 1636, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-chdpbp2p6b/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 832, \"height\": 1636, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-chdpbp2p6b/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 823, \"height\": 1637, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-chdpbp2p6b/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1177, \"height\": 1633, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-chdpbp2p6b/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 867, \"height\": 1589, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-chdpbp2p6b/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 794, \"height\": 1429, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-chdpbp2p6b/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1207, \"height\": 618, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-chdpbp2p6b/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 535, \"height\": 1438, \"label\": \"Table\"}]"
motivation: 表格异常检测缺乏同时利用特征相关性和样本相关性的方法。
method: 使用非参数Transformer学习特征和样本依赖，通过掩码重建生成异常分数。
result: 在多个UCI和工业数据集上取得最优结果。
conclusion: 结合两种依赖显著提升表格异常检测能力。
---

## Abstract
Anomaly detection is vital in many domains, such as finance, healthcare, and cybersecurity. In this paper, we propose a novel deep anomaly detection method for tabular data that leverages Non-Parametric Transformers (NPTs), a model initially proposed for supervised tasks, to capture both feature-feature and sample-sample dependencies. In a reconstruction-based framework, we train an NPT to reconstruct masked features of normal samples. In a non-parametric fashion, we leverage the whole training set during inference and use the model's ability to reconstruct the masked features to generate an anomaly score. To the best of our knowledge, this is the first work to successfully combine feature-feature and sample-sample dependencies for anomaly detection on tabular datasets. Through extensive experiments on 31 benchmark tabular datasets, we demonstrate that our method achieves state-of-the-art performance, outperforming existing methods by 2.4% and 1.2% in terms of F1-score and AUROC, respectively. Our ablation study further proves that modeling both types of dependencies is crucial for anomaly detection on tabular data.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题**：表格数据的异常检测（Anomaly Detection, AD）传统方法要么只利用**特征-特征依赖**（如自编码器重建），要么只利用**样本-样本依赖**（如K近邻），但鲜有工作同时结合两者。
- **动机**：已有监督学习（如NPT）表明，同时建模特征间和样本间关系对表格分类/回归任务至关重要。作者假设这些依赖是**类别相关的**，因此用于异常检测时应能区分正常与异常样本——仅在正常样本上学习的依赖模式，对异常样本会失效。
- **意义**：首次在表格数据异常检测中成功融合两种依赖，填补了该领域空白。

## 2. 论文提出的方法论

### 核心思想

采用**重建框架**：训练一个非参数Transformer（NPT）模型来重建被掩码的正常样本特征。推理时，对每个验证样本应用多个随机掩码，利用整个训练集（非参数方式）通过NPT重建掩码特征，重建误差越高则越可能是异常。

### 关键技术细节

- **模型**：Non-Parametric Transformer (NPT)，包含两种自注意力机制：
  - **Attention Between Datapoints (ABD)**：在样本间做多头自注意力，捕捉样本-样本依赖。
  - **Attention Between Attributes (ABA)**：在每个样本内部特征间做多头自注意力，捕捉特征-特征依赖。
  - 交替堆叠ABD和ABA层，外加残差连接、层归一化和前馈网络。
- **训练目标**：随机掩码每个样本的部分特征（masking probability \(p_{mask}\)），训练NPT根据未掩码特征和整个训练集来预测被掩码的特征。损失函数：数值特征用均方误差，分类特征用交叉熵。
- **异常分数公式**：
  \[
  \text{NPT-AD}(z; D_{train}) = \frac{1}{m}\sum_{k=1}^m \mathcal{L}(z^{(k)}; D_{train})
  \]
  其中 \(m\) 为所有可能的确定性掩码个数（最大同时掩码特征数 \(r\)），\(\mathcal{L}\) 是重建损失。
- **推理流程**（对应论文图1）：  
  (a) 对每个验证样本应用掩码 → (b) 将掩码后的验证样本与全部未掩码训练集组成矩阵，输入NPT进行重建 → (c) 计算重建误差 → 对所有掩码重复并取平均得到最终分数。

## 3. 实验设计

### 数据集与场景

- **基准**：31个表格数据集，包括：
  - 经典AD数据集：Arrhythmia, Thyroid。
  - ODDS（Outlier Detection DataSets）中的28个数据集（如Wine, Lympho, Glass, Vertebral, WBC, Ionosphere, Vowels, Letter, Cardio, Musk, Speech, Abalone, Optdigits, Satimage-2, Satellite, Pendigits, Annthyroid, Mnist, Mammography, Shuttle, Mulcross, ForestCover等）。
  - 3个真实世界高维数据集（来自Han et al., 2022）：fraud, campaign, backdoor。
- **场景**：半监督设定——训练集仅含正常样本（或少量污染），验证集包含正常和异常样本，按已有文献标准划分（50%正常样本训练，50%正常+全部异常验证）。

### 对比方法

- **深度方法**：GOAD, DROCC, NeuTraL-AD, Shenkar & Wolf的内部对比学习法（Internal Contrastive），以及Vanilla Transformer（同样用于掩码重建）。
- **非深度方法**：Isolation Forest, KNN, RRCF, COPOD, PIDForest。
- **消融基线**：Mask-KNN（仅依赖样本-样本依赖的KNN插补重建）和Vanilla Transformer（仅依赖特征-特征依赖）。

### 评估指标

- F1-score（↑）和AUROC（↑），20次独立随机种子运行取平均值±标准差，并做5% t检验。

## 4. 资源与算力

- **GPU配置**：4或8块Nvidia V100 16GB/32GB，取决于数据集维度。小/中数据集也可在单GPU上训练。
- **训练时间**：附录表14给出了各数据集训练和推理时长（例如Wine训练63秒，Backdoor训练18396秒）。
- **优化器**：LAMB with β=(0.9,0.999)，外加Lookahead wrapper。
- **学习率调度**：flat-then-anneal（前70%步数恒定，后30%余弦退火至0）。

## 5. 实验数量与充分性

- **主要实验**：31个数据集 × 20次随机种子 = 620次主实验，报告均值、标准差和排名。
- **消融实验**：对比NPT-AD、Vanilla Transformer、Mask-KNN在31个数据集上的F1和AUROC（附录表1、11、13）。
- **训练集污染实验**：合成数据集，11个污染水平（0%~10%），5次运行，对比NPT-AD、Transformer、NeuTraL-AD、GOAD和Shenkar & Wolf。
- **架构变体对比**：DROCC/GOAD/NeuTraL-AD各有3-4种架构变体（附录表8-10），均纳入排名计算。
- **评估公平性**：遵循文献标准（阈值设为预测异常数等于真实异常数），报告均值和标准差，并进行t检验。对比方法结果大多取自原论文或官方代码复现。

**结论**：实验数量充分、覆盖广泛（大小规模、不同特征数、不同异常比例），消融和对比设计合理，结果客观可靠。

## 6. 论文的主要结论与发现

- **性能领先**：NPT-AD在31个数据集上平均F1-score为68.8%，平均AUROC为89.8%，均超过所有对比方法，平均排名最低（F1排名3.1，AUROC排名2.5）。
- **消融验证**：同时利用两种依赖（NPT-AD）显著优于仅用特征的Transformer（F1 56.2）和仅用样本的Mask-KNN（F1 57.5），证明**两种依赖对表格异常检测都至关重要**。
- **污染鲁棒性**：训练集污染低于2%时F1接近最优；低于5%时AUROC接近最优；对高污染（>5%）性能下降明显，但仍优于多数对比方法。
- **低方差**：NPT-AD的均值标准差（F1 2.0，AUROC 0.8）小于大多数对比方法，归因于非参数推理的稳定性。

## 7. 优点

- **创新性**：首个成功结合特征-特征和样本-样本依赖的表格异常检测方法，理论贡献明确。
- **方法简洁有效**：基于掩码重建框架，直接利用NPT捕捉两类依赖，异常分数定义直观。
- **全面实验**：31个数据集、多种对比方法、消融、污染分析、架构变体比较，验证充分。
- **可复现性**：代码开源（GitHub），超参数和实现细节透明。
- **低稳定性方差**：非参数推理方式使得结果在不同随机种子间更稳定，增强了可靠性。

## 8. 不足与局限

- **计算复杂度高**：当特征数d较大时，掩码数量组合爆炸（\(m = \sum_{k=1}^r \binom{d}{k}\)），导致推理时间急剧增加。对大特征数数据集（如Mnist、Backdoor）训练和推理时间较长。
- **高污染下性能下降**：训练集污染超过5%后，F1和AUROC显著下降（特别是F1在10%污染时降至约50%），且由于NPT在推理时也依赖训练集，污染有双重影响（训练和推理均受影响）。
- **依赖NPT结构**：目前仅能使用NPT作为骨架，限制了自监督预训练任务的灵活选择（其他检索方法可能更优）。
- **未测试超大规模数据集**：尽管包含了ForestCover（28万样本），但未在更大规模（百万级以上）或极稀疏数据集上验证。
- **特征数受限**：当d极大时（如图像展平），注意力机制的内存和时间开销可能不切实际，论文未具体讨论此场景。

（完）
