---
title: "SCENT: Robust Spatiotemporal Learning for Continuous Scientific Data via Scalable Conditioned Neural Fields"
title_zh: SCENT：基于可扩展条件神经场的连续科学数据鲁棒时空学习
authors: "David Keetae Park, Xihaier Luo, Guang Zhao, Seungjun Lee, Miruna Oprescu, Shinjae Yoo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=vhjuemZuRU"
tags: ["query:ocean-qc"]
score: 9.0
evidence: 鲁棒时空学习，处理传感器故障导致的缺失值，可应用于海洋数据质量控制
tldr: 针对科学数据中传感器故障导致的缺失和时空依赖复杂等问题，提出SCENT框架。该框架基于Transformer编码-处理器-解码器架构，统一了插值、重建和预测任务。在处理含缺失值的海洋气象等科学数据集时，SCENT在重建和预报精度上显著优于现有方法，且具有良好的可扩展性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vhjuemzuru/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1760, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhjuemzuru/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1770, \"height\": 1035, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhjuemzuru/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 862, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhjuemzuru/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1763, \"height\": 536, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhjuemzuru/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1750, \"height\": 1052, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhjuemzuru/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 844, \"height\": 802, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhjuemzuru/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 845, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhjuemzuru/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 843, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhjuemzuru/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1260, \"height\": 2090, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhjuemzuru/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1658, \"height\": 2102, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vhjuemzuru/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1738, \"height\": 2077, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vhjuemzuru/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1711, \"height\": 340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhjuemzuru/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 847, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhjuemzuru/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 813, \"height\": 409, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhjuemzuru/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1572, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhjuemzuru/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1393, \"height\": 1354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhjuemzuru/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1712, \"height\": 1388, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhjuemzuru/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1717, \"height\": 1368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhjuemzuru/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1298, \"height\": 499, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhjuemzuru/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 700, \"height\": 472, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhjuemzuru/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 786, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhjuemzuru/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 892, \"height\": 489, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vhjuemzuru/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1126, \"height\": 254, \"label\": \"Table\"}]"
motivation: 科学数据常因传感器故障等导致缺失值，且时空依赖复杂，现有方法难以处理。
method: 提出SCENT框架，采用Transformer架构统一插值、重建和预测，并通过条件神经场实现可扩展性。
result: 在多个科学数据集上，SCENT在缺失值重建和预测任务中达到最优性能。
conclusion: 该框架为含缺失值的科学数据提供了一种统一的鲁棒学习方法。
---

## Abstract
Spatiotemporal learning is challenging due to the intricate interplay between spatial and temporal dependencies, the high dimensionality of the data, and scalability constraints. These challenges are further amplified in scientific domains, where data is often irregularly distributed (e.g., missing values from sensor failures) and high-volume (e.g., high-fidelity simulations), posing additional computational and modeling difficulties. In this paper, we present SCENT, a novel framework for scalable and continuity-informed spatiotemporal representation learning. SCENT unifies interpolation, reconstruction, and forecasting within a single architecture. Built on a transformer-based encoder-processor-decoder backbone, SCENT introduces learnable queries to enhance generalization and a query-wise cross-attention mechanism to effectively capture multi-scale dependencies. To ensure scalability in both data size and model complexity, we incorporate a sparse attention mechanism, enabling flexible output representations and efficient evaluation at arbitrary resolutions. We validate SCENT through extensive simulations and real-world experiments, demonstrating state-of-the-art performance across multiple challenging tasks while achieving superior scalability.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：时空学习（Spatiotemporal Learning）面临空间与时间依赖的复杂交织、数据高维性以及可扩展性瓶颈。在科学领域，数据常因传感器故障导致不规则分布（如缺失值），且数据量极大（如高保真模拟），进一步加剧了计算和建模困难。
- **研究动机**：现有方法如隐式神经表示（INRs）虽具有灵活性，但缺乏可扩展性和泛化性（需为每个新样本重新训练）。而通用INRs（GINRs）和条件神经场（CNFs）虽有所改进，但仍存在多阶段优化瓶颈或处理稀疏、噪声数据能力不足。
- **整体含义**：本文提出SCENT框架，旨在通过统一的编码器-处理器-解码器架构，同时支持插值、重建和预测，并具备可扩展性和鲁棒性，以应对科学数据中的缺失值、噪声和动态传感器等挑战。

