---
title: Outlier-robust Kalman Filtering through Generalised Bayes
title_zh: 通过广义贝叶斯实现鲁棒异常值的卡尔曼滤波
authors: "Gerardo Duran-Martin, Matias Altamirano, Alex Shestopaloff, Leandro Sánchez-Betancourt, Jeremias Knoblauch, Matt Jones, Francois-Xavier Briol, Kevin Patrick Murphy"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=D2MNVeVh5J"
tags: ["query:anomaly-id"]
score: 7.0
evidence: 通过广义贝叶斯实现状态空间模型的鲁棒异常值卡尔曼滤波
tldr: 传统卡尔曼滤波在测量模型存在异常值和误设时性能下降。本文提出结合广义贝叶斯与扩展/集合卡尔曼滤波的鲁棒更新规则，具有闭式形式且计算高效。在目标跟踪、高维混沌系统状态估计等实验中，该方法以更低计算成本匹配或超越其他鲁棒滤波方法。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-d2mnvevh5j/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 752, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-d2mnvevh5j/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 837, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-d2mnvevh5j/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 796, \"height\": 560, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-d2mnvevh5j/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 807, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-d2mnvevh5j/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 797, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-d2mnvevh5j/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 807, \"height\": 1219, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-d2mnvevh5j/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 840, \"height\": 669, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-d2mnvevh5j/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 765, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-d2mnvevh5j/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 809, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-d2mnvevh5j/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1582, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-d2mnvevh5j/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1247, \"height\": 486, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-d2mnvevh5j/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 789, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-d2mnvevh5j/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1600, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-d2mnvevh5j/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1554, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-d2mnvevh5j/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1583, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-d2mnvevh5j/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1590, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-d2mnvevh5j/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1543, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-d2mnvevh5j/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1542, \"height\": 697, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-d2mnvevh5j/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1563, \"height\": 702, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-d2mnvevh5j/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 873, \"height\": 491, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-d2mnvevh5j/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 775, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-d2mnvevh5j/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 647, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-d2mnvevh5j/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 908, \"height\": 539, \"label\": \"Table\"}]"
motivation: 传统卡尔曼滤波对异常值敏感，在测量模型误设时性能下降。
method: 结合广义贝叶斯和扩展/集合卡尔曼滤波，获得闭式鲁棒更新规则。
result: 在多个滤波问题中，以更低计算成本匹配或超越其他鲁棒方法。
conclusion: 该方法提供了高效鲁棒的在线滤波。
---

## Abstract
We derive a novel, provably robust, efficient, and closed-form Bayesian update rule for online filtering in state-space models in the presence of outliers and misspecified measurement models. Our method combines generalised Bayesian inference with filtering methods such as the extended and ensemble Kalman filter. We use the former to show robustness and the latter to ensure computational efficiency in the case of nonlinear models. Our method matches or outperforms other robust filtering methods (such as those based on variational Bayes) at a much lower computational cost. We show this empirically on a range of filtering problems with outlier measurements, such as object tracking, state estimation in high-dimensional chaotic systems, and online learning of neural networks.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 论文的核心问题与整体含义

- **研究动机**：概率状态空间模型（SSM）广泛应用于时间序列预测、在线学习、目标跟踪等场景。卡尔曼滤波（KF）在线性高斯模型下是最优的，但其假设测量噪声为高斯分布，实际中异常值（outliers）或测量模型误设会导致滤波性能严重下降。现有鲁棒方法如变分贝叶斯（VB）或粒子滤波（PF）计算成本高，难以扩展到高维系统。
- **整体含义**：本文提出一种基于广义贝叶斯（Generalised Bayes）的加权观测似然滤波器（WoLF），能够以闭式更新、低计算成本的方式鲁棒处理异常值，同时保持与标准KF相近的复杂度，适用于线性及非线性（EKF、EnKF）场景。

## 2. 论文提出的方法论

- **核心思想**：将广义贝叶斯框架引入滤波更新步骤，用加权负对数似然替代标准对数似然，从而降低异常观测的影响。权重函数W(yt, ŷt)动态依赖于当前观测与其预测值之间的差异，实现自适应下采样。
- **关键技术细节**：
    - 定义损失函数：ℓt(θt) = -W²(yt, ŷt) log q(yt|θt)。
    - 提出三种权重函数：
        - **IMQ（逆多二次型）**：W(yt, ŷt) = [1 + ||yt - ŷt||²/c²]^{-1/2}，连续平滑，补偿型。
        - **MD（马氏距离型）**：用马氏距离替代欧氏距离，考虑测量协方差。
        - **TMD（阈值马氏距离型）**：若马氏距离 > c，则权重为0（忽略该观测），否则为1；检测-拒绝型。
    - 线性情形下（Proposition 3.1）：WoLF-KF更新方程与标准KF相同，仅将R_t^{-1}替换为W² R_t^{-1}，因此计算复杂度仍为O(m³)。
    - 非线性情形：扩展至EKF和EnKF，分别通过加权似然（式16）或加权误差项（式84-89）实现。
    - 理论证明（Theorem 3.2）：对于线性/线性化SSM，标准KF的后验影响函数（PIF）无界，而WoLF在权重函数有界且加权范数有界条件下PIF有界，从而保证异常值鲁棒性。

