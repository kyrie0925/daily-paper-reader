---
title: Three-Dimensional Trajectory Prediction with 3DMoTraj Dataset
title_zh: 基于3DMoTraj数据集的三维轨迹预测
authors: "Hao Zhou, Xu Yang, Mingyu Fan, Lu Qi, Xiangtai Li, Ming-Hsuan Yang, Fei Luo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=jkVH7nLzUR"
tags: ["query:ocean-obs"]
score: 8.0
evidence: 引入了来自海洋环境中无人水下航行器的三维轨迹数据集
tldr: 针对三维轨迹预测数据集缺失的问题，收集了来自海洋环境中无人水下航行器的3DMoTraj数据集，并提出了解耦轨迹预测与相关轨迹精炼的方法。该方法先解耦轴间相关性降低复杂度，再重新关联精炼，在多个指标上取得了优于现有方法的性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-jkvh7nlzur/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 800, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jkvh7nlzur/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1753, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jkvh7nlzur/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jkvh7nlzur/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1719, \"height\": 1031, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jkvh7nlzur/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1773, \"height\": 638, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jkvh7nlzur/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 854, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jkvh7nlzur/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1685, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jkvh7nlzur/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 903, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jkvh7nlzur/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1755, \"height\": 1287, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jkvh7nlzur/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1783, \"height\": 834, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jkvh7nlzur/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1785, \"height\": 832, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jkvh7nlzur/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1787, \"height\": 831, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jkvh7nlzur/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1788, \"height\": 829, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-jkvh7nlzur/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jkvh7nlzur/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1772, \"height\": 660, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jkvh7nlzur/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 863, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jkvh7nlzur/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 592, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jkvh7nlzur/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 519, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jkvh7nlzur/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 819, \"height\": 345, \"label\": \"Table\"}]"
motivation: 现有数据集未专门设计用于三维轨迹预测，缺乏来自真实海洋环境的UUV数据。
method: 提出解耦轨迹预测和相关轨迹精炼，先独立预测各轴再校正相关性。
result: 在3DMoTraj和其他数据集上，该方法均优于基线预测模型。
conclusion: 所提数据集和方法为三维轨迹预测研究提供了基准和有效方案。
---

## Abstract
With the growing interest in embodied and spatial intelligence, accurately predicting trajectories in 3D environments has become increasingly critical. However, no datasets have been explicitly designed to study 3D trajectory prediction. To this end, we contribute a 3D motion trajectory (3DMoTraj) dataset collected from unmanned underwater vehicles (UUVs) operating in oceanic environments. Mathematically, trajectory prediction becomes significantly more complex when transitioning from 2D to 3D. To tackle this challenge, we analyze the prediction complexity of 3D trajectories and propose a new method consisting of two key components: decoupled trajectory prediction and correlated trajectory refinement. The former decouples inter-axis correlations, thereby reducing prediction complexity and generating coarse predictions. The latter refines the coarse predictions by modeling their inter-axis correlations. Extensive experiments show that our method significantly improves 3D trajectory prediction accuracy and outperforms state-of-the-art methods. Both the 3DMoTraj dataset and the method are available at https://github.com/zhouhao94/3DMoTraj.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：随着具身智能和空间智能的发展，三维（3D）环境中的轨迹预测至关重要，例如用于无人水下航行器（UUV）的导航与避障。然而，当前公开的轨迹预测数据集绝大部分仅包含2D轨迹（如行人、车辆），缺乏专门为3D场景设计的轨迹数据集，导致3D轨迹预测研究进展缓慢。
- **背景与挑战**：从数学角度看，预测3D轨迹比2D轨迹复杂度显著增加：预测一个2D点等价于优化含5个参数的2D高斯分布，而预测3D点则需要优化含9个参数的3D高斯分布（增加近一倍）。这一高复杂度严重阻碍了多智能体3D场景的精准预测。

### 2. 方法论：核心思想、关键技术细节
- **核心思想**：采用“分而治之”策略，先解耦轴间相关性以降低复杂度，再重新建模相关性以精炼预测。
- **关键技术细节**：
  - **解耦轨迹预测**：以 LBEBM 为基线，将其单一解码器替换为三个独立的解码器，分别预测 x、y、z 轴上的未来轨迹。
    - 首先用三个独立的MLP关键点预测器对每个轴预测关键点（第3、6、9、12帧）。
    - 将关键点特征与全局编码特征拼接，再通过三个独立的MLP轨迹预测器生成各轴的粗预测轨迹。
    - 此步骤将每个3D点的参数从9个降至6个（优化三个1D高斯分布），降低复杂度。
  - **相关轨迹精炼**：设计 SCA-LSTM（状态相关与聚合LSTM）来建模粗预测的轴间相关性。
    - 采用中心LSTM提取跨轴总结特征，节点LSTM提取各轴特征。
    - **状态相关（SC）模块**：利用门控机制根据中心LSTM与节点LSTM的隐藏状态，更新节点LSTM的细胞状态，捕捉轴间依赖。
    - **状态聚合（SA）模块**：通过注意力机制和聚合门，将各节点LSTM的隐藏状态加权聚合，更新中心LSTM的细胞状态。
    - 精炼后，LSTM输出偏移量（offsets）对粗预测进行校正。
  - **损失函数**：结合基线LBEBM的损失，加入关键点损失、未来轨迹损失、偏移损失（均为MSE）。

