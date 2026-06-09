---
title: Optimal Sensor Scheduling and Selection for Continuous-Discrete Kalman Filtering with Auxiliary Dynamics
title_zh: 具有辅助动力学的连续-离散卡尔曼滤波的最优传感器调度与选择
authors: "Mohamad Al Ahdab, John Leth, Zheng-Hua Tan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=CAPNgWkEEk"
tags: ["query:ocean-obs"]
score: 7.0
evidence: 具有不规则测量的卡尔曼滤波最优传感器调度，可应用于海洋观测网络
tldr: 连续-离散卡尔曼滤波中，传感器测量过程常与辅助状态耦合，例如提高测量率会增加能耗。本文研究在此场景下的最优传感器调度与选择问题，将测量事件建模为独立泊松过程，考虑传感器精度和成本约束。该方法能有效优化传感器部署策略，适用于海洋浮标、自主航行器等观测网络的设计。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-capngwkeek/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1048, \"height\": 2153, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-capngwkeek/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1022, \"height\": 1385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-capngwkeek/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1729, \"height\": 1787, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-capngwkeek/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1730, \"height\": 1417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-capngwkeek/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1740, \"height\": 1491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-capngwkeek/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1737, \"height\": 1718, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-capngwkeek/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1725, \"height\": 1643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-capngwkeek/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1723, \"height\": 1639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-capngwkeek/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1723, \"height\": 1638, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-capngwkeek/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1732, \"height\": 1763, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-capngwkeek/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 866, \"height\": 968, \"label\": \"Table\"}]"
motivation: 连续-离散卡尔曼滤波中传感器测量过程与辅助状态耦合，需要优化调度。
method: 将测量事件建模为泊松过程，结合连续-离散卡尔曼滤波设计传感器调度策略。
result: 优化了传感器部署，降低能耗并保持滤波精度。
conclusion: 为海洋观测等领域的传感器网络设计提供了理论指导。
---

## Abstract
We study the Continuous-Discrete Kalman Filter (CD-KF) for State-Space Models (SSMs) where continuous-time dynamics are observed via multiple sensors with discrete, irregularly timed measurements. Our focus extends to scenarios in which the measurement process is coupled with the states of an auxiliary SSM. For instance, higher measurement rates may increase energy consumption or heat generation, while a sensor’s accuracy can depend on its own spatial trajectory or that of the measured target. Each sensor thus carries distinct costs and constraints associated with its measurement rate and additional constraints and costs on the auxiliary state. We model measurement occurrences as independent Poisson processes with sensor-specific rates and derive an upper bound on the mean posterior covariance matrix of the CD-KF along the mean auxiliary state. The bound is continuously differentiable with respect to the measurement rates, which enables efficient gradient-based optimization. Exploiting this bound, we propose a finite-horizon optimal control framework to optimize measurement rates and auxiliary-state dynamics jointly. We further introduce a deterministic method for scheduling measurement times from the optimized rates. Empirical results in state-space filtering and dynamic temporal Gaussian process regression demonstrate that our approach achieves improved trade-offs between resource usage and estimation accuracy.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：在实际应用中（如卫星遥感、血糖监测、机器人环境探测），连续时间状态通过多个传感器离散、不规则地观测。每个传感器具有不同的精度、能耗、成本等特性，且测量过程往往与辅助状态（如传感器温度、位置、剩余能量）耦合。例如提高测量率会增加能耗或热产生，传感器精度可能依赖于其空间轨迹。因此需要权衡资源消耗与估计精度，实现最优的传感器调度与选择。
- **问题背景**：现有工作多针对离散时间系统或假设连续测量，未考虑连续-离散设置下传感器调度与辅助状态动力学的联合优化。本文填补这一空白，提出统一框架。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：将每个传感器的测量到达建模为独立的不齐次泊松过程，具有时变速率 λₛ(t)。基于此随机化模型推导后验协方差矩阵的上界，该上界关于测量速率连续可微，从而可用梯度优化。进一步构建有限时域最优控制问题，联合优化测量速率和辅助状态输入（如车辆轨迹）。最后用基于 Wasserstein-2 距离的最优量化方法从优化后的速率中确定性地选取测量时刻。
- **关键技术细节**：
  - **状态空间模型**：连续时间状态演化方程 (1a)，离散测量方程 (1b)。引入辅助状态 ξ (6)，包括受测量影响的扰动部分 ξₚ 和未扰动部分 ξᵤ。
  - **随机化卡尔曼滤波**：测量到达为泊松过程，协方差演化方程 (8)，辅助状态演化 (9)。
  - **协方差上界（命题6.1）**：利用 Kalman 更新项（Lemma A.1 证明其凸性）和 Jensen 不等式，得到上界协方差矩阵满足的 ODE (10)，此上界 ⪰ 真实均值协方差。
  - **辅助状态上界（命题6.2）**：在辅助动态满足凹/凸假设（Assumption 5.1）下，用比较定理得到均值辅助状态的上/下界。
  - **最优控制问题 (12)**：最小化运行成本 L 和终端成本 LT，约束包括动力学、测量速率非负、输入集、运行约束和终端约束。假设成本/约束在协方差上单调非增。
  - **确定性测量时刻选择（命题8.1）**：通过最小化 Wasserstein-2 距离将归一化强度测度 μₛ 量化为等概率区间上的条件质心，得到确定性时刻，使得平均测量次数匹配预期。
