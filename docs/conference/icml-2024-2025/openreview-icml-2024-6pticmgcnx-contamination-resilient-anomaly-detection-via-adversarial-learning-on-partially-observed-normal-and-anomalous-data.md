---
title: Contamination-Resilient Anomaly Detection via Adversarial Learning on Partially-Observed Normal and Anomalous Data
title_zh: 基于对抗学习和部分观测正常及异常数据的抗污染异常检测
authors: "Wenxi Lv, Qinliang Su, Hai Wan, Hongteng Xu, Wenchao Xu"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=6PTiCmGcNx"
tags: ["query:anomaly-id"]
score: 8.0
evidence: 利用部分观测的正常和异常样本通过对抗学习进行抗污染异常检测
tldr: 现实异常检测中，正常数据集常被异常样本污染，导致模型性能下降。本文针对此问题提出一种对抗学习框架，通过收集两个小型部分观测的正常和异常样本集，辅助从污染数据中学习正常分布。理论证明在温和条件下该方法可有效恢复真实分布。实验表明，在多种污染比例下，该方法显著优于现有方法。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-6pticmgcnx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 821, \"height\": 350, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-6pticmgcnx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1411, \"height\": 611, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6pticmgcnx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 875, \"height\": 1093, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6pticmgcnx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1540, \"height\": 1093, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6pticmgcnx/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 806, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6pticmgcnx/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 853, \"height\": 452, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6pticmgcnx/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 787, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6pticmgcnx/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 722, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6pticmgcnx/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 670, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6pticmgcnx/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 782, \"height\": 381, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6pticmgcnx/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1028, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6pticmgcnx/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 736, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6pticmgcnx/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 963, \"height\": 488, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6pticmgcnx/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1141, \"height\": 684, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-6pticmgcnx/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1609, \"height\": 457, \"label\": \"Table\"}]"
motivation: 现实异常检测中，正常数据集常被污染，影响模型性能。
method: 利用部分观测的正常和异常小样本，通过对抗学习从污染数据中学习正常分布。
result: 在多种污染场景下显著提升了异常检测准确率。
conclusion: 所提方法在数据污染下仍能鲁棒检测异常。
---

## Abstract
Many existing anomaly detection methods assume the availability of a large-scale normal dataset. But for many applications, limited by resources, removing all anomalous samples from a large un-labeled dataset is unrealistic, resulting in contaminated datasets. To detect anomalies accurately under such scenarios, from the probabilistic perspective, the key question becomes how to learn the normal-data distribution from a contaminated dataset. To this end, we propose to collect two additional small datasets that are comprised of partially-observed normal and anomaly samples, and then use them to help learn the distribution under an adversarial learning scheme. We prove that under some mild conditions, the proposed method is able to learn the correct normal-data distribution. Then, we consider the overfitting issue caused by the small size of the two additional datasets, and a correctness-guaranteed flipping mechanism is further developed to alleviate it. Theoretical results under incomplete observed anomaly types are also presented. Extensive experimental results demonstrate that our method outperforms representative baselines when detecting anomalies under contaminated datasets.

---

## 论文详细总结（自动生成）

# 论文详细中英文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

现实异常检测中，获取纯净大规模正常数据集往往成本高昂或不现实，常见的是包含异常样本的**污染数据集**。现有方法要么假设训练集完全正常（如 Deep SVDD），要么仅利用额外收集的少量异常样本（如 Deep SAD），但未能同时利用少量的正常样本。此外，这些额外收集的样本数量通常很小（几十到几百个），极易导致过拟合。本文的核心动机是：**如何在训练集被污染、仅能获取部分正常和异常样本的情况下，鲁棒地学习正常数据分布并检测异常**。该问题贴近实际应用（如工业缺陷检测、金融欺诈），具有重要价值。

## 2. 论文提出的方法论：核心思想、关键技术细节

**核心思想**：基于对抗学习（GAN）框架，利用污染数据集 \( \mathcal{X} \)、小型纯正常集 \( \mathcal{X}^+ \) 和小型纯异常集 \( \mathcal{X}^- \) 来学习正常数据分布 \( p^+(x) \)。通过构造特定的混合分布 \( P(x) \) 和 \( Q(x) \)，并最小化它们之间的 \( f \)-散度，理论上可以证明生成器分布收敛到真实正常分布。

**关键技术细节**：

1. **分布构造**：
   - \( P(x) = (1-\lambda)p_{\text{data}}(x) + \lambda p^+(x) \) （包含污染数据和正常数据）
   - \( Q(x) = (1-\beta)p_g(x) + \beta p^-(x) \) （包含生成数据和异常数据）
   - 其中 \( p_{\text{data}} \) 为污染数据分布，\( p_g \) 为生成器分布，\( \lambda, \beta \) 为权重。

2. **理论保证**（Theorem 3.1）：当正常与异常支撑集不交叠且 \( \beta > (1-\lambda)(1-\pi) \)（\( \pi \) 为正常样本比例），采用 Pearson \( \chi^2 \) 或 KL 散度时，最优生成器分布等于 \( p^+(x) \)。

