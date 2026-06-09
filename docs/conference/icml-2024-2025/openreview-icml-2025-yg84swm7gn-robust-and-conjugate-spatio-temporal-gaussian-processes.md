---
title: Robust and Conjugate Spatio-Temporal Gaussian Processes
title_zh: 鲁棒且共轭的时空高斯过程
authors: "William Laplante, Matias Altamirano, Andrew B. Duncan, Jeremias Knoblauch, Francois-Xavier Briol"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=YG84SWm7gn"
tags: ["query:ocean-qc"]
score: 8.0
evidence: 鲁棒异常值的时空高斯过程，在天气预报上验证，可直接用于海洋数据
tldr: 针对时空高斯过程在存在异常值时性能下降的问题，将鲁棒共轭高斯过程（RCGP）推广到时空场景。该方法保持线性计算复杂度，同时克服了RCGP先验均值选择差、不确定性量化不可靠、超参数需手动选择等缺点。在金融和天气预报应用中展示了鲁棒性和准确性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 849, \"height\": 546, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 852, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1585, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 839, \"height\": 498, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1765, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1079, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1224, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 785, \"height\": 419, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 787, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 783, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 784, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 799, \"height\": 792, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 799, \"height\": 799, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1224, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1319, \"height\": 968, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1309, \"height\": 1127, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1045, \"height\": 1309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1227, \"height\": 1054, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1235, \"height\": 656, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yg84swm7gn/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 881, \"height\": 494, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-yg84swm7gn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 861, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yg84swm7gn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 865, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yg84swm7gn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 634, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yg84swm7gn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1772, \"height\": 455, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yg84swm7gn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 907, \"height\": 456, \"label\": \"Table\"}]"
motivation: 现有时空高斯过程在异常值存在时性能退化，且鲁棒版本存在多种缺陷。
method: 将RCGP扩展到时空设置，采用状态空间形式保持线性复杂度，并改进了先验均值和超参数选择。
result: 在金融和天气预报数据上，该方法在异常值污染下仍保持高精度和可靠的不确定性。
conclusion: 所提方法提供了鲁棒且高效的时空高斯过程框架。
---

## Abstract
State-space formulations allow for Gaussian process (GP) regression with linear-in-time computational cost in spatio-temporal settings, but performance typically suffers in the presence of outliers. In this paper, we adapt and specialise the *robust and conjugate GP (RCGP)* framework of Altamirano et al. (2024) to the spatio-temporal setting. In doing so, we obtain an outlier-robust spatio-temporal GP with a computational cost comparable to classical spatio-temporal GPs. We also overcome the three main drawbacks of RCGPs: their unreliable performance when the prior mean is chosen poorly, their lack of reliable uncertainty quantification, and the need to carefully select a hyperparameter by hand. We study our method extensively in finance and weather forecasting applications, demonstrating that it provides a reliable approach to spatio-temporal modelling in the presence of outliers.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **问题背景**：时空高斯过程（STGP）通过状态空间公式实现了线性计算成本，但在面对异常值（如极端事件、测量误差）时性能严重退化。现有时空GP的鲁棒改进方法（如非高斯似然、离群值拒绝卡尔曼滤波）要么破坏共轭性导致近似代价高，要么缺乏理论保障。
- **研究动机**：Altamirano et al. (2024) 提出的鲁棒共轭GP（RCGP）具有稳健性与共轭性，但仍存在三个主要缺陷：
  1. 对先验均值选择敏感（若先验均值远离真实函数，权重会错误地降低好点的权重）；
  2. 不确定性量化不可靠（超参数 β 和 c 的选择不当会导致过度或不足置信）；
  3. 超参数 c（缩小函数）需人工根据异常值比例启发式选择，实际中难以确定，且固定常数c在时空场景中不够自适应。
  此外，RCGP 计算复杂度为 O(N³)，不适合大规模时空数据。