- **数值求解**：采用直接多打靶法结合 Euler 离散化，用 JuMP 和 IPOPT 求解 NLP。

## 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **主要实验场景**：
  - 机器人监测环境过程（如污染物浓度）示例：两传感器，能耗受充电站距离影响，噪声随距离指数增加。又引入放射性环境扩展，传感器精度随辐射损伤下降。
  - 附录中还包含：水质监测（传感器结垢与主动除垢）、航天器监测地面目标、移动目标跟踪（非高斯模型，采用滚动时域框架）。
- **Benchmark 对比方法**：
  - **Random**：均匀离散化后按常数速率采样。
  - **Greedy**：每一步按预测协方差减小的即时得分选择传感器。
  - **M-Optimized**：从优化速率的泊松过程中采样多个实现，选成本最低者。
- **评价指标**：协方差迹的均值、标准差、最差值；能量 η 和退化 ζ 的均值、标准差、最差值。

## 4. 资源与算力：如果文中有提到，请总结使用了多少算力。若未明确说明，也请指出这一点。

- **未明确说明**使用的 GPU 型号、数量或训练时长。论文仅在附录 D 中报告了在 Intel Core Ultra 7 155H @ 1.40 GHz, 64GB RAM 设备上的优化时间（针对不同离散点数从约 0.5 秒到 3.5 秒），但未提及并行训练或大规模计算资源。所有实验均可能在普通 CPU 上完成。

## 5. 实验数量与充分性：大概做了多少组实验，这些实验是否充分、客观、公平

- **实验数量**：
  - 主要示例（机器人+放射性环境）给出两种场景（无/有辐射损伤），对比四种方法（Optimized, M-Optimized, Greedy, Random），统计了三种指标。
  - 附录包含多个额外示例（水质、航天器、目标跟踪），每个都有可视化结果。
  - 附录 H 还提供了违反假设的非凸/非凹情况下的四组实验。
- **充分性**：实验覆盖了不同应用领域和模型复杂度，对比了基准方法，结果展示了所提方法在资源-精度权衡上的优势。但缺少与更多现有最优传感器调度方法的系统对比（因现有方法未覆盖此设定）。另外，随机性评估中仅对 Greedy 和 Random 运行一至多次？表 1 中给出了均值和标准差，推测多次重复，但未明确说明重复次数。
- **客观性与公平性**：对比方法中 Greedy 和 Random 基于相同的优化轨迹输入（而联合优化学到了更好的轨迹），可能使结果偏向所提方法。作者在文中也承认缺乏直接对比的现有方法，因此比较是合理的。

## 6. 论文的主要结论与发现

- 所提联合优化测量速率和辅助状态输入的方法能够有效降低协方差迹（不确定性），并更好地满足能量和退化约束。
- 确定性量化方法（Proposition 8.1）与大量采样（M-Optimized）性能相近，但无需多次采样，计算高效。
- 在多个场景（机器人、水质、航天器、目标跟踪）中验证了可行性，即使在辅助动态不满足严格凹凸假设时（附录 H）也能取得合理结果。
- 提出的上界能够很好追踪真实协方差，说明理论分析具有实用价值。

## 7. 优点：方法或实验设计上有哪些亮点

- **理论贡献**：首次将传感器调度与辅助动力学联合考虑，给出可微上界，使得梯度优化成为可能。
- **模型普适性**：辅助状态可包含多种物理量（位置、能量、损伤、结垢），测量速率可用作连续决策变量。
- **确定性调度方法**：基于 Wasserstein 距离的最优量化，避免了泊松随机采样的不确定性，易于工程应用。
- **实验覆盖性**：涉及多个真实世界启发场景，包括非线性和不确定动力学（通过滚动时域扩展），验证了方法的泛化能力。

## 8. 不足与局限

- **假设限制**：辅助动态需满足凹/凸性（Assumption 5.1）以获得严格上界；虽附录显示轻微违背时可容忍，但严重非线性下理论保证失效。
- **对比方法较少**：缺乏与其他现有传感器调度算法（如基于信息论、强化学习）的直接比较。
- **实验重复性未明确**：表 1 未说明重复次数与随机种子，统计鲁棒性有待明确。
- **计算复杂度**：对于高维状态或长时域，直接求解 OCP 可能计算昂贵，文中仅给出小规模示例。
- **检测与泛化**：未考虑非高斯噪声、模型失配等实际挑战；滚动时域扩展仅简要介绍，未深入分析闭环性能。

（完）
