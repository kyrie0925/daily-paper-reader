---
title: Deep Positive-Unlabeled Anomaly Detection for Contaminated Unlabeled Data
title_zh: 面向污染未标记数据的深度正-无标签异常检测
authors: "Hiroshi Takahashi, Tomoharu Iwata, Atsutoshi Kumagai, Yuuki Yamanaka"
date: 2025-01-21
pdf: "https://openreview.net/pdf?id=UEOLHWNswj"
tags: ["query:anomaly-id"]
score: 9.0
evidence: 面向含异常未标记数据的深度正-无标签异常检测框架
tldr: 半监督异常检测中未标记数据常被异常污染，削弱了检测效果。本文提出深度正-无标签异常检测框架，整合PU学习，有效利用少量已知异常和污染未标记数据。在多个基准上优于现有方法，解决了污染数据下的异常检测挑战。
source: ICML-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ueolhwnswj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1785, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueolhwnswj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1781, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueolhwnswj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1774, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueolhwnswj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1780, \"height\": 416, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ueolhwnswj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1616, \"height\": 578, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueolhwnswj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1601, \"height\": 577, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueolhwnswj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1615, \"height\": 576, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueolhwnswj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1616, \"height\": 577, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueolhwnswj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1599, \"height\": 576, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueolhwnswj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1599, \"height\": 577, \"label\": \"Table\"}]"
motivation: 现有半监督异常检测假设未标记数据正常，但实际常被污染，导致性能下降。
method: 提出深度正-无标签异常检测框架，利用PU学习从未标记数据中分离已知异常，优化异常检测器。
result: 在多种污染比例下，所提方法均优于现有半监督及无监督异常检测方法。
conclusion: 该框架有效处理污染未标记数据，提升了半监督异常检测的实用性和鲁棒性。
---

## Abstract
Semi-supervised anomaly detection, which aims to improve the anomaly detection performance by using a small amount of labeled anomaly data in addition to unlabeled data, has attracted attention. Existing semi-supervised approaches assume that most unlabeled data are normal, and train anomaly detectors by minimizing the anomaly scores for the unlabeled data while maximizing those for the labeled anomaly data. However, in practice, the unlabeled data are often contaminated with anomalies. This weakens the effect of maximizing the anomaly scores for anomalies, and prevents us from improving the detection performance. To solve this problem, we propose the deep positive-unlabeled anomaly detection framework, which integrates positive-unlabeled learning with deep anomaly detection models such as autoencoders and deep support vector data descriptions. Our approach enables the approximation of anomaly scores for normal data using the unlabeled data and the labeled anomaly data. Therefore, without labeled normal data, our approach can train anomaly detectors by minimizing the anomaly scores for normal data while maximizing those for the labeled anomaly data. Experiments on various datasets show that our approach achieves better detection performance than existing approaches.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：半监督异常检测通常利用少量已知异常样本和大量未标记数据来提升检测性能。现有方法假设未标记数据中大部分为正常，通过最小化未标记数据的异常分数、最大化已知异常数据的异常分数来训练检测器。然而，实际场景中未标记数据往往被异常污染（即包含未标记的异常点），导致“最大化异常分数”的效果被削弱，严重限制了检测性能的提升。
- **核心问题**：如何在未标记数据被异常污染的情况下，有效利用少量已知异常和污染未标记数据，提升异常检测的准确率和鲁棒性。
- **整体含义**：本文提出**深度正-无标签（PU）异常检测框架**，将 PU 学习与深度异常检测模型（如自编码器、DeepSVDD）相结合，能够从未标记数据和已知异常中近似正常数据的异常分数，从而无需正常标签即可优化检测器。该方法在多个基准数据集上优于现有半监督和无监督方法，解决了污染数据下的实际困难。

---

## 2. 方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：将异常视为“正类”，正常视为“负类”，利用 PU 学习的假设——未标记数据分布是正常分布与异常分布的混合（\( p_U(x) = \alpha p_A(x) + (1-\alpha)p_N(x) \)）。从而近似出正常数据的异常分数期望：
  \[
  (1-\alpha)E_{p_N}[\ell_{\text{BCE}}(x,0;\theta)] \approx \frac{1}{N}\sum \ell_{\text{BCE}}(x_n,0;\theta) - \alpha\frac{1}{M}\sum \ell_{\text{BCE}}(\tilde{x}_m,0;\theta)
  \]
  其中 \(\ell_{\text{BCE}}\) 是基于重构误差的二元交叉熵损失。
- **关键技术细节**：
  - 训练目标函数：\( \alpha L_A^+(\theta) + L_U^-(\theta) - \alpha L_A^-(\theta) \)，其中前三项分别对应已知异常的异常分数、未标记数据的正常分数、已知异常的正常分数。为避免第二、三项之和为负导致无意义解，取绝对值保证非负。
  - 具体实现两个变体：
    - **PUAE（Positive-Unlabeled Autoencoder）**：基于自编码器的重构误差，使用上述损失函数。
    - **PUSVDD（Positive-Unlabeled Support Vector Data Description）**：基于 DeepSVDD 的特征距离损失 \( \|f_\theta(x)-c\|^2 \)，替换 PUAE 中的损失函数。
  - 算法流程：采用小批量随机梯度下降（如 Adam），交替计算三类损失并更新参数。