3. **过拟合缓解——翻转机制**：由于 \( \mathcal{X}^+ \) 和 \( \mathcal{X}^- \) 很小，判别器容易过拟合。作者提出在 \( P \) 和 \( Q \) 中引入“翻转”概率 \( \gamma \)，随机将一些正常样本视为异常、异常样本视为正常，混淆判别器，并证明在条件 \( (1-\gamma)\beta > (1-\lambda)(1-\pi) + \gamma \) 下，生成器仍可收敛到正常分布（Theorem 3.2）。同时提出自适应调整 \( \gamma \) 的方法。

4. **不完全异常类型场景**（Theorem 3.3）：当异常集仅覆盖部分异常类型时，生成器会收敛到正常分布与未观测异常分布的混合，但可以通过增大 \( \lambda \) 减轻未观测异常的影响。

5. **检测方法**：使用 BiGAN 架构（生成器 + 编码器），联合利用重构误差 \( \|x - G(E(x))\|^2 \) 和潜变量范数 \( \|E(x)\|^2 \) 作为异常得分。

**算法流程简述**：
- 输入：\( \mathcal{X} \), \( \mathcal{X}^+ \), \( \mathcal{X}^- \)。
- 交替优化判别器和生成器，损失函数为 LSGAN 形式（对应 Pearson \( \chi^2 \) 散度）。
- 在训练过程中根据判别器输出差异自适应调整翻转概率 \( \gamma \)。
- 训练完成后使用异常得分检测测试样本。

## 3. 实验设计

- **数据集**：
  - 玩具数据集：MNIST、Fashion-MNIST、CIFAR-10、20Newsgroups（文本特征由 BERT 提取）。
  - 真实异常检测数据集：UNSW-NB15（网络攻击）、HAR（人体活动识别）。
  - 额外 9 个经典异常检测数据集（Arrhythmia、Cardio、Satellite 等）。
- **基准方法**：无监督方法（Deep SVDD、Deep Isolation Forest）、自监督方法（SLAD、ICL）、半监督/利用异常样本的方法（Deep SAD、FeaWAD、RoSAS、PReNet、AA-BiGAN、SOEL）。
- **评估指标**：AUROC。
- **实验设置**：控制污染比例 \( \epsilon_p \)（5%~30%）、辅助集大小 \( \epsilon_n, \epsilon_a \)（1%~5%）、正常类别数量等。每个异常类型独立训练并取平均。

## 4. 资源与算力

论文**未明确说明**使用的 GPU 型号、数量或训练时长。所有实验基于 PyTorch 实现，采用 Adam 优化器。对于图像数据集使用 DCGAN 架构，表格数据使用 3 层 MLP。

## 5. 实验数量与充分性

- **实验组数丰富**：包括不同污染比例（4 级 × 6 数据集）、不同辅助集大小（10~50 × 6 数据集）、不同正常类别数量（1/3/5 × 4 数据集）、不同异常类型收集数量（1~4 × 4 数据集）、消融实验（2 数据集 × 2 模块）、参数敏感性分析（λ/β、γ、ρ 等）。
- **公平性**：基线方法使用官方实现或 DeepOD 库，配置尽量统一。报告多次运行平均结果（除注明外）。
- **结论可靠**：在所有污染条件下，所提方法一致优于对比方法，消融实验验证了各组件的有效性。
- **充分性评价**：实验覆盖了多种污染场景、数据模态（图像、文本、表格）、不同样本量，对比方法全面，结论具有说服力。

## 6. 论文的主要结论与发现

- 所提出的对抗学习框架（CR-GAN）能有效从污染数据中恢复正常数据分布，即便仅有少量部分观测的正常和异常样本。
- 翻转机制成功缓解了小样本过拟合问题，且理论保证不丢失收敛性。
- 当异常类型不完全时，模型仍能有效抑制已观测异常的影响。
- 在 6 个主要数据集和 9 个经典数据集上，所提方法 AUROC 均显著高于现有半/弱监督方法，尤其在污染比例高、辅助集小时优势更明显。

## 7. 优点

1. **理论创新**：严格证明在温和条件下生成器可收敛到真实正常分布，包括翻转机制下的不变性。
2. **实际价值高**：解决现实场景中训练数据污染、可获取正常/异常样本极少的难题。
3. **过拟合缓解巧妙**：翻转机制简单有效，且自适应调整无需额外调参。
4. **完备性**：考虑了不完全异常类型的实际情形，并给出理论分析。
5. **实验充分**：多数据集、多维度对比，消融和参数分析全面，结果可靠。

## 8. 不足与局限

1. **未报告计算资源与时间**：无法评估方法的实际训练开销。
2. **假设正常与异常支撑集不交叠**：现实场景中可能存在噪声或重叠，该假设可能过强。
3. **对超参数敏感依赖**：虽提供了理论条件，但实际中 \( \lambda, \beta, \gamma \) 仍需要调参，论文仅给出大致范围（0.6~0.8）。
4. **只使用 BiGAN 架构**：未探索其他生成模型（如扩散模型）是否可进一步提升性能。
5. **未在超大规模数据集（如 ImageNet）上验证**：实验均基于中小规模数据集，泛化性待进一步检验。
6. **异常检测指标单一**：仅使用 AUROC，未对比 F1 或 PR 曲线，尤其在不平衡场景中可能不够全面。

（完）