### 3. 实验设计：数据集、benchmark与对比方法
- **数据集**：
  - **主要数据集**：3DMoTraj（自建），包含8个水下场景，每个场景3个UUV，共13000+帧。采用滑动窗口生成样本：8帧观察（4秒）→ 12帧预测（6秒）。采用留一法交叉验证（7训练+1测试）。
  - **泛化性验证**：使用2D行人轨迹数据集 ETH/UCY 和 SDD，将方法适配为2D版本测试。
- **基准与对比方法**：
  - 对比了11种方法：SSTGCNN、MSRL、FlowChain、PECNet、LBEBM、NPSN、TrajCLIP、CausalHTP、MS-TIP、MRGTraj、S-Implicit。所有方法均修改为接受3D输入、预测3D轨迹。
  - 评价指标：ADE（平均位移误差）和 FDE（最终位移误差）。
- **其他实验**：超参数分析（SC/SA迭代次数1-4、SCA-LSTM层数1-4）、消融实验（验证解耦和精炼组件的贡献）、模型效率分析（参数量、FLOPs、推理速度）。

### 4. 资源与算力
- 文中未明确说明训练使用的GPU数量和总训练时长。
- 仅在模型效率分析中提及在 **NVIDIA 2080 Ti GPU** 上测试推理速度（输入尺寸70×8×3），推理时间0.08秒（>12 FPS），参数量3.41M，FLOPs 0.24G。
- 未提供训练阶段的算力细节（如GPU型号数量、训练轮数对应的总时间等）。

### 5. 实验数量与充分性
- **实验组数**：
  - 主实验：在8个场景上分别测试并报告均值（表2）。
  - 超参数分析：2组（迭代数4种、层数4种，见表3、4）。
  - 消融实验：4种变体（表5）。
  - 泛化性实验：2个2D数据集（表6）。
  - 模型效率分析：6种方法对比（表7）。
  - 可视化案例：3个示例（图5）及失败案例（图7）。
- **充分性评价**：实验设计较全面，涵盖了性能对比、组件有效性验证、超参数调优、泛化能力及效率。对比方法涵盖近年主流2D和3D方法，采用标准留一法避免验证偏差，具有较好的公平性。但缺少对更多3D场景（如无人机、机器人）的验证，且未进行统计显著性检验。

### 6. 主要结论与发现
- 提出的方法在3DMoTraj数据集上 **全面优于所有对比方法**：平均ADE从0.68降至0.58（降低14.6%），FDE从1.22降至1.02（降低16.3%）。
- 解耦轨迹预测相比基线LBEBM提升19.0% ADE/FDE；加入SCA-LSTM精炼后进一步显著提升。
- SCA-LSTM优于普通LSTM（ADE/FDE提升12.1%/2.9%），证明建模轴间相关性的有效性。
- 在2D数据集ETH/UCY和SDD上，方法也能带来增益，表明解耦策略具有泛化性。
- 模型效率适中，推理速度>12 FPS，可满足实时需求。

### 7. 优点
- **数据集创新**：首次公开专门用于3D轨迹预测的数据集（3DMoTraj），包含多种水下场景、复杂的UUV运动和洋流扰动，并提供细粒度意图标注（运动、静态）。
- **方法新颖**：严谨的理论分析（附录A），将3D高斯分布分解为独立部分和相关性部分，并据此设计解耦+精炼框架，逻辑清晰。
- **性能显著**：在多个指标上大幅超越现有方法，尤其在z轴预测上改进明显（可视化验证）。
- **泛化性验证**：不仅在3D任务上成功，在2D任务上也有效，证明方法通用性。
- **公平对比**：调整所有对比方法适配3D输入，并统一数据增强策略为3D版本。

### 8. 不足与局限
- **实验覆盖有限**：仅基于UUV水下场景，未在无人机或机器人等其他3D环境中验证，可能限制泛化性。
- **模型缺陷**：对短时间内多次急弯的轨迹预测效果差（图7），说明简单的交互建模和缺乏3D环境先验（如点云地图）是瓶颈。
- **算力信息缺失**：未提供训练所需的具体GPU资源与时间，不利于复现和横向比较。
- **意图标注利用不足**：论文虽标注了运动/静态意图，但方法本身并未显式利用意图信息进行条件预测（仅作为数据集特性介绍），未验证意图信息对精度的贡献。
- **统计检验缺失**：未报告性能差异的统计显著性（如置信区间或p值），说服力略有不足。

（完）