- **适用性**：框架可扩展至其他非负可微的损失函数（如去噪自编码器、自监督检测器）。

---

## 3. 实验设计

- **数据集**：8 个图像数据集：
  - 前四个：MNIST、FashionMNIST、SVHN、CIFAR10（每个 10 类，选取其中一类为正常，另一类为“未见异常”，其余为“可见异常”）。
  - 后四个：CIFAR100（利用超类划分）、PathMNIST、OCTMNIST、TissueMNIST（医学图像，按专业类别划分正常/异常）。
- **训练数据构造**：共 5000 样本，其中 4500 个未标记正常、250 个标记可见异常、250 个未标记可见异常（即未标记数据被 5% 的异常污染）。测试集包含正常、可见异常、未见异常各约一半。
- **对比方法**：
  - 无监督：Isolation Forest（IF）、AE、DeepSVDD、LOE（Latent Outlier Exposure）。
  - 半监督：ABC（Autoencoding Binary Classifier）、DeepSAD、SOEL（State-of-the-art 半监督方法，基于 LOE）。
  - 参考：PU 学习二分类器（PU）。
- **评价指标**：AUROC（曲线下面积），所有实验重复 5 次取平均和标准差。
- **超参数**：对 PUAE、PUSVDD、PU、LOE、SOEL 等设置 \(\alpha=0.1\)（真实污染比例），并使用验证集进行早停。

---

## 4. 资源与算力

- **硬件**：CPU 为 AMD EPYC 9124 16-Core Processor，内存 512GB，GPU 为 NVIDIA RTX 6000 Ada（未说明数量）。
- **训练设置**：所有神经网络采用卷积架构，学习率 1e-4，mini-batch 128，最大 200 个 epoch，weight decay 1e-3，早停基于验证集。文中**未明确给出总训练时长**。

---

## 5. 实验数量与充分性

- **实验数量**：在 8 个数据集上，每个数据集的正常类遍历（例如 MNIST 中 9 种正常选择），每个设置重复 5 次随机种子，共产生大量结果。此外还进行了超参数敏感性实验（图 2，改变 \(\alpha\) 从 0.1 到 0.5），以及不同未标记异常数量（附录 B，从 100 到 500 个未标记异常）的对比。
- **充分性评价**：
  - 覆盖了多种图像类型（手写、时尚、街景、自然、医学），具有较好的泛化性。
  - 对比了 8 种以上现有方法（含无监督和半监督），包括最新的 SOEL。
  - 缺少消融实验（如仅使用 PU 损失而不取绝对值、不同基础检测器的对比等），未明确分析各模块贡献。
  - 实验设置严格，但未涉及时间序列或表格数据，泛化范围有限。

---

## 6. 主要结论与发现

- PUSVDD 在全部 8 个数据集上取得**最优或持平的最优结果**，显著优于现有半监督方法（如 SOEL、DeepSAD）和无监督方法（如 IF、AE、DeepSVDD）。
- PUAE 在大部分数据集上优于对应基础模型（AE 和 ABC），但在部分数据集上略逊于 PUSVDD。
- 相比传统 PU 分类器，所提方法能有效检测**未见异常**（unseen anomalies），而 PU 分类器因只能在正常与可见异常间划分边界，对未见异常失效。
- 超参数 \(\alpha\) 的敏感性实验表明，PUSVDD 对 \(\alpha\) 偏离真实值比 SOEL 更鲁棒；当 \(\alpha\) 接近真实污染比例时，性能最佳。
- 在未标记异常数量变化时（附录 B），PUSVDD 仍保持优于 SOEL 的性能。

---

## 7. 优点

- **理论严谨**：基于无偏 PU 学习，损失函数在数据集规模趋于无穷时渐近无偏，有理论保证。
- **实用性强**：能同时处理**可见异常**（类似已知类型的异常）和**未见异常**（全新类型），弥补了传统半监督异常检测对污染数据敏感、PU 分类器无法检测新异类别的缺陷。
- **通用性**：框架适用于多种深度异常检测模型（AE、DeepSVDD、自监督模型等），只需损失函数非负可微。
- **鲁棒性**：对超参数 \(\alpha\) 误差容忍度较高，有利于实际应用。

---

## 8. 不足与局限

- **实验覆盖有限**：仅使用图像数据集，未在时间序列、表格数据或文本数据上验证。作者在结论中提未来扩展至时间序列，侧面反映当前局限。
- **偏差风险**：假设异常分布是固定的（\(p_A\)），但真实世界新异常可能不符合该分布，存在领域偏移。文中也承认这一点。
- **超参数\(\alpha\)依赖**：虽然实验显示对\(\alpha\)有一定鲁棒性，但最佳性能仍需精确估计污染比例，而实际中该比例未知，需额外估计方法（已有工作，但本文未实验）。
- **缺少消融研究**：未单独评估 PU 学习组件、损失函数裁剪等对最终性能的具体贡献，也未分析不同基础检测器（如 AE vs. DAE）在框架下的差异。
- **计算成本**：虽未报告具体训练时间，但神经网络训练（最大200 epoch）加上遍历正常类，总计算量较大，但未与对比方法进行公平的时间统计。

（完）
