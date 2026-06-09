---
title: Online Adaptive Anomaly Thresholding with Confidence Sequences
title_zh: 基于置信序列的在线自适应异常阈值
authors: "Sophia Huiwen Sun, Abishek Sankararaman, Balakrishnan Murali Narayanaswamy"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=hbsKxUEreL"
tags: ["query:anomaly-id"]
score: 8.0
evidence: 自适应异常阈值设置，基于置信序列
tldr: 在线无监督异常检测中，阈值选择常因分布漂移而困难。本文提出一种连接在线阈值与置信序列的算法，能在分布变化下自适应调整阈值，并提供假阳性率和假阴性率的统计保证。如果提供相关离线数据可进一步提升性能。该方法适用于大规模系统监控，为异常检测阈值设定提供了理论支持。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-hbskxuerel/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 828, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hbskxuerel/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 703, \"height\": 135, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hbskxuerel/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 823, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hbskxuerel/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 821, \"height\": 272, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hbskxuerel/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 775, \"height\": 297, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hbskxuerel/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1593, \"height\": 806, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hbskxuerel/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1334, \"height\": 666, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-hbskxuerel/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 723, \"height\": 549, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-hbskxuerel/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hbskxuerel/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 862, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hbskxuerel/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 599, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hbskxuerel/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1098, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hbskxuerel/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1041, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-hbskxuerel/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1345, \"height\": 300, \"label\": \"Table\"}]"
motivation: 在线异常检测中阈值选择困难，尤其在数据分布变化时缺乏自适应性和统计保证。
method: 构造置信序列实现自适应阈值，提供无需分布假设的FPR/FNR统计保证。
result: 在合成和真实数据上算法能有效应对分布偏移，且离线数据可加速收敛。
conclusion: 为在线异常检测提供了首个兼具适应性和统计保证的阈值方法。
---

## Abstract
Selecting appropriate thresholds for anomaly detection in online, unsupervised settings is a challenging task, especially in the presence of data distribution shifts. Addressing these challenges is critical in many practical large scale systems, such as infrastructure monitoring and network intrusion detection. This paper proposes an algorithm that connects online thresholding with constructing confidence sequences achieving (1) adaptive online threshold selection robust to distribution shifts, (2) statistical guarantees on false positive and false negative rates without any distributional assumptions, and (3) improved performance when given relevant offline data to warm-start the online algorithm, while having bounded degradation if the offline data is irrelevant. We complement our theoretical results by empirical evidence that our method outperforms commonly used baselines across synthetic and real world datasets.

---

## 论文详细总结（自动生成）

# 基于置信序列的在线自适应异常阈值：详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：在线异常检测（OAD）中，阈值的选择直接影响系统性能。在无监督、在线场景下，数据分布漂移使得静态阈值容易导致大量误报（FP）或漏报（FN）。此外，实际系统往往有冷启动问题——初期因缺乏数据而无法做出决策，导致大量样本被“弃权”（abstain）。现有方法无法同时满足：高准确率、低弃权率、自适应分布变化、有效利用离线数据、且无需分布假设。
- **整体含义**：本文首次提出一种基于置信序列（Confidence Sequences, CS）的阈值自适应算法，能够在无分布假设下保证假阳性率和假阴性率的统计界，并能在离线数据相关时提升性能、不相关时性能退化有界。该工作为在线异常检测阈值设定提供了理论严谨的解决方案。

## 2. 论文提出的方法论

- **核心思想**：将异常定义为超过异常分数分布第p分位数的样本。利用置信序列（CS）构造每个时刻的估计区间 \(C(p, \alpha, S_{1:t})\)，然后根据当前样本 \(S_t\) 与CS的关系做出决策：
  - 若 \(S_t > \max C\) → 判为异常（1）
  - 若 \(S_t < \min C\) → 判为正常（0）
  - 否则 → 弃权（*）
- **关键技术细节**：
  - 采用Howard & Ramdas (2022)的逐点置信序列公式（式1），其宽度随时间按 \(O(\sqrt{\log\log t / t})\) 收缩。
  - 针对分布漂移，使用Shekhar & Ramdas (2023)的变点检测算法（Algorithm 2），通过比较前向和后向CS是否相交来检测变化。
  - 对于离线数据，设计算法仅当离线CS与在线CS相交且唯一时才合并使用；否则只用在线数据。
  - 最终算法（Algorithm 5）结合了变点检测和离线数据利用，无需知道漂移位置和幅度。
