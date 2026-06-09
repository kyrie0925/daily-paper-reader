---
title: "ODIM: Outlier Detection via Likelihood of Under-Fitted Generative Models"
title_zh: "ODIM: 基于欠拟合生成模型似然的异常检测"
authors: "Dongha Kim, JaesungHwang, Jongjin Lee, Kunwoong Kim, Yongdai Kim"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=R8nbccD7kv"
tags: ["query:anomaly-id"]
score: 9.0
evidence: 利用欠拟合生成模型似然进行异常检测
tldr: 无监督异常检测中，全训练似然模型表现不佳。本文发现欠拟合生成模型会先记忆正常样本，据此提出ODIM方法，利用欠拟合似然做异常检测。实验证明该方法在多种数据集上优于现有方法，揭示了利用模型欠拟合进行异常检测的新范式。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-r8nbccd7kv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 877, \"height\": 226, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-r8nbccd7kv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1745, \"height\": 273, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-r8nbccd7kv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 751, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-r8nbccd7kv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1720, \"height\": 263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-r8nbccd7kv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1426, \"height\": 328, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 862, \"height\": 102, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 865, \"height\": 104, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 864, \"height\": 103, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 815, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 650, \"height\": 83, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 530, \"height\": 92, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1094, \"height\": 1762, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1772, \"height\": 1248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1415, \"height\": 1507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1761, \"height\": 1254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1417, \"height\": 1534, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1683, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1243, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1674, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1242, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1745, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1243, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1743, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1241, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1315, \"height\": 388, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1151, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1066, \"height\": 378, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1275, \"height\": 512, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 693, \"height\": 1214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 885, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 677, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 909, \"height\": 502, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-r8nbccd7kv/table-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 891, \"height\": 503, \"label\": \"Table\"}]"
motivation: 现有全训练似然模型在无监督异常检测中表现差，本文观察到先记忆正常样本的欠拟合效应可解决该问题。
method: 提出ODIM，通过精心控制的欠拟合训练，利用生成模型似然作为异常分数，区分正常与异常样本。
result: 在多个基准数据集上，ODIM优于现有无监督异常检测方法，验证了欠拟合似然的有效性。
conclusion: 欠拟合似然是一种有效的无监督异常检测信号，为异常检测提供了新思路。
---

## Abstract
The unsupervised outlier detection (UOD) problem refers to a task to identify inliers given training data which contain outliers as well as inliers, without any labeled information about inliers and outliers. It has been widely recognized that using fully-trained likelihood-based deep generative models (DGMs) often results in poor performance in distinguishing inliers from outliers. In this study, we claim that the likelihood itself could serve as powerful evidence for identifying inliers in UOD tasks, provided that DGMs are carefully under-fitted. Our approach begins with a novel observation called the inlier-memorization (IM) effect--when training a deep generative model with data including outliers, the model initially memorizes inliers before outliers. Based on this finding, we develop a new method called the outlier detection via the IM effect (ODIM). Remarkably, the ODIM requires only a few updates, making it computationally efficient--at least tens of times faster than other deep-learning-based algorithms. Also, the ODIM filters out outliers excellently, regardless of the data type, including tabular, image, and text data. To validate the superiority and efficiency of our method, we provide extensive empirical analyses on close to 60 datasets.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）
- **问题定义**：无监督异常检测（UOD）任务要求在没有标签信息的情况下，从包含正常样本（inliers）和异常样本（outliers）的训练数据中识别出正常样本。
- **现有困境**：广泛使用的基于似然的深度生成模型（DGM）在完全训练后，其似然值无法有效区分正常与异常样本（例如在OOD任务中，异常样本的似然值反而更高）。
- **核心洞察**：本文发现，若对DGM进行精心控制的**欠拟合**训练，其似然值反而能成为强有力的异常检测信号。关键在于一个新颖现象——“正常样本记忆效应”（Inlier-Memorization Effect, IM effect）：当训练数据包含异常时，模型在早期训练阶段会先记忆正常样本，之后再记忆异常样本。
- **整体贡献**：基于IM效应，提出ODIM方法，实现高效、跨数据类型的无监督异常检测。

