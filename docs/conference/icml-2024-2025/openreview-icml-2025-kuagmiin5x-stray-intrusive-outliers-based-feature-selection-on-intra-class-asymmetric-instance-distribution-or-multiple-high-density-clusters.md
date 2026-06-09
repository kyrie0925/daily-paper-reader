---
title: Stray Intrusive Outliers-Based Feature Selection on Intra-Class Asymmetric Instance Distribution or Multiple High-Density Clusters
title_zh: 基于流浪侵入离群值的特征选择：应对类内不对称分布或多高密聚类
authors: "Lixin Yuan, Yirui Wu, Wenxiao Zhang, Minglei Yuan, Jun Liu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=kUagmiIN5x"
tags: ["query:anomaly-id"]
score: 6.0
evidence: 提出了基于流浪侵入离群值的特征选择方法
tldr: 针对具有类内不对称分布或高密聚类的数据，提出SIOFS特征选择方法。通过识别流浪侵入离群点，修改偏度系数并融合3σ原则确定类主体，基于离群点侵入程度评分特征。在分类任务中有效提升特征选择效果。
source: ICML-2025-Accepted
selection_source: conference_retrieval
motivation: 现有特征选择方法难以处理类内不对称分布或多高密聚类数据中的真实离群点。
method: 提出SIOFS，通过修改偏度系数和3σ原则识别流浪侵入离群点，并基于侵入程度进行特征评分。
result: 在多个分类数据集上，SIOFS相比基线方法显著提升了分类准确率。
conclusion: 关注流浪侵入离群点可有效指导特征选择，适用于复杂分布数据。
---

## Abstract
For data with intra-class Asymmetric instance Distribution or Multiple High-density Clusters (ADMHC), outliers are real and have specific patterns for data classification, where the class body is necessary and difficult to identify. Previous Feature Selection (FS) methods score features based on all training instances or rarely target intra-class ADMHC. In this paper, we propose a supervised FS method, Stray Intrusive Outliers-based FS (SIOFS), for data classification with intra-class ADMHC. By focusing on Stray Intrusive Outliers (SIOs), SIOFS modifies the skewness coefficient and fuses the threshold in the 3$\sigma$ principle to identify the class body, scoring features based on the intrusion degree of SIOs. In addition, the refined density-mean center is proposed to represent the general characteristics of the class body reasonably. Mathematical formulations, proofs, and logical exposition ensure the rationality and universality of the settings in the proposed SIOFS method. Extensive experiments on 16 diverse benchmark datasets demonstrate the superiority of SIOFS over 12 state-of-the-art FS methods in terms of classification accuracy, normalized mutual information, and confusion matrix. SIOFS source codes is available at https://github.com/XXXly/2025-ICML-SIOFS

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机与背景）

- **核心问题**：在类内呈现不对称实例分布或多高密度聚类（ADMHC）的高维数据分类任务中，存在真实离群点——称为“流浪侵入离群点”（Stray Intrusive Outliers, SIOs），这些离群点远离自身类主体并侵入其他类主体，导致传统特征选择方法难以有效识别关键特征。
- **研究动机**：现有特征选择方法（如基于所有实例评分、或仅针对一般离群点）很少专门处理ADMHC场景，且无法准确刻画类主体（class body）。作者旨在通过聚焦SIOs，设计一种基于侵入程度评分的新特征选择方法。

## 2. 论文提出的方法论

### 核心思想
- **聚焦SIOs**：识别那些远离自身类中心并侵入其他类主体的实例，利用它们对分类的负面影响来反向评估特征的重要性。
- **特征评分**：特征对SIOs的侵入程度越低（即有助于区分两类），得分越高，排名越靠前。

### 关键技术细节
1. **精炼密度-均值中心（RDM center）**  
   - 定义实例密度为以该实例为球心、包含至少一半类内实例的最小超球半径的倒数。  
   - 选取高密度实例（比例α ∈ (0,1]）并取均值得到RDM中心，以合理表示类主体的一般特征。

2. **基于修改偏度系数与3σ原则的分割阈值**  
   - 计算类内实例到RDM中心的距离，并引入修改的偏度系数 \( \hat{s}^{(l)} \) 来量化分布不对称性。  
   - 融合3σ原则得到分割阈值 \( \Theta^{(l)} = u^{(l)} + (2 - \frac{\hat{s}^{(l)}}{3})\hat{\sigma}^{(l)} \)，用于判断实例是否侵入其他类主体。

3. **识别SIOs**  
   - 若实例 \( x_i^{(k)} \) 满足 \( \|x_i^{(k)} - u^{(l)}\|_1 < \Theta^{(l)} \) 且满足侵入判定条件（两个类超球相交），则确定为SIO，并形成SIO类对。