- **目标**：将 RCGP 推广到时空场景，保持线性时间复杂度的同时，解决上述三个缺陷，实现鲁棒且高效的时空建模。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：将 RCGP 的广义贝叶斯框架与 STGP 的状态空间形式结合，通过加权得分匹配损失（weighted score-matching divergence）推导出鲁棒且共轭的滤波/平滑更新方程（Proposition 3.1）。利用状态空间的序列特性，动态调整权重函数以适应数据，从而解决 RCGP 的三大缺陷。
- **关键技术细节**：
  - **状态空间表示**：假设可分离且平稳的核函数，将时空GP先验表示为随机微分方程的解，得到线性高斯状态空间模型（式4），状态包含函数及其时间导数。
  - **广义贝叶斯更新**：使用加权得分匹配损失（式10），该损失包含权重函数 w(x,y)（选择逆多二次核 IMQ，式9）。损失函数二次型导致后验仍为高斯，更新公式与卡尔曼滤波形式一致，但用修正后的观测值和协方差矩阵（Proposition 3.1）。
  - **自适应权重**：针对 RCGP 的三个问题，提出：
    - 中心函数 γ(x_k) 取为滤波预测均值 f̂_k（来自稳健的广义后验预测），避免依赖先验均值。
    - 缩小函数 c²(x_k) 取为滤波预测方差 diag(Ŝ_k)，自适应控制下采样速率。
    - β 固定为 σ/√2，使无异常值时恢复标准 STGP。
  - **鲁棒性理论**（Proposition 3.3）：证明 IMQ 权重满足 sup_y |y|·w² < ∞，从而后验影响函数（PIF）有界，保证对任意大异常值的稳健性。
  - **鲁棒超参数优化**（φGB）：标准边际似然对异常值敏感，改用加权似然目标 φGB = ∑ w̃_k log p(y_k|y_1:k-1)，其中 w̃_k 为空间权重的某种聚合（如最小分位数），避免过度拟合异常值。
- **算法流程**：对于每个时间步 k，进行预测步（式5），然后根据更新步（式13-14）计算后验均值 m_GB 和协方差 P_GB，其中涉及自适应权重 w_k（基于当前预测分布计算γ和c）。平滑通过 Rauch-Tung-Striebel 算法完成。计算复杂度 O(n_t·n_s³)，与标准 STGP 相同。

### 3. 实验设计：数据集、基准与对比方法
- **数据集与场景**：
  1. **合成时空数据**（图1）：二维空间网格+时间，真实函数 f=sin(2πt)s₁²+cos(2πt)s₂²，10%异常值。
  2. **合成时间序列**（图3、4、8-10）：一维输入，GP生成数据+异常值，检验具体缺陷修复。
  3. **规范化设置**（表1）：合成时空数据，分有/无异常值两种情况。
  4. **金融数据**：
     - Twitter 闪崩（2013年4月23日，810点）（图5）。
     - 指数期货（N=46800点，合成闪崩）（表2、图16）。
  5. **天气预报数据**（英国 CRU 温度，571空间点×24月，N=11991，图6、表3）。在2023年10-11月引入聚集异常值，12月做一步预测。
- **基准与对比方法**：
  - 标准 STGP（作为基线）。
  - 原始 RCGP（在时间序列中对比）。
  - Relevance Pursuit（RP，Ament et al. 2024，仅在 Twitter 闪崩对比）。
  - BayesNewton 包中的鲁棒顺序GP方法：马尔可夫期望传播（MEP）、马尔可夫变分推理（MVI）、马尔可夫拉普拉斯（MLa）（在指数期货和天气数据中对比）。
  - 所有方法均使用Matérn核（ν=3/2或5/2）。
- **评估指标**：RMSE、负对数预测密度（NLPD）、期望权重比（EWR）——捕捉鲁棒性与统计效率的权衡。

### 4. 资源与算力
- **文中明确说明**：所有实验在 2020 年 13 英寸 MacBook Pro 的 M1 芯片（CPU）和 8GB 内存上运行（附录 C.2）。**未使用 GPU**。没有提供具体的训练时长，但由于状态空间方法的线性复杂度，实验中小规模数据（如 Twitter 闪崩 810 点）计算快速，大规模（46800 点）也仅需秒级（表 2 ST-RCGP 总时间 9.4 秒）。