## 2. 方法论：核心思想、关键技术细节与算法流程
### 2.1 核心思想
利用深度生成模型（如VAE、IWAE）在训练早期呈现的IM效应：正常样本的损失值比异常样本下降得更快。因此，在模型恰好处于“欠拟合但已初步记忆正常样本”的阶段，用每个样本的损失值（负对数似然的下界）作为异常分数——损失值大的样本更可能是异常。

### 2.2 关键技术细节
- **基础模型**：采用重要性加权自编码器（IWAE），因其对似然的估计更紧，能更清晰地体现IM效应（K=50）。
- **预处理器**：使用**Min-Max缩放**（将每个特征归一化到[0,1]），而非标准化。理论（Proposition 3.4）和实验均表明，Min-Max缩放能使正常与异常样本的l1范数更接近，从而强化IM效应。
- **自适应停止策略**：在每个更新步，对当前所有样本的损失值拟合一个双组分高斯混合模型（GMM-2），用**Wasserstein距离**衡量两个高斯分布的分离程度。当Wasserstein距离达到最大且连续`Npat`次未改进时停止训练，并取该时刻的模型作为最优欠拟合模型。超参数：`Nu=10`（每10步评估一次），`Npat=10`。
- **集成策略**：用B=10个不同随机初始化的模型独立训练，取每个样本的损失均值作为最终ODIM分数，以稳定结果。

### 2.3 算法流程（文字描述）
1. 对原始数据做Min-Max缩放。
2. 并行训练B个IWAE模型（B=10），每个模型独立初始化。
3. 对每个模型，迭代更新（使用Adam，学习率5e-4，batch size 128）：
   - 每`Nu`步计算当前所有样本的IWAE损失值，归一化后拟合GMM-2，计算Wasserstein距离。
   - 若当前距离大于历史最优，则更新最优模型并重置早停计数器；否则计数器+1；若计数器达到`Npat`，停止该模型的训练。
4. 对每个样本，计算B个最优模型下IWAE损失的平均值作为ODIM分数。
5. 输出分数：分数高 → 异常；分数低 → 正常。

## 3. 实验设计
### 3.1 使用的数据集与场景
- **来源**：ADBench基准库，共57个数据集。
- **类别**：
  - **表格数据（36个）**：涵盖医疗、金融、天文学等领域（如Cardio, Cover, Thyroid, Fraud等）。
  - **图像数据（6个）**：MNIST, MNIST-C, FMNIST, CIFAR10, SVHN, MVTec-AD（使用ViT提取的特征向量）。
  - **文本数据（5个）**：Amazon, 20news, Agnews, Imdb, Yelp（使用BERT/RoBERTa嵌入）。
- **额外场景**：
  - 部分标注异常（半监督）：在训练集外给出少量标注的异常样本。
  - 差分隐私：将DP-SGD应用于ODIM，对比DeepSVDD。

### 3.2 Benchmark与对比方法
- **传统方法**：PCA, OCSVM, LOF, IForest, kNN, COPOD, ECOD等（共16种，来自ADBench）。
- **深度学习UOD方法**：DeepSVDD, DAGMM, DROCC, GOAD, ICL, DTE, DDPM（基于扩散模型）等。
- **所有基线结果**直接引用自Livernoche et al. (2023)的附录，保证公平对比。

## 4. 资源与算力
论文明确说明使用**单张NVIDIA TITAN XP GPU**，基于PyTorch框架运行。未给出具体训练时长或GPU数量，但强调ODIM仅需很少的更新（通常少于1个epoch），因此计算效率极高——比深度学习基线方法快数十倍。运行时间对比表（Table 4）展示了ODIM在多个大型数据集上的秒级运行时间，远快于DeepSVDD（需数百秒）。

