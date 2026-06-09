---
title: Hierarchical State Space Models for Continuous Sequence-to-Sequence Modeling
title_zh: 用于连续序列到序列建模的分层状态空间模型
authors: "Raunaq Bhirangi, Chenyu Wang, Venkatesh Pattabiraman, Carmel Majidi, Abhinav Gupta, Tess Hellebrekers, Lerrel Pinto"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=TK7xkOsXDu"
tags: ["query:ocean-qc"]
score: 4.0
evidence: 分层状态空间模型处理传感器数据，可应用于海洋观测质量控制
tldr: 该论文针对连续序列到序列预测问题，提出分层状态空间模型，能够有效处理非线性传感器噪声和数据漂移。在少量标注数据下也能表现良好，其方法可迁移至海洋观测数据质量评估与异常检测任务。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-tk7xkosxdu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-tk7xkosxdu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 702, \"height\": 258, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-tk7xkosxdu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1774, \"height\": 597, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-tk7xkosxdu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1683, \"height\": 734, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-tk7xkosxdu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 642, \"height\": 612, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-tk7xkosxdu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 286, \"height\": 138, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-tk7xkosxdu/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1774, \"height\": 1022, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-tk7xkosxdu/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 720, \"height\": 1332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-tk7xkosxdu/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 452, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-tk7xkosxdu/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 353, \"height\": 405, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-tk7xkosxdu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1752, \"height\": 767, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-tk7xkosxdu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1748, \"height\": 1299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-tk7xkosxdu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 838, \"height\": 995, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-tk7xkosxdu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 799, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-tk7xkosxdu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1635, \"height\": 498, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-tk7xkosxdu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1235, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-tk7xkosxdu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1788, \"height\": 1115, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-tk7xkosxdu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1308, \"height\": 1114, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-tk7xkosxdu/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 737, \"height\": 548, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-tk7xkosxdu/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1573, \"height\": 1158, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-tk7xkosxdu/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1560, \"height\": 982, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-tk7xkosxdu/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1559, \"height\": 727, \"label\": \"Table\"}]"
motivation: 传统方法在真实传感器数据上表现不佳，且标注成本高。
method: 构建分层状态空间模型，利用层次结构处理多尺度动态。
result: 在传感器预测任务上优于基线方法。
conclusion: 为连续序列建模提供了鲁棒方案，适用于海洋传感器数据。
---

## Abstract
Reasoning from sequences of raw sensory data is a ubiquitous problem across fields ranging from medical devices to robotics. These problems often involve using long sequences of raw sensor data (e.g. magnetometers, piezoresistors) to predict sequences of desirable physical quantities (e.g. force, inertial measurements). While classical approaches are powerful for locally-linear prediction problems, they often fall short when using real-world sensors. These sensors are typically non-linear, are affected by extraneous variables (e.g. vibration), and exhibit data-dependent drift. For many problems, the prediction task is exacerbated by small labeled datasets since obtaining ground-truth labels requires expensive equipment. In this work, we present Hierarchical State-Space models (HiSS), a conceptually simple, new technique for continuous sequential prediction. HiSS stacks structured state-space models on top of each other to create a temporal hierarchy. Across six real-world sensor datasets, from tactile-based state prediction to accelerometer-based inertial measurement, HiSS outperforms state-of-the-art sequence models such as causal Transformers, LSTMs, S4, and Mamba by at least 23% on MSE. Our experiments further indicate that HiSS demonstrates efficient scaling to smaller datasets and is compatible with existing data-filtering techniques. Code, datasets and videos can be found on https://hiss-csp.github.io.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机与背景）

- **问题**：连续序列到序列预测（Continuous Sequence Prediction, CSP）在医疗设备、机器人等领域广泛存在，需要从长序列原始传感器数据（如磁力计、压阻传感器）预测物理量（如力、惯性测量）。传统方法（如卡尔曼滤波）依赖精确模型，但在真实传感器中常面临非线性、振动干扰、数据相关漂移等难题。此外，标注数据获取成本高，导致小样本问题突出。
- **背景**：深度序列模型（LSTM、Transformer）在处理高频、长序列传感器数据时存在内存/计算瓶颈；状态空间模型（SSM，如S4、Mamba）虽线性复杂度且表现较好，但仍缺乏对多尺度时间结构的显式建模。
- **目标**：提出分层状态空间模型（HiSS），利用时间层次结构提升CSP性能，同时验证其在低数据场景和预处理兼容性上的优势。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：将输入传感器序列划分为等长块（chunk），先由**底层SSM**处理每个块，提取局部特征；再将各块最后一时间步的输出拼接为“块特征序列”，由**顶层序列模型**（可选用SSM或LSTM/Transformer）预测最终输出序列。通过两个不同时间分辨率的模型层级，分别捕获局部细节和全局结构。
- **技术细节**：
  - **数据预处理**：重采样传感器序列至50Hz，输出序列至5Hz；对每个轨迹开头估计静止信号并减去；附加一阶差分。
  - **HiSS架构**：
    - 底层：共享SSM（如S4）处理每个大小为k的块，输出块特征。
    - 顶层：SSM（或LSTM/Transformer）处理缩短后的特征序列，生成输出。
  - **计算复杂度**：非重叠块时总复杂度O(N)；重叠块O(Nk)，仍远优于Transformer的O(N²)。
