---
title: Non-parametric Online Change Point Detection on Riemannian Manifolds
title_zh: 黎曼流形上的非参数在线变点检测
authors: "Xiuheng Wang, Ricardo Augusto Borsoi, Cédric Richard"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=VW7Jk8KhNC"
tags: ["query:anomaly-id"]
score: 8.0
evidence: 流形上在线变点检测，用于时间序列异常
tldr: 流形值时间序列的变点检测因几何特性而困难。本文提出一种非参数在线变点检测算法，通过随机黎曼优化追踪广义Karcher均值，并给出检测和虚警率的理论界。实验表明该方法在多种流形数据上有效。该工作将变点检测推广到非欧空间，对海洋、气象等流形观测数据有潜在应用价值。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-vw7jk8khnc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 848, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-vw7jk8khnc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 840, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-vw7jk8khnc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-vw7jk8khnc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 847, \"height\": 407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-vw7jk8khnc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1687, \"height\": 852, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-vw7jk8khnc/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1644, \"height\": 982, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-vw7jk8khnc/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 850, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-vw7jk8khnc/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 517, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-vw7jk8khnc/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 611, \"height\": 377, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-vw7jk8khnc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 845, \"height\": 458, \"label\": \"Table\"}]"
motivation: 现有流形数据变点检测方法未充分利用几何结构，且缺乏在线算法。
method: 监控广义Karcher均值，使用随机黎曼梯度下降实现在线更新。
result: 理论证明检测性能边界，仿真和真实数据上验证有效。
conclusion: 首次为流形数据提供在线变点检测算法及保证。
---

## Abstract
Non-parametric detection of change points in streaming time series data that belong to Euclidean spaces has been extensively studied in the literature. Nevertheless, when the data belongs to a Riemannian manifold, existing approaches are no longer applicable as they fail to account for the structure and geometry of the manifold. In this paper, we introduce a non-parametric algorithm for online change point detection in manifold-valued data streams. This algorithm monitors the generalized Karcher mean of the data, computed using stochastic Riemannian optimization. We provide theoretical bounds on the detection and false alarm rate performances of the algorithm, using a new result on the non-asymptotic convergence of the stochastic Riemannian gradient descent. We apply our algorithm to two different Riemannian manifolds. Experimental results with both synthetic and real data illustrate the performance of the proposed method.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：流形值时间序列数据（如扩散张量成像、行人检测、姿态识别中的 SPD 矩阵或 Grassmann 流形数据）的变点检测（CPD）在现实中具有重要意义。然而，现有变点检测方法绝大多数假设数据属于欧氏空间，无法利用流形的非欧几何结构。少数面向流形的方法要么是离线参数化的，要么缺乏理论分析，要么不适用于在线场景。
- **动机**：填补非参数在线变点检测在黎曼流形上的空白，同时提供理论保证（检测延迟、虚警率界），以支撑实际应用（如语音活动检测、动作识别等）。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：通过随机黎曼梯度下降（R-SGD）在线跟踪数据流的广义 Karcher 均值，并利用两个不同步长（λ < Λ）的估计量间的黎曼距离作为检测统计量。大步长估计量快速适应新分布（代表变化后均值），小步长估计量保持记忆（代表变化前均值）。
- **关键技术细节**：
  - 广义 Karcher 均值的定义：`m* = argmin_{m∈M} E_{x∼P}[c(x,m)]`，本文主要采用 `c(x,m) = d_M^2(x,m)`（Karcher 均值）。
  - 在线更新公式（R-SGD）：
    - `m_{λ,t+1} = exp_{m_{λ,t}}(-λ H(m_{λ,t}, x_t))`
    - `m_{Λ,t+1} = exp_{m_{Λ,t}}(-Λ H(m_{Λ,t}, x_t))`
  - 检测统计量：`g_t = d_M(m_{λ,t}, m_{Λ,t})`。当 `g_t > ξ` 时判定为变点。
  - 理论分析（三个定理）：
    - **定理 4.1**：R-SGD 在常数步长下的非渐近收敛界（曲率依赖的线性收敛速率）。
    - **定理 4.2**：无变点时虚警率上界（与 Karcher 方差、梯度噪声等成正比）。
    - **定理 4.3**：有变点时检测率下界（与变化前后均值距离、步长、样本数等相关）。
- **算法流程**：Algorithm 1 给出了在线步骤：初始化、更新两估计量、计算距离、与阈值比较。