## 5. 实验数量与充分性
- **主实验**：在46个表格数据集、6个图像数据集、5个文本数据集上进行了训练集上的异常检测性能测试，报告了AUC和PR分数。所有结果均为5次随机初始化的平均值。
- **消融实验**：
  - IWAE采样数K（1~100）：显示K≥50时性能饱和。
  - 早停耐心Npat（1~15）：Npat≥10后性能饱和。
  - 集成模型数量B（1~20）：B越大效果越好，但B=10后提升有限。
  - 学习率（1e-4~0.1）：在合理范围内（≤1e-2）表现稳定。
  - 预处理器比较：Min-Max vs 标准化（30个表格数据集），Min-Max更优。
- **扩展实验**：
  - 半监督（部分标注异常）：在6个表格数据集上，标注比例0.3和0.5均大幅提升性能。
  - 差分隐私（DP-SGD）：在4个表格数据集上，ODIM+DP-SGD的AUC明显高于DeepSVDD+DP-SGD。
- **运行时间对比**：在8个数据集上比较ODIM与OCSVM, LOF, IForest, DeepSVDD，ODIM速度极快。
- **充分性**：实验覆盖多种数据类型、大量基线、关键超参数调优、扩展场景，且结果以平均和细节表格呈现，客观充分。但所有基线结果来自第三方文献，可能未完全复现，但已尽力保证公平。

## 6. 主要结论与发现
1. **IM效应**：深度生成模型在训练早期会优先记忆正常样本，该效应可用于无监督异常检测。
2. **ODIM方法有效**：在所有三类数据（表格、图像、文本）上，ODIM的AUC和PR均**超过或持平所有基线方法**，尤其在图像数据上提升显著（AUC 0.813 vs. 次优0.757）。
3. **计算效率极高**：所需训练更新极少（通常少于1个epoch），比任何深度学习UOD方法都快数十倍。
4. **通用性**：无需特定数据领域的伪标签策略，直接使用似然值，可插拔地应用于各类数据。
5. **扩展性好**：能自然融入半监督和差分隐私场景。

## 7. 优点
- **创新性**：首次将“记忆效应”从有监督分类问题（噪声标签）推广到生成模型的无监督异常检测，并理论分析了梯度与输入范数的关系（Proposition 3.1）。
- **简单有效**：算法仅需少量训练步，避免了深度模型的全训练开销。
- **跨领域普适性**：在表格、图像、文本数据集上均表现优异，无需领域定制。
- **自适应停止策略**：基于Wasserstein距离自动选择最优欠拟合点，避免了手动调参。
- **理论支撑**：提供了预处理器选择的理论（Proposition 3.4）和初始梯度方向的分析（Proposition 3.1）。
- **开源代码**：代码公开可复现。

## 8. 不足与局限
- **预处理器依赖**：方法性能受预处理器选择影响较大（Min-Max优于标准化），但未给出理论上最优的预处理器，仅依赖经验。
- **理论深度有限**：对IM效应在训练持续阶段的解释主要靠直觉和简单线性模型分析，缺少对复杂深层网络下IM效应机制的完整理论证明。
- **基线对比来源**：所有基线结果引用自先前论文附录，可能因实验设定（如数据划分、随机种子）细微差异导致不完全公平，但作者已尽力确保一致。
- **图像与文本数据的特征依赖**：在图像和文本上使用的是预训练模型（ViT/BERT）提取的特征，而非原始像素/文本，ODIM对这些特征的依赖性未被深入探讨。
- **异常比例假设**：实验数据集大多异常比例较小（<10%），未系统评估异常比例极高时方法的鲁棒性。
- **应用限制**：需在训练过程中多次计算Wasserstein距离（每10步），可能在大规模数据上增加少许开销，但仍远优于全训练方法。

（完）