4. **特征评分**  
   - 对每个SIO类对，计算每个特征上的平均侵入程度 \( \bar{S}^{(kl_0)}_f \)。  
   - 选取侵入程度最低的一半SIO类对，对特征评分取平均，按升序排名并选择前m个特征。

### 公式与算法流程（文字说明）
- 论文给出了RDM中心获取算法（Algorithm 1）、SIOs识别算法（Algorithm 2）和最终特征选择算法（Algorithm 3）。  
- 时间复杂度：主要瓶颈为RDM中心的 \( O(n^2) \)，整体复杂度为 \( O(n^2 + n + nc + c^2 + dc) \)。

## 3. 实验设计

### 数据集
- **16个多类型数据集**：  
  - 小样本高维（CLL, TOX, Carcinom, Lung等12个生物/图像数据）  
  - 严重类间侵入（GISETTE手写数字）  
  - 深度特征（UCM、AID遥感场景，ModelNet 3D物体）  
  - 大类别数（Caltech101物体识别）

### Benchmark与对比方法
- **监督方法**（12个）：Fisher, QMI, ReliefF, TRC, ILFS, FSDOC, FSTU, FSNS, ReOLSR, MRMSR, S2DFS, IOFS。  
- **无监督方法**（3个扩展）：InfFS_U, EGCFS, FSDK。  
- 全部使用原文参数设置，代码取自原始发布。

### 评估指标
- 分类准确率（ACC）、归一化互信息（NMI）、混淆矩阵（CM）。  
- 使用线性SVM作为分类器，五折交叉验证（ModelNet使用原划分）。

## 4. 资源与算力

- **文中未明确提及GPU型号、数量或训练时长**。  
- 实验环境：Windows 7, Intel Xeon Gold 6128 CPU @ 3.40GHz, 16GB RAM。  
- 表5给出了部分数据集的运行时间（如CLL 0.92秒，GISETTE 865.58秒），显示SIOFS在大型数据集上耗时较长但可控。

## 5. 实验数量与充分性

- **实验数量**：  
  - 16个数据集 × 多种对比方法（总计15+个基线）。  
  - 消融实验：①不同类中心（RDM vs CFDP vs 均值）；②有无偏度系数（w/o SC）。  
  - 参数敏感性分析（α从0.05到0.95）。  
  - 不同特征数（50~300或5%~95%）下的性能比较。  
- **充分性与客观性**：  
  - 实验覆盖了多种数据场景（小样本、高维、深度特征、大类别），对比方法全面。  
  - 所有实验使用统一的五折交叉验证，结果报告了均值和标准差，统计可靠。  
  - 代码开源，参数遵循原文，消融实验验证了各组件贡献。

## 6. 论文的主要结论与发现

- **SIOFS在大部分数据集上优于所有基线**，尤其在ADMHC场景（如CLL、GISETTE）提升显著（比第二名高4.93%）。  
- **RDM中心**比CFDP和均值中心更有效（在8/12数据集上获得最高ACC）。  
- **偏度系数**的引入有助于处理多峰分布，且使结果更稳定（α标准差更小）。  
- 参数α在多数数据集上鲁棒，但对极少部分数据（如CLL）较敏感。  
- 无监督方法对比中，SIOFS在13/15数据集上取得最优。

## 7. 优点

- **方法新颖**：首次针对类内ADMHC数据，利用流浪侵入离群点进行特征选择，而非平等对待所有实例。  
- **数学完备**：给出RDM中心、分割阈值、侵入判定等关键步骤的数学证明（Theorem 1-2），确保理论合理性。  
- **实验全面**：涵盖16个多类型数据集、多个评估指标、消融和参数分析，验证了方法的有效性和鲁棒性。  
- **代码开源**：提供GitHub链接，便于复现和扩展。

## 8. 不足与局限

- **时间复杂度偏高**：RDM中心计算需 \( O(n^2) \)，在大规模数据集（如AID, ModelNet）上运行时间较长（表5）。  
- **参数α需调优**：虽然多数情况下鲁棒，但对部分分散型数据敏感，实际应用中可能需要交叉验证选择α。  
- **对极端不平衡类的处理**：当某类只有一个训练实例时，需要特殊处理（如设置变量系数ν），论文虽给出方案但不够通用。  
- **实验未覆盖更大型数据集**：如百万级样本场景，方法扩展性有待验证。  
- **未使用GPU加速**：所有实验在CPU上运行，未探索深度学习框架下的优化。

（完）
