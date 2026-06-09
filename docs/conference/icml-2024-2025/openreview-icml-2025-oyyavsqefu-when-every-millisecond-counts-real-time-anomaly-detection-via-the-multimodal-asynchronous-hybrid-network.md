---
title: "When Every Millisecond Counts: Real-Time Anomaly Detection via the Multimodal Asynchronous Hybrid Network"
title_zh: 争分夺秒：基于多模态异步混合网络的实时异常检测
authors: "Dong Xiao, Guangyao Chen, Peixi Peng, Yangru Huang, Yifan Zhao, Yongxing Dai, Yonghong Tian"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=oYyaVSqEFu"
tags: ["query:anomaly-id"]
score: 7.0
evidence: 面向自动驾驶的实时异常检测
tldr: 现有自动驾驶异常检测忽略响应时间。本文提出多模态异步混合网络，结合事件相机的高时间分辨率和RGB相机的空间特征，通过异步图神经网络和CNN提取特征，在保证高精度的同时实现毫秒级响应。实验表明该方法在真实驾驶场景中大幅降低延迟且检测精度优于基线。该工作推动了实时异常检测在安全关键系统中的应用。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 860, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1769, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 861, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 857, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 854, \"height\": 242, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1769, \"height\": 1033, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1770, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1732, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1744, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1730, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1763, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1770, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1771, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1415, \"height\": 628, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyyavsqefu/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1249, \"height\": 1047, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1781, \"height\": 521, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1774, \"height\": 346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 867, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 864, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1777, \"height\": 414, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1774, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1709, \"height\": 514, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1359, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1321, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1097, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyyavsqefu/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1309, \"height\": 202, \"label\": \"Table\"}]"
motivation: 自动驾驶异常检测需同时满足高精度和低延迟，现有方法侧重精度。
method: 构建多模态异步混合网络，融合事件流（图神经网络）与RGB图像（CNN）特征。
result: 在驾驶数据集上延迟降至毫秒级，检测准确率保持领先。
conclusion: 实现了精度与速度的最佳权衡，适用于实时系统。
---

## Abstract
Anomaly detection is essential for the safety and reliability of autonomous driving systems. Current methods often focus on detection accuracy but neglect response time, which is critical in time-sensitive driving scenarios. In this paper, we introduce real-time anomaly detection for autonomous driving, prioritizing both minimal response time and high accuracy. We propose a novel multimodal asynchronous hybrid network that combines event streams from event cameras with image data from RGB cameras. Our network utilizes the high temporal resolution of event cameras through an asynchronous Graph Neural Network and integrates it with spatial features extracted by a CNN from RGB images. This combination effectively captures both the temporal dynamics and spatial details of the driving environment, enabling swift and precise anomaly detection. Extensive experiments on benchmark datasets show that our approach outperforms existing methods in both accuracy and response time, achieving millisecond-level real-time performance.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：自动驾驶中的异常检测对安全至关重要，但现有方法过度关注检测精度（如AUC、AP），却忽视了同样关键的因素——**响应时间**（response time）。在真实驾驶场景中，毫秒级的延迟足以决定制动或碰撞的差异。
- **核心痛点**：当前SOTA模型依赖深度神经网络，推理延迟较大；且检测延迟（从异常发生到系统识别的时间）未被纳入评估。这使得现有系统在安全关键场景中无法满足实时性要求。
- **本文目标**：提出**实时异常检测**（Real-Time Anomaly Detection）任务，同时优化高精度与极低响应时间。通过融合**事件相机**（event camera）的高时间分辨率（微秒级）与**RGB相机**的丰富空间信息，实现毫秒级响应和领先的检测准确率。

## 2. 方法论：核心思想、技术细节与算法流程

### 核心思想
- 构建**多模态异步混合网络**，将稀疏、异步的事件流通过**图神经网络**（GNN）处理，与CNN提取的RGB图像特征进行融合，并利用GRU和注意力机制捕捉时序依赖，最终实现快速、准确的异常检测。

### 关键技术细节