## 2. 方法论：核心思想、关键技术细节、算法流程

- **核心思想**：SCENT基于Transformer架构，引入可学习查询（learnable queries）和查询级交叉注意力机制，捕捉多尺度依赖；采用稀疏注意力确保对数据规模和模型复杂度均具有可扩展性；通过条件神经场实现连续时空表示学习。
- **关键技术细节**：
  - **编码器-处理器-解码器框架**：输入数据 \( U_{t_i} \)（含空间坐标、时间戳）通过交叉注意力编码为固定大小的潜在令牌 \( Z_{t_o}^M \)。
  - **时间目标空间编码器（TTSE）**：将输入时间 \( t_i \) 和输出时间 \( t_o \) 同时输入，增强注意力聚焦；使用傅里叶特征编码坐标，线性投影编码函数值；通过上下文嵌入网络（CEN）中的稀疏自注意力丰富令牌上下文。
  - **时间扭曲处理器（TWP）**：学习连续时间动态，将 \( Z_{t_i}^M \) 映射到 \( Z_{t_o}^M \)，支持重建（\(\Delta t=0\)）和预测（\(\Delta t>0\)）。提出**扭曲-展开预测（WUF）**策略：当预测跨度超过时间地平线 \( t_h \) 时，直接跳到 \( t_h \) 状态作为参考，减少多步展开时的误差累积。
  - **时间条件解码器**：对目标空间坐标和输出时间进行傅里叶特征编码，通过交叉注意力与潜在令牌交互，再经校准网络（CN）中的稀疏自注意力层校准。
- **算法流程（文字说明）**：
  - **训练**：从轨迹中采样输入 \( U_{t_i} \) 和目标 \( U_{t_o} \)，其中 \( \Delta t \) 在 \([0, t_h]\) 内随机选择。前向传播得到预测 \( \hat{U}_{t_o} \)，计算相对MSE损失，反向传播更新参数。
  - **推理**：给定输入 \( U_{t_i} \) 和目标时间 \( t_o \)，若 \( t_o - t_i > t_h \)，则计算商 \( q \) 和余数 \( r \)，先执行 \( q \) 次 \( t_h \) 步扭曲跳跃，再以余数 \( r \) 执行一次前向传播，最终得到预测。

## 3. 实验设计

- **数据集**：
  - **模拟挑战环境**：基于Navier-Stokes方程生成五种场景：S1（无噪声完整数据）、S2（乘性噪声）、S3（区域缺失传感器）、S4（随机50%稀疏）、S5（动态移动传感器）。各含100k训练轨迹、1k验证轨迹，每轨迹50步。
  - **基准Navier-Stokes数据集**：NS-3（ν=1e-3）、NS-4（ν=1e-4）、NS-5（ν=1e-5），不同湍流程度。
  - **真实数据**：
    - AirDelhi：印度德里PM2.5数据，包含基准（AD-B，30分钟间隔）、时间精细（AD-T，1分钟）、空间精细（AD-F，0.02 km²网格）。
    - Kuroshio Path：50年海洋再分析数据，预测黑潮路径纬度。
    - 降雨临近预报：德国气象局1km×1km、5分钟分辨率数据，预测未来60分钟降雨场。
- **基准方法**：FNO、OFormer、DINO、CORAL、AROMA、GNOT（部分数据集）。对于AirDelhi还对比了IDW、RF、XGBoost、ARIMA、N-BEATS、NSGP等。
- **评估指标**：MSE、Rel-MSE、RMSE。

## 4. 资源与算力

- **硬件**：大部分实验使用单张NVIDIA H100 80GB HBM3 GPU；最大模型变体（图4可扩展性评估）需要8张H100进行分布式训练。
- **训练时长**：论文未明确给出每实验的具体训练时长，但提供了训练步数（如模拟数据集50k步，基准Navier-Stokes 110k-150k步）和批次大小（256或100），可推断训练时间在数小时至数天范围内。