- **关键公式**：置信序列上下界为 \(\hat{Q}(\max(0, p-2u_t(\alpha)), S_{1:t})\) 和 \(\hat{Q}(\min(1, p+2u_t(\alpha)), S_{1:t})\)，其中 \(u_t(\alpha) = 0.85 \sqrt{t^{-1}[\log\log(et) + 0.8\log(1612/\alpha)]}\)。
- **算法流程**：每个时间步t，先执行变点检测（Algorithm 2），若检测到变化则弃权并重置；否则调用Algorithm 4（利用离线数据）或Algorithm 1（仅在线）进行决策。

## 3. 实验设计

- **使用的数据集/场景**：
  - 合成数据：从正态分布和帕累托分布生成，加入随机分布漂移。
  - MNIST手写数字：偶数数字为正常，奇数为异常，用于单类异常检测。
  - 真实云服务数据：两个大规模数据集DS1和DS2（共约1.8亿样本），来自大型云监控服务，目标异常率为0.001%（p=1-10⁻⁶）。
- **Benchmark/对比方法**：
  - 静态阈值：τ30%（将固定比例样本判为异常）。
  - DSpot：基于极值理论的动态阈值方法。
  - EQ：基于在线梯度下降的经验分位数方法。
- **评估指标**：弃权率（Abs. %）和错误数（FP+FN）。

## 4. 资源与算力

论文中未明确提及使用的GPU型号、数量或训练时长。实验主要涉及CPU上的流式处理，未涉及大规模深度学习训练。因此，无法提供算力细节。

## 5. 实验数量与充分性

- **实验数量**：合成数据1000次重复（每次2000样本），MNIST结果在多个stream上重复，真实数据两个大规模数据集共约18000个stream。
- **充分性与公平性**：
  - 合成实验覆盖了四种场景（是否含漂移、是否含离线数据），结果取平均值±标准差，统计稳定。
  - MNIST实验使用了两种常见异常检测模型（隔离森林和卷积自编码器）生成分数，证明了算法与任意评分模型的兼容性。
  - 真实数据实验与四种基线对比，展示了在目标异常率下的性能优势。
  - 不足：未进行消融实验（如单独验证变点检测模块、离线数据利用模块的贡献）；未与更多最新基线（如基于深度学习的阈值方法）比较。

## 6. 论文的主要结论与发现

- 理论证明：任何不弃权的算法在平稳流上至少会出现 \(O(\sqrt{T})\) 次错误（定理15），因此弃权是必要的。
- 所提算法在平稳流上实现零错误、弃权数 \(O(\sqrt{T})\)（概率≥1-2α）。
- 在分段平稳流中，错误数仅与变化次数和量级有关，与流长度无关；弃权数 \(O(\sqrt{HT \cdot T})\)。
- 当离线数据与在线分布匹配时，弃权数可降低至 \(O(\sqrt{N+T} - \sqrt{N})\)；不匹配时，性能相对于无离线数据仅增加常数延迟。
- 真实数据实验中，算法实现了目标异常率（0.001%），而所有基线产生的异常数高出一个数量级，导致警报疲劳。

## 7. 优点

- **理论完备性**：首次为在线自适应阈值提供了统计保证，覆盖平稳、漂移、离线数据等场景。
- **无需分布假设**：算法和理论均不要求高斯、次高斯等假设，适用于任意连续分布。
- **实际可用性强**：能够与任意异常评分算法结合，适用于大规模监控系统。
- **自适应离线数据**：离线数据相关时自动利用、无关时自动忽略，且有理论退化界。
- **实验验证充分**：覆盖合成、MNIST、真实云数据，与多种基线对比，结果一致优于基线。

## 8. 不足与局限

- **理论假设较强**：论文假设样本在时间上独立、分布漂移为突变且间隔足够大（可检测性假设5.1和6.1）。现实场景中可能出现缓变漂移或时间依赖，算法尚无保障。
- **实验覆盖有限**：未在更复杂的数据集（如多变量时间序列、网络入侵检测公开基准）和更多基线（如基于贝叶斯变点检测的方法）上测试。
- **可扩展性未讨论**：未涉及流长度极大（如万亿级）或高维分数时的计算效率问题。
- **参数敏感性**：算法需要指定分位数p和置信度α，实际中p的选取可能依赖领域知识，论文未讨论自适应p的方法。
- **开源代码未提供**：论文声称将开源，但论文中未给出链接，可复现性受限。

（完）