### 5. 实验数量与充分性
- **实验数量**：论文包含大量实验，可归纳为以下几组：
  - 问题修复验证（图3、4、附录C.5-C.12）：展示RCGP的失败模式及ST-RCGP的改进。
  - 规范化设置（表1）：有/无异常值条件下的性能对比。
  - 金融应用（图5、表2）：两个真实数据集，其中表2对比了5种方法并报告标准差。
  - 天气应用（图6、表3）：月度数据，给出各月RMSE和NLPD。
  - 超参数优化对比（附录C.3、C.14）：φ vs φGB，并重复5次。
  - 敏感性分析（附录C.8、C.9）：IMQ指数、中心和缩小函数的影响。
  - 异常值时间影响（附录C.10）。
- **充分性与公平性**：
  - 实验覆盖了不同数据规模、不同异常值类型（随机、聚集、闪崩）、不同空间维度（1D时序、2D时空）。
  - 对比方法包括多种当前最先进的鲁棒STGP和RCGP变体，评估指标客观。
  - 在表2中报告了平均和标准差（3次或20次重复），具有统计意义。
  - 但在天气数据中未对比其他鲁棒方法（如MEP等），只在指数期货中对比；且未在大规模时空数据上比较MEP等方法的性能（可能由于计算量）。总体而言，实验设计较为充分，但更广泛的对比（如与其他稀疏或变分方法）可以进一步验证。

### 6. 论文的主要结论与发现
1. **ST-RCGP 成功克服 RCGP 三大缺陷**：通过自适应的中心（预测均值）和缩小（预测方差）函数，消除了对先验均值的敏感性，提供了可靠的不确定性量化，并自动选择合适的 c，无需人工指定异常值比例。
2. **鲁棒性理论保证**：Proposition 3.3 证明后验影响函数有界，即对任意大异常值鲁棒。
3. **计算成本与标准 STGP 相当**：O(n_t·n_s³) 时间，O(n_t·n_s²) 内存，远低于批处理 RCGP 的 O(N³)（N=n_t·n_s）。
4. **在多种场景中性能优越**：在合成数据、金融数据（真实闪崩和大规模合成闪崩）以及天气预测中，ST-RCGP 在异常值存在时 RMSE 和 NLPD 显著优于 STGP，且与更贵的学生 t 似然方法（MEP/MVI/MLa）性能相当甚至更好，同时计算速度更快（表2）。
5. **在规范化设置中保持效率**：表1显示，在无异常值时，ST-RCGP 与标准 STGP 的 RMSE/NLPD 几乎相同，EWR 接近1，说明并未因鲁棒性而牺牲统计效率。

### 7. 优点
- **理论贡献**：将 RCGP 与状态空间融合，提出自适应权重选择，给出鲁棒性证明（PIF有界）。
- **实用价值**：克服 RCGP 的实际使用障碍（先验均值、超参数选择），使其更易部署。
- **计算高效**：线性时间复杂度，可直接用于大规模时空数据，且是精确推断（无近似）。
- **实验丰富**：覆盖多个真实与合成数据集，与多种基线进行定量对比，包括当前最先进的鲁棒顺序GP方法。
- **不确定性量化改善**：通过自适应方差，比 RCGP 更可靠（参见图4覆盖图）。
- **代码开源**：提供可复现的实现。

### 8. 不足与局限
- **空间规模限制**：方法仍需要 O(n_s³) 时间处理每个时间步的空间网格，当空间点数量很大（如数万）时仍可能成为瓶颈。论文未讨论变分或稀疏近似来处理大规模空间维度（如 Hamelijnck et al. 2021 的方法）。
- **对比不够全面**：
  - 在天气数据中未与其他鲁棒方法（如 MEP）定量对比。
  - 未与基于稀疏近似的鲁棒 GP（如使用 inducing points 的 RCGP 变体）比较。
- **超参数优化仍依赖有效权重聚合**：提出的 φGB 中 w̃_k 的选择（如最小权重分位数）需要一定经验，论文未深入探讨不同聚合策略的影响。
- **实验重现性**：所有实验在 M1 MacBook CPU 上运行，但未报告具体的训练时间（仅表2给出了总时间），其他实验计算成本未定量说明。
- **缺少并行化讨论**：状态空间本质上是序列的，无法直接并行，论文指出这是未来工作。
- **仅限于回归问题**：未扩展到分类、计数等其他似然类型。

（完）