## 5. 实验数量与充分性

- **实验数量**：共涉及8大类任务/数据集，包括：
  - 5种模拟环境的预测性能对比（表1）
  - 3个Navier-Stokes基准的长程预测（表2）
  - AirDelhi三个变体的预测（表1）
  - 可扩展性分析（图4）：模型大小（7档）和数据集大小（3档）的缩放实验
  - 连续学习能力定性定量实验（图6）
  - 消融实验（表3）：逐一移除CEN、CN、Proj、TT四个模块，并测试多模块组合
  - Kuroshio路径预测（图7）
  - 降雨临近预报（图8）
  - 此外包含模型复杂度分析（附录L）。
- **充分性与公平性**：实验较为充分，覆盖了噪声、缺失、稀疏、动态传感器等多种真实挑战。基准方法均使用官方或合理复现设置，超参数在附录中详细列出，对比公平。但Kuroshio路径实验仅对比了四种特征工程/神经网络方法，未与更多SOTA神经网络模型对比，略有欠缺。

## 6. 主要结论与发现

- SCENT在所有模拟挑战场景（S1-S5）中均优于FNO、OFormer、CORAL、AROMA，尤其在动态移动传感器（S5）上表现突出（Rel-MSE 0.326 vs 次优0.525）。
- 在Navier-Stokes基准（NS-3、NS-4、NS-5）上，SCENT均达到最佳MSE/Rel-MSE，验证了扭曲-展开预测（WUF）在长程预测中的有效性。
- 在AirDelhi真实数据上，SCENT在AD-T和AD-F数据集上取得最佳RMSE；在AD-B基准上略逊于AROMA（44.2 vs 40.78），但定性结果（图5b）显示SCENT更好地捕捉PM2.5分布。
- 可扩展性实验表明，SCENT随模型参数和数据集大小增大而性能持续提升，且优于FNO，未出现明显的收敛饱和。
- 消融实验证实CEN、CN、线性投影和TT均对性能有贡献，去掉所有模块后Rel-MSE上升67.8%。

## 7. 优点

- **统一框架**：单一模型同时支持重建、插值和预测，无需分阶段训练。
- **处理不规则数据**：天然适应稀疏、噪声、缺失和移动传感器场景。
- **连续时间学习**：通过时间扭曲处理器和WUF策略实现任意时间步的预测，减少误差累积。
- **可扩展性**：稀疏注意力机制使模型对输入点数和模型参数均线性缩放，实验证实了数据量和模型容量增大时性能持续提升。
- **模块化设计**：CEN、CN、TT等组件均可独立消融，便于分析和改进。
- **计算复杂度分析**：附录中提供了与FNO、AROMA的Big-O对比，论证了SCENT在长程预测时的效率优势。

## 8. 不足与局限

- **实验覆盖不足**：
  - 对高维真实数据集（如3D气象场）未进行验证，仅限于2D或准2D数据。
  - Kuroshio路径实验对比方法较少，未与近期基于Transformer的时序模型（如PatchTST、TimesNet）比较。
  - 降雨临近预报中仅对比RainNet，缺乏与更多现有时空模型（如ConvLSTM、PredRNN）的对比。
- **偏差风险**：模拟数据基于Navier-Stokes方程，其平滑性和结构可能使模型获益，真实数据中更复杂的噪声模式（如非高斯、相关性噪声）未测试。
- **应用限制**：
  - 模型对可学习查询数量M和稀疏注意力组大小等超参数敏感，需针对不同数据集调优（附录C-G展示了不同超参数）。
  - 虽提出WUF策略，但时间地平线 \( t_h \) 需作为超参数设定，可能影响长程预测稳定性。
  - 大规模训练需8张H100，算力需求较高，对小团队不友好。
- **仅限监督学习**：未探索自监督或无监督场景，可能限制对无标注科学数据的泛化能力。

（完）
