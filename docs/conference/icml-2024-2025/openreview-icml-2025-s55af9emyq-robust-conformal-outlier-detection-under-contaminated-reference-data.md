---
title: Robust Conformal Outlier Detection under Contaminated Reference Data
title_zh: 污染参考数据下的鲁棒共形异常值检测
authors: "Meshi Bashari, Matteo Sesia, Yaniv Romano"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=s55Af9Emyq"
tags: ["query:anomaly-id"]
score: 8.0
evidence: 污染参考数据下的鲁棒共形异常值检测
tldr: 共形预测在异常值检测中需要干净的参考集来控制错误率，但实际中参考集常受污染。本文理论分析了污染的影响，证明在非对抗场景下污染数据会导致保守的I类错误控制，即共形方法具有内在鲁棒性。实验验证了理论结果，并展示了该方法在污染场景下仍能维持良好性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 843, \"height\": 419, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 839, \"height\": 224, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1744, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1742, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1290, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 875, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 874, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 902, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1750, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1748, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1743, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1742, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1540, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1290, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1291, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1656, \"height\": 1206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1656, \"height\": 1205, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1655, \"height\": 1205, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1711, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1218, \"height\": 1210, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1220, \"height\": 1210, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1222, \"height\": 1609, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s55af9emyq/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1241, \"height\": 973, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 689, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1199, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1768, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1768, \"height\": 999, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1768, \"height\": 1000, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1775, \"height\": 1098, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1771, \"height\": 1101, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1775, \"height\": 1098, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1775, \"height\": 1097, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1772, \"height\": 1104, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1771, \"height\": 1101, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1771, \"height\": 1096, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1771, \"height\": 1098, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1770, \"height\": 1097, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1771, \"height\": 1096, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1771, \"height\": 1096, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1771, \"height\": 1096, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1774, \"height\": 1147, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1774, \"height\": 1153, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1774, \"height\": 1150, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1774, \"height\": 1142, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1773, \"height\": 1152, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s55af9emyq/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1773, \"height\": 1148, \"label\": \"Table\"}]"
motivation: 真实场景中参考数据集往往含有污染，影响异常检测的假阳性控制。
method: 分析共形方法在污染数据下的性质，证明其保守性并保持有效性。
result: 理论证明和实验验证了方法的鲁棒性。
conclusion: 共形预测对参考数据污染具有内在鲁棒性。
---