## 3. 实验设计

- **数据集/场景**：
  - **合成数据**：
    - SPD 流形（S⁺⁺ₚ）：从 Wishart 分布采样，p=8，2000 样本，变点 t_r=1500。
    - Grassmann 流形（Gᵏₚ）：从矩阵高斯分布生成，p=15, k=5，2000 样本，变点 t_r=1500。
  - **真实数据**：
    - **语音活动检测**：TIMIT 语音 + QUT-NOISE 噪声，提取 STFT 特征，构造 SPD 协方差或 Grassmann 子空间描述符。
    - **骨架动作识别**：HDM05 动作捕捉数据库，构造关节协方差描述符（p=93）。
- **Benchmark 与对比方法**：
  - Scan-B（欧氏在线核方法），NEWMA（欧氏在线 EWMA 特征），F-CPD（流形离线 Fréchet 均值方法），NODE（欧氏在线密度比方法）。其中 Scan-B、NEWMA、NODE 被向量化适应流形数据。
- **评估指标**：ROC 曲线（检测率 vs 虚警率）、平均运行长度（ARL）与平均检测延迟（MDD）。

## 4. 资源与算力

- **文中未明确提及**：未说明使用的 GPU 型号、数量、训练时长或分布式计算资源。代码库为 Python 实现（Pymanopt），运行环境推测为通用 CPU/GPU，但无详细规格。

## 5. 实验数量与充分性

- **实验数量**：
  - 合成数据：每种流形上 10⁴ 次蒙特卡洛运行（图 1、2）。
  - 语音活动检测：10⁴ 次运行（图 3）。
  - 骨架动作识别：10³ 次运行（图 4）。
- **充分性评估**：
  - **覆盖性**：涵盖两种常见流形（SPD、Grassmann），合成数据与两类真实场景。对比了 4 种基线方法（含流形专用和欧氏方法），指标包括 ROC 和 ARL-MDD 折衷。
  - **合理性**：实验设计较为客观，基线选择涵盖不同流派，未包含自身变体消融（如不同步长组合、阈值自适应影响），但提供了附录中自适应阈值示例（图 9）。
  - **局限性**：缺少对理论界中参数（如曲率、Karcher 方差）的敏感性分析；未在更多流形（如球面、双曲流形）上验证。

## 6. 主要结论与发现

- **合成数据**：本文方法在 ROC 曲线和 ARL-MDD 折衷上显著优于所有基线，尤其在高 ARL（低虚警率）时检测延迟更低。
- **真实数据**：
  - 语音活动检测：检测率高于 Scan-B 和 NEWMA（除极小 ARL 外），且 MDD 更优。
  - 骨架动作识别：检测率大幅领先，MDD 在中等 ARL 以上显著降低。
- **理论贡献**：首次为流形在线变点检测提供非渐近收敛、虚警率上界、检测率下界等理论保证。
- **实用性**：算法框架通用，可应用于多种流形，且计算复杂度可控（O(p³) 或 O(p²k)）。

## 7. 优点

- **理论原创性**：给出了 R-SGD 在常数步长下的非渐近收敛结果（曲率依赖线性率），并基于此推导了 CPD 的虚警与检测性能界。
- **算法普适性**：基于广义 Karcher 均值，不限于特定流形；可拓展到非 Hadamard 流形（实验验证了 Grassmann 流形）。
- **实验充分性**：在合成和真实场景下与多种基线对比，结果稳健；提供了统计量直方图、阈值自适应方法等辅助分析。
- **可复现性**：开源代码公开（GitHub），利于社区验证。

## 8. 不足与局限

- **理论假设限制**：理论分析依赖于凸性和 Hadamard 流形条件（如曲率有下界），实际流形（如 Grassmann）可能不满足，理论保证难以直接推广。
- **样本需求**：要求变点间间隔足够长以使算法收敛，否则检测延迟大、性能下降。
- **计算资源未讨论**：未报告训练时间或硬件需求，不利于资源规划。
- **实验覆盖不足**：
  - 缺少消融实验分析步长 λ、Λ 或阈值 ξ 的影响。
  - 未包含更多流形（如球面 S²）或更高维数据以验证扩展性。
  - 对比方法中未包含近期深度流形学习基线（如图神经网络流形 CPD）。
- **阈值选择**：虽提供启发式自适应方法（附录 B），但依赖于高斯假设和人工调参。

（完）