- **公式/算法流程**（文字描述）：
  1. 输入序列{s_1,...,s_m} → 划分为块（大小k）；
  2. 每个块经过底层SSM → 取每块最后输出c_t；
  3. 所有c_t构成新序列{c_1,...,c_n}（n≈m/k）；
  4. 顶层SSM处理该序列 → 输出预测序列{y_1,...,y_n}。

## 3. 实验设计：数据集、基准与对比方法

- **数据集与场景**：提出CSP-Bench，包含六个数据集（三个自收集+三个公开）：
  - 自收集：ReSkin Marker Writing（触觉→末端速度）、ReSkin Intrinsic Slip（触觉→线/角速度）、XELA Joystick Control（触觉→摇杆状态）。
  - 公开：RoNIN（智能手机IMU→平面速度）、VECtor（IMU→用户速度）、TotalCapture（IMU→关节速度）。
  - 累计约40小时数据，传感器频率50Hz，输出5Hz。
- **基准（baseline）**：两类：
  - **扁平模型**：Transformer、LSTM、S4、Mamba、MEGA。
  - **分层模型**：各种高低层组合（如Transformer+Transformer、LSTM+S4、S4+S4、Mamba+S4等）。
- **对比方法**：HiSS与扁平最优模型、其他分层模型在6个任务上比较MSE。

## 4. 资源与算力

- 论文**未明确说明**使用的GPU型号、数量及训练时长，仅提到所有模型训练600 epochs，学习率1e-3（无调度器）。调参范围在附录中给出，但未提及硬件资源。

## 5. 实验数量与充分性

- **实验数量**：核心实验（Table 2）覆盖6个数据集×至少5种扁平模型+16种分层模型，每种5个随机种子。此外还有消融实验：
  - 下采样输入对比（Table 3a）。
  - 低通滤波预处理兼容性（Table 3b）。
  - 小样本训练（Table 3c）。
  - 块大小影响（Table 4）。
  - 超参数扫掠（附录B）。
- **充分性**：实验设计较全面，对比了多个SOTA模型，验证了层次结构的优势，并分析了失败案例（TotalCapture）。但缺少与更多传统滤波方法（如卡尔曼滤波）的直接对比，且仅在6个传感器数据集上验证，泛化性仍有待扩展。

## 6. 主要结论与发现

1. **SSM表现优于LSTM和Transformer**：扁平SSM（Mamba、S4）平均比LSTM提升14% MSE，比Transformer提升10%。
2. **HiSS进一步提升**：HiSS在扁平最优模型基础上平均提升23% MSE（中位数），其中S4作为底层模型效果最佳。
3. **HiSS超越简单下采样**：直接下采样输入无法达到HiSS性能，说明层次结构能有效提取高频信息。
4. **块大小影响**：块大小接近传感器/输出频率比（10）时最优，继续增大提升有限。
5. **兼容预处理**：低通滤波可同时改善扁平模型和HiSS，但HiSS在不滤波时仍优于滤波后的扁平模型。
6. **小样本高效**：在30%~50%训练数据下，HiSS在所有任务上优于扁平模型，体现数据效率。
7. **失败案例**：在TotalCapture（高维输入输出、小数据集）上，LSTM优于SSM及HiSS，推测SSM难以过滤高频噪声。

## 7. 优点

- **方法新颖简洁**：通过简单堆叠SSM实现时间层次，不增加复杂结构。
- **性能突出**：在多个传感器任务上显著超越SOTA，且线性复杂度。
- **数据高效**：小样本场景下优势明显，适合标注成本高的应用。
- **兼容现有预处理**：可与低通滤波结合使用，降低预处理依赖。
- **开源基准**：贡献CSP-Bench，包含多模态传感器数据，利于后续研究。

## 8. 不足与局限

- **高维小样本场景失效**：TotalCapture任务中HiSS不如LSTM，表明SSM在噪声大、维度高、数据少的场景可能不够鲁棒。
- **块大小超参数**：虽然分析了影响，但缺乏自适应优化方法，需手动选定。
- **缺少与经典滤波方法的对比**：未与卡尔曼滤波、粒子滤波等传统CSP方法直接比较。
- **领域覆盖有限**：仅包含触觉和IMU传感器，未在音频、ECG等其他连续数据上验证。
- **算力资源未报告**：难以评估训练成本的可复现性。
- **数据偏差风险**：自收集数据集（如ReSkin writing）基于特定机器人和任务，可能不直接推广到其他设置。

（完）