1. **多模态异步混合骨干网络**：
   - **图像分支**：使用ResNet（CNN）从RGB图像提取空间特征，并输出中间特征图。
   - **事件分支**：事件相机输出事件流$E = \{e_i = (x_i, t_i, p_i)\}$（坐标、时间戳、极性）。将事件建模为图$G=(V,E)$：每个事件作为一个节点，基于时空邻近构建边（最多16邻居）。使用**深度异步图神经网络（DAGr）** 进行特征提取，包含残差图卷积层和样条卷积：
     \[
     f'_i = W_c f_i + \sum_{j\in \mathcal{N}(i)} W(e_{ij}) f_j
     \]
     样条卷积支持通过查找表加速推理。
   - **特征融合**：将CNN特征$g_I(\hat{x}_i)$（通过双线性插值采样）逐节点拼接到GNN节点特征$f_i$：$f'_i = [f_i, g_I(\hat{x}_i)]$。该单向共享（仅有图像向事件分支共享）既提升稀疏事件场景下的特征表达，又保持计算高效。

2. **异常检测网络**（见图2）：
   - **对象级特征提取**：对每个检测到的对象$i$，从事件流中提取其边界框内的事件特征$o_{t,i}$（通过异步GNN），与RGB图像特征$g_{t,i}$拼接并经过全连接层降维得到$f_{t,i}$。
   - **时空关系学习**：使用两个独立的GRU分别处理边界框时序特征$b_{t,i}$和融合特征$f_{t,i}$，捕获时序动态：
     \[
     h_{b,t,i} = \text{GRU}(b_{t,i}, h_{b,t-1,i}), \quad h_{f,t,i} = \text{GRU}(f_{t,i}, h_{f,t-1,i})
     \]
   - **注意力机制**：对GRU输出的隐藏状态分别计算注意力权重$\alpha_b, \alpha_f$，突出潜在的异常对象。
   - **风险分数预测**：加权后的特征拼接并经过全连接层和softmax，输出每个对象的风险分数$s_{t,i}$。

3. **实时响应时间优化**：整体架构采用单阶段设计（共享特征提取），避免两阶段级联的额外延迟。异步GNN和样条卷积的查找表加速，使模型达到约579 FPS。

## 3. 实验设计

### 数据集与场景
- **ROL**（Karim et al., 2023）和**DoTA**（Yao et al., 2022）：两个常用的第一人称驾驶异常检测数据集，包含详细的时空标注（异常开始、结束、边界框等）。目前这些数据集不含真实事件模态，作者使用**v2e**工具将视频转换为模拟事件流，补充事件模态。
- **Rush-Out**子集：从ROL和DoTA中提取“突然冒出”场景（如行人/车辆盲区冲出），共1084个视频，专用于评估低延迟能力。
- 另外使用**DSEC**（真实事件驾驶数据集）进行V2E生成数据的验证实验（DSEC只含正常驾驶，无异常）。

### Benchmark与对比方法
- **对比方法**：包括ConvAE、ConvLSTMAE、AnoPred、FOL系列（IoU、Mask、STD、Ensemble）、MAMTCF、AM-Net、STFE、TTHF等；此外还对比了实时异常检测方法EfficientAD、AED-MAE、MOVAD。
- **评估指标**：
  - 传统指标：AUC、AP、AUC-Frame（帧级AUC）、mTTA（平均提前时间）。
  - **新指标**：**mResponse**（平均响应时间），通过多个阈值下检测延迟的平均值衡量实时性；FPS（帧率）。

### 实验设置
- RGB图像：ResNet50骨干，输入224×224，YOLOX检测器。
- 训练：RGB分支30 epochs，batch size 64，每epoch 1920图像；事件分支batch size 32，150k迭代（约2500轮遍历）。优化器Adam/AdamW，学习率0.001/2e-4，ReduceLROnPlateau调度。

## 4. 资源与算力

- 论文**未明确说明**训练所用的GPU型号、数量及具体训练时长。
- 但给出了计算量分析：每个事件处理需8.732 MFLOPs，显存占用23.5 GB。在Orin芯片上正常负载下可处理约560k events/s，峰值可达10M events/s，总计算量约87.32 TFLOPs（高速驾驶最坏情况）。作者指出Orin/Thor等芯片可支持部署，而Xavier/Parker在极端条件下可能受限。
- 推理速度：在测试中达到**579 FPS**（ROL数据集），响应时间mResponse为1.17秒（ROL）和1.21秒（DoTA）（注：此处为延迟指标，值越小越好）。

## 5. 实验数量与充分性