## 3. 实验设计

- **数据集/场景**：
    1. **2D目标跟踪**（线性KF）：
        - 学生t分布观测（重尾异常）
        - 混合模型观测（5%概率跳变均值）
    2. **UCI回归数据集上的在线MLP学习**（非线性EKF）：
        - 9个UCI数据集（Boston, Concrete, Energy, Kin8nm, Naval, Power, Protein, Wine, Yacht）
        - 人为添加10%均匀异常值（U[-50,50]）
    3. **Lorenz96混沌系统状态估计**（非线性EnKF）：
        - 100维状态，0.1%概率异常值（设为100）
- **Benchmark方法**：
    - KF/EKF基线：标准KF、EKF。
    - 鲁棒基线：KF-B（Bernoulli异常检测+VB）、KF-IW（逆Wishart先验+VB）、Hub-EnKF（Huber化EnKF）、OGD（在线Adam优化）。
- **对比指标**：
    - 跟踪：缩放RMSE（JT,i）和相对运行时间。
    - 回归：RMedSE（中位数平方根误差，对异常值稳健）和每步时间。
    - Lorenz96：内状态RMSE（Lt）及超参数敏感性分析。

## 4. 资源与算力

- 论文未明确说明使用的GPU型号、数量或训练时长。所有实验在CPU上运行，代码基于JAX实现，强调了低计算成本（线性情形O(m³)，与KF同阶）。未提及大规模分布式训练资源。

## 5. 实验数量与充分性

- **实验数量**：三个主要实验场景，每个场景包含100次独立试验（trials），UCI实验覆盖9个数据集，Lorenz96实验包含多次运行和超参数扫描。附录中还有补充1D回归实验。
- **充分性**：
    - 覆盖线性、非线性（EKF、EnKF）多种滤波框架。
    - 对比了多种代表性鲁棒方法（VB型、Huber型、优化型）。
    - 进行了超参数敏感性分析（图14, 17）和异常率敏感性分析（图16）。
    - 提供理论证明（PIF有界）支持。
- **公平性**：超参数通过贝叶斯优化在第一次试验中选择，其余试验固定，减少调参偏差。但缺少对计算时间与精度权衡的系统性统计检验。

## 6. 论文的主要结论与发现

- WoLF方法在大多数实验中匹配或优于现有鲁棒滤波方法（KF-B、KF-IW、Hub-EnKF），且计算成本显著更低（通常接近标准KF，而VB方法慢2-12倍）。
- WoLF-IMQ（连续加权）和WoLF-TMD（阈值加权）在不同异常场景下表现稳定，且对超参数选择不如对比方法敏感。
- 理论证明（PIF有界）保证了方法的鲁棒性，而标准KF的PIF无界。

## 7. 优点

- **计算高效**：闭式更新，复杂度O(m³)，与KF同阶，远低于VB迭代方法（O(I m³)）。
- **方法简洁易扩展**：只需修改似然权重，即可应用于KF、EKF、EnKF，甚至指数族分布。
- **理论保证**：严格证明后验影响函数有界，提供鲁棒性理论基础。
- **实验设计全面**：涵盖低维跟踪、高维混沌系统、在线神经网络学习等多种场景，对比方法多样。

## 8. 不足与局限

- **局限性**：
    - 当前方法仅针对测量异常值，未处理状态过程异常（如模型突变）。
    - 假设测量协方差R_t和动态协方差Q_t已知，实际中可能未知。
    - 后验假设为单峰高斯，不适用于多模态后验分布。
    - 未与粒子滤波（PF）类方法进行全面比较（附录中仅简要对比RBPF，指出其速度慢）。
- **实验覆盖**：
    - 未在真实数据集上测试（所有实验均为模拟或人为添加异常值的UCI数据），可能高估实际性能。
    - 未进行统计显著性检验（如配对t检验）以确认方法间差异是否显著。
    - 超参数选择仅基于第一次试验，未在所有试验中重新优化，可能导致某些方法表现偏优或偏劣。
- **偏差风险**：作者来自学术界和工业界（Google DeepMind、UCL、牛津等），可能存在对自身方法的偏好，但实验设计相对透明。

（完）