## Abstract
Conformal prediction is a flexible framework for calibrating machine learning predictions, providing distribution-free statistical guarantees. In outlier detection, this calibration relies on a reference set of labeled inlier data to control the type-I error rate. However, obtaining a perfectly labeled inlier reference set is often unrealistic, and a more practical scenario involves access to a contaminated reference set containing a small fraction of outliers. This paper analyzes the impact of such contamination on the validity of conformal methods. We prove that under realistic, non-adversarial settings, calibration on contaminated data yields conservative type-I error control, shedding light on the inherent robustness of conformal methods. This conservativeness, however, typically results in a loss of power. To alleviate this limitation, we propose a novel, active data-cleaning framework that leverages a limited labeling budget and an outlier detection model to selectively annotate data points in the contaminated reference set that are suspected as outliers. By removing only the annotated outliers in this ``suspicious'' subset, we can effectively enhance power while mitigating the risk of inflating the type-I error rate, as supported by our theoretical analysis. Experiments on real datasets validate the conservative behavior of conformal methods under contamination and show that the proposed data-cleaning strategy improves power without sacrificing validity.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：共形预测（Conformal Prediction）为异常检测提供了分布自由的类型 I 错误控制，但其校准过程依赖于一个完全干净的、仅含内点的参考数据集。然而在实际应用中，获取完美标记的参考集十分困难，更常见的场景是参考集受到少量异常值（outliers）的污染。
- **核心问题**：当参考数据集被污染时，共形方法是否还能保证类型 I 错误控制？如果失控，是过于保守还是过于激进？如何在不牺牲有效性的前提下提高检测能力（power）？
- **整体含义**：本文理论上证明，在非对抗、现实的污染场景下，共形方法会表现出保守的类型 I 错误（实际错误率低于目标水平），而非失控膨胀，这揭示了共形方法的内在鲁棒性。但这种保守性会导致检测能力下降。为此，论文提出一个主动数据清洗框架（Label-Trim），利用有限的标注预算选择性地移除参考集中的真实异常值，从而在保持类型 I 错误控制的同时提升检测能力。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：利用一个预训练的异常检测模型（如 Isolation Forest、ReAct），计算污染参考集中每个点的非一致性分数（nonconformity scores），然后选择分数最高的 $m$ 个样本（最可能是异常值）进行人工标注。只移除标注为异常值的点，保留标注为内点的点以及所有未被标注的点，得到部分清洁的参考集 $D_{\text{cal}}^{\text{LT}}$。最后在该清洁集上计算共形 p 值。
- **关键技术细节**：
  - **算法 1**（构建阶段）：给定污染参考集 $D_{\text{cal}}=\{X_i\}_{i=1}^n$、分数函数 $s(\cdot)$、标注预算 $m$。计算所有 $S_i=s(X_i)$，排序后取最大的 $m$ 个进行标注。构造 $D_{\text{cal}}^{\text{LT}} = \{\text{索引 } i \leq n-m \} \cup \{\text{标注为内点的索引}\}$。
  - **算法 2**（测试阶段）：对测试点 $X_{n+1}$，计算共形 p 值：
    \[
    \hat{p}_{n+1}^{\text{LT}} = \frac{1 + \sum_{i \in D_{\text{cal}}^{\text{LT}}} \mathbb{I}[s(X_i) \geq s(X_{n+1})]}{1 + |D_{\text{cal}}^{\text{LT}}|}.
    \]
    若 $\hat{p}_{n+1}^{\text{LT}} \leq \alpha$，则拒绝零假设（判定为异常值）。
- **理论依据**：论文给出定理 3.1，在 $m \leq \alpha(n+1)$ 的条件下，Label-Trim 方法的类型 I 错误率上界为
  \[
  \mathbb{P}(\hat{p}_{n+1}^{\text{LT}} \leq \alpha) \leq \alpha + \frac{1}{n_0+1} - \mathbb{E}\left[ \frac{\hat{n}_1^{\text{LT}}}{n_0+1} \left( (1-\alpha) - \hat{F}_1^{\text{LT}}(\hat{Q}_{1-\alpha}^{\text{LT}}) \right) \right],
  \]
  其中 $\hat{n}_1^{\text{LT}}$ 为清洁集中剩余异常值数量，$\hat{F}_1^{\text{LT}}$ 为剩余异常值得分的经验 CDF，$\hat{Q}_{1-\alpha}^{\text{LT}}$ 为清洁集得分上 $1-\alpha$ 分位数。当异常值被有效去除时，该上界接近 $\alpha$，保证了近似的有效性。

## 3. 实验设计：数据集/场景、基准、对比方法

- **数据集**：
  - 表格数据集（3个）：shuttle、credit-card、KDDCup99。
  - 视觉数据集（6个）：以 CIFAR-10 为内点，异常点分别来自 MNIST、SVHN、Texture、Places365、TinyImageNet、CIFAR-100。
- **基准模型**：
  - 表格数据：Isolation Forest（sklearn 默认参数）。
  - 视觉数据：ReAct（ResNet-18 骨干，分数基于能量函数），另补充 VGG-19 骨干和 SCALE（ResNet-18）的结果。
- **对比方法**：
  - **Standard**：使用未清洁的污染参考集 $D_{\text{cal}}$。
  - **Oracle**（不可行基准）：使用仅含内点的理想参考集。
  - **Naive-Trim**：直接移除得分最高的 $r\%$ 个点（$r=n_1/(n_0+n_1)$）。
  - **Small-Clean**：用标注预算 $m$ 随机选 $m$ 个点，只保留其中的内点作为小清洁集。
  - **Label-Trim**：本文方法，预算 $m=50$（默认）。