- **主要结果**：表1在ROL和DoTA两个数据集上对比了9种现有方法，涵盖了多种主流框架。
- **消融实验**：表2进行了10种配置的消融（逐步添加RGB、Event、GRU、Attention、BBox、Object模块、单阶段vs两阶段），验证各组件贡献。
- **网络深度/骨干对比**：表3调整层数（4/5/6层），表4对比CNN、Swin、ViT-B骨干。
- **两阶段变体**：表5和表6详细分析两阶段架构下不同输入的组合（BBox、Flow、同步/异步Event、GRU、Attention、RGB）。
- **实时方法对比**：表8与EfficientAD、AED-MAE、MOVAD对比。
- **合成事件验证**：表9用DSEC原始事件与V2E合成事件对比，差异很小。
- **极端场景**：表11在恶劣天气/低光下与STFE、TTHF对比。
- **灵敏度分析**：图11分析IoU阈值和置信度阈值的影响。
- **定性可视化**：多组异常场景的注意力分数曲线和帧级检测示例（图3-10）。
- **总计**：约10+组定量表格实验和大量定性分析。实验覆盖多个数据集、多种组件、多阈值参数，设计相对充分。
- **公平性**：对比方法均采用原文报告或复现的最佳设置，指标统一。但所有方法在ROL/DoTA上均使用v2e生成事件数据（作者指出当前无真实事件异常数据集），因此对比是公平的，但无法反映真实事件相机的性能差异。

## 6. 主要结论与发现

- 提出的方法在**检测精度**上达到或超越SOTA：例如在ROL上AUC 0.879（最高），AP 0.570（略低于TTHF的0.585但差距很小），AUC-Frame 0.736（仅次于TTHF）。
- 在**响应时间**上显著领先：mResponse为1.17秒（ROL），比第二名MAMTCF（1.88秒）低37.8%；FPS高达579，远超其他方法（大多<100 FPS）。
- 事件模态的异步GNN能够捕捉帧间快速运动，实现**帧间异常检测**（inter-frame anomaly detection），进一步降低检测延迟。
- 单阶段架构、共享特征和异步处理是实现毫秒级实时性的关键设计。
- 在极端光照（强逆光、夜间）和恶劣天气下，事件相机优势明显，模型仍保持较高准确率。
- 模型具备硬件部署可行性（分析Orin等芯片的算力匹配）。

## 7. 优点

- **任务定义创新**：正式提出“实时异常检测”概念，将响应时间作为关键评价维度，并设计mResponse指标进行量化。
- **多模态融合策略巧妙**：首次将事件相机用于自动驾驶异常检测，利用异步GNN保留事件的时间分辨率，并通过单向特征共享减少冗余计算。
- **高效架构设计**：
  - 单阶段检测（共享特征）避免两阶段级联延迟。
  - 样条卷积结合查找表实现极速推理。
  - 模块化设计允许灵活扩展（增加网络深度或替换骨干）。
- **实验全面性**：在多个数据集上进行了充分的消融和对比，并专门构建了Rush-Out极端场景和恶劣天气子集测试低延迟能力。
- **重视实用性**：分析了部署可行性（芯片算力、功耗、硬件同步误差），证明方法可部署于主流自动驾驶芯片。

## 8. 不足与局限

- **对象检测器依赖**：模型性能严重依赖前期对象检测的准确性。论文附录E指出在模糊或小目标场景下检测失败会导致整个异常检测失效（GRU无法积累有效时序特征）。这在实际部署中可能成为瓶颈。
- **事件数据为合成**：所有实验均使用v2e转换的合成事件流，而非真实事件相机（如DAVIS）。尽管论文用DSEC数据集验证了v2e的保真度，但合成数据无法完全模拟真实相机的噪声特性、带宽限制和校准误差，可能高估了实际性能。
- **泛化性不足**：实验仅涵盖两个数据集（ROL、DoTA）及衍生的Rush-Out子集，未在其他自动驾驶异常检测数据集（如D2-City、BDD100K异常子集）上验证。
- **未考虑多类别异常**：当前方法输出单一风险分数，未区分异常类型（如碰撞、横穿行人、落石等），可能限制后续决策系统。
- **误报分析缺失**：论文主要强调召回率和早期检测，但未深入分析误报率及其对系统可靠性的影响。高误报可能导致不必要的制动惊吓用户。
- **计算资源未明述**：训练时所使用的GPU型号、数量、训练时间缺失，影响可复现性评估。
- **极端场景负载上限**：在高速驾驶时事件爆发率可达10M events/s，计算量可达87 TFLOPs，可能超出低端芯片（如Xavier）的实时能力。论文虽提及芯片适配性，但未提供实际端到端延迟测试数据。

（完）