- **场景设置**：训练集和校准集具有相同污染率 $r$（0%~5% 及更高）；测试集由内点测试集和异常点测试集组成。每项实验重复 100 次随机分割，报告平均类型 I 错误和平均相对 power（以 Standard 为 1 归一化）。

## 4. 资源与算力

- 论文中**未明确说明**所使用的 GPU 型号、数量或训练时长。
- 视觉实验使用预训练的 ResNet-18 和 VGG-19 骨干进行特征提取，仅在特征上运行 ReAct/SCALE 方法，计算开销较小。表格实验使用轻量级 Isolation Forest。整体算力需求不高，未提及分布式或多卡训练。

## 5. 实验数量与充分性

- **实验数量**：涵盖了 3 个表格数据集 × 多种污染率（0%~5% 及更高）、多种标注预算 $m$（10~100）、多种目标类型 I 错误率 $\alpha$（0.01~0.05）、两种额外异常检测模型（LOF、OC-SVM）、多种异常注入策略（随机、低分异常）、测试时分布漂移等。视觉数据上报告了 6 个异常集、3 种骨干模型的结果。
- **充分性**：实验设计全面，覆盖了主要变量和边缘条件。每次实验平均 100 次随机分割并报告标准误，确保了统计可靠性。对比方法设置公平（使用相同检测模型和训练数据）。补充材料中提供了大量额外结果（如高污染率、更多模型）。
- **客观性**：没有明显偏向性 bias，对自身方法的保守性也进行了诚实分析。实验是公平的。

## 6. 论文的主要结论与发现

1. **污染导致保守性**：标准共形方法在污染参考集下类型 I 错误率显著低于目标 $\alpha$，且随污染率增加进一步降低（符合引理 2.2）。
2. **Naive-Trim 无效**：简单移除高得分点会导致类型 I 错误膨胀（高于 $\alpha$），因为可能移除了内点。
3. **Label-Trim 有效**：在低污染率下，Label-Trim 的类型 I 错误接近 $\alpha$，且检测能力接近 Oracle；在中高污染率下仍具一定保守性但远优于 Standard。
4. **预算影响**：随着标注预算 $m$ 增加，Label-Trim 性能单调提升，在 $m$ 超过条件 $m \leq \alpha(n+1)$ 时仍能控制类型 I 错误（鲁棒性）。
5. **目标 $\alpha$ 影响**：Label-Trim 在低 $\alpha$ 下优势更明显，因为污染主要影响得分分布尾部。
6. **对其他模型和分布漂移的鲁棒性**：方法在 LOF、OC-SVM 以及测试异常分布漂移下仍保持有效性和较好 power。

## 7. 优点

- **理论与实践结合**：提供了严谨的理论上界（引理 2.2、定理 3.1），并用大量实验验证。
- **实用性**：利用有限的标注预算，无需完全清洁参考集，适用于实际场景。
- **全面的实验验证**：覆盖多类型数据集、多模型、多场景，结果可信。
- **算法简洁**：Label-Trim 基于排序和选择性标注，易于实现。
- **公开代码**：提供 GitHub 仓库，可复现。

## 8. 不足与局限

- **标注依赖**：方法需要主动标注，若无法获取人工标注（或标注成本过高）则不适用。
- **保守性残留**：当标注预算很小或污染率较高时，Label-Trim 仍可能保守，power 提升有限。
- **理论条件较强**：定理 3.1 要求 $m \leq \alpha(n+1)$，但实验表明超出该条件仍有效，理论界可以进一步放松。
- **i.i.d. 假设**：理论分析和主要实验假设内点和测试点同分布，未考虑协变量漂移或标签漂移（仅补充实验中考察了异常分布漂移）。
- **未探索半监督清洗**：文中提到未来方向，但当前方法未涉及利用小清洁集辅助清洗大污染集。

（完）
