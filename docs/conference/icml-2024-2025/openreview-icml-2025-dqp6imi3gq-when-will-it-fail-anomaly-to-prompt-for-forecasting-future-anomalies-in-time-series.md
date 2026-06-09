---
title: "When Will It Fail?: Anomaly to Prompt for Forecasting Future Anomalies in Time Series"
title_zh: 何时会失败？：从异常到提示的时间序列未来异常预测
authors: "Min-Yeong Park, Won-Jeong Lee, Seong Tae Kim, Gyeong-Moon Park"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Dqp6IMI3gQ"
tags: ["query:anomaly-id"]
score: 8.0
evidence: 通过异常感知预测和合成异常提示预测时间序列中的未来异常
tldr: 时间序列异常预测（预测未来异常发生的时间点）是一个重要但探索不足的问题。本文提出A2P框架，包含异常感知预测（AAF）和合成异常提示（SAP）两个模块。AAF学习异常间关系，SAP合成异常提示使模型关注异常模式。实验表明，该框架在多个数据集上能精准预测未来异常时间点，填补了异常预测领域的空白。
source: ICML-2025-Accepted
selection_source: conference_retrieval
motivation: 现有方法无法精确预测时间序列中未来异常的发生时刻。
method: 提出A2P框架，包含异常感知预测和合成异常提示，学习异常间关系。
result: 在多个数据集上实现了对未来异常时间点的有效预测。
conclusion: 该框架为时间序列异常预测提供了新解决方案。
---

## Abstract
Recently, forecasting future abnormal events has emerged as an important scenario to tackle realworld necessities. However, the solution of predicting specific future time points when anomalies will occur, known as Anomaly Prediction (AP), remains under-explored. Existing methods dealing with time series data fail in AP, focusing only on immediate anomalies or failing to provide precise predictions for future anomalies. To address AP, we propose a novel framework called Anomaly to Prompt (A2P), comprised of Anomaly-Aware Forecasting (AAF) and Synthetic Anomaly Prompting (SAP). To enable the forecasting model to forecast abnormal time points, we adopt a strategy to learn the relationships of anomalies. For the robust detection of anomalies, our proposed SAP introduces a learnable Anomaly Prompt Pool (APP) that simulates diverse anomaly patterns using signal-adaptive prompt. Comprehensive experiments on multiple real-world datasets demonstrate the superiority of A2P over state-of-the-art methods, showcasing its ability to predict future anomalies.

---

## 论文详细总结（自动生成）

好的，以下是根据您提供的论文内容生成的中文总结。

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在许多现实场景（如医疗监护、工业系统维护）中，不仅需要检测已发生的异常，更需要**提前预测未来何时会发生异常**，即 Anomaly Prediction（AP）任务。现有时间序列预测模型只关注信号本身，忽略异常重要性；异常检测模型只处理过去信号。两者简单组合会导致预测信号“平滑”掉异常，使得后续检测失效。
- **整体含义**：本文首次提出针对 AP 任务的解决方案，旨在基于历史信号，预测未来特定时间点是否异常。

## 2. 论文提出的方法论

- **核心思想**：将异常知识融入预测和检测过程。通过预训练一个异常感知预测网络（AAF）和一个人工合成异常提示池（SAP），使模型学会在预测时保留异常特征，并在检测时增强对异常的敏感性。
- **关键技术细节**：
  - **统一共享骨干网络**：采用 Transformer 作为共享骨干，分别连接预测头（ΘF）和重建检测头（ΘAD），同时学习预测和表示。
  - **异常感知预测（AAF）**：预训练一个跨注意力网络，学习输入信号中异常特征与未来异常标签之间的关系。输入信号经过随机异常注入（季节/趋势/形状等类型），网络输出异常概率，使用 MSE 损失训练。
  - **合成异常提示（SAP）**：引入可学习的异常提示池（APP），包含 M 个键-提示对。通过特征提取器获取输入信号的特征查询，选择最匹配的 N 个提示，将其在嵌入层拼接（信号自适应），使原本正常的嵌入变成异常嵌入，用于后续重建训练。同时使用散度损失（KL 散度 + 键拉近）迫使合成异常特征与正常特征分离。
  - **主训练**：冻结预训练好的 AAF 和 APP，优化共享骨干。预测损失使用 AAF 输出的异常概率加权 MSE（对异常时刻赋予更高权重）；重建损失包括原始信号重建和合成异常信号重建为正常信号两项。
- **公式/算法流程**：预训练阶段损失 L_PT = λ_AAF L_AAF + λ_D L_D + λ_F L_F；主训练阶段损失 L_MT = λ_R L_R + λ_AF L_AF。所有 λ 默认设为 1。

## 3. 实验设计

- **数据集**：4 个真实世界多变量时间序列数据集：MBA（心电异常）、Exathlon（Spark 系统）、SMD（服务器指标）、WADI（水分配系统）。另外在附录还测试了 MSL、PSM、SWaT、SMAP。
- **基准**：采用 5 种 SOTA 预测模型（PatchTST、MICN、GPT2、iTransformer、FITS）与 3 种 SOTA 异常检测模型（AnomalyTransformer、DCDetector、CAD）的组合作为基线；附录中还测试了 TranAD、BeatGAN、DiffusionAD。
- **评价指标**：主要使用 F1-score（无 Point Adjustment，但引入容忍窗口 t=50，即允许检测结果前后 50 步误差）。此外还报告了 VUS-PR / VUS-ROC。
- **超参数**：输入长度 100，输出长度 100/200/400，提示池大小 10，提示数量 3，提示 token 长度 5，骨干 3 层 Transformer，隐藏维度 256。

## 4. 资源与算力

- **GPU 型号与数量**：单张 NVIDIA RTX 3090。
- **训练时长**：每个数据集训练时间最多 1 小时（WADI 数据集）。共训练 5 个 epoch，batch size 16。
- **其他**：论文比较了 GFLOPs 和参数量，指出 A2P 比基线（PatchTST+AnomalyTransformer）训练时 GFLOPs 略高，但由于共享骨干，总参数量更低，且推理时无额外开销。

## 5. 实验数量与充分性

- **实验组数**：
  - 主实验结果（表 1）：4 个数据集 × 3 种输出长度 × 3 个随机种子，对比 5×3=15 种基线组合。
  - 消融实验：AAF/SAP 消融、预训练损失消融、共享骨干消融、异常概率加权消融、标签损失类型消融（MSE vs BCE）。
  - 额外数据集（表 10）、额外基线（表 12）、VUS 指标（表 11）、不同容忍窗口（图 8）、超参数敏感性（图 10）。
  - 定性结果图（图 6、图 9）和计算复杂度对比（图 7）。
- **充分性评价**：实验较为充分，覆盖了不同领域、不同序列长度、多种基线组合、多种评价指标。消融实验验证了每个模块的有效性。但缺少对异常注入方式选择的消融（仅引用了一种方案），且仅在 4 个主要数据集上深度分析，部分数据集（如 WADI）只有 27 个异常段，样本量偏少。

## 6. 论文的主要结论与发现

- A2P 在 AP 任务上全面超越所有基线组合，在 MBA、Exathlon、SMD、WADI 上平均 F1 比最佳基线高出约 5-10 个点。
- AAF 和 SAP 均有独立贡献，两者结合效果最好。
- 预训练损失 L_F 和 L_D 均能提升性能，其中 L_D（散度损失）单独带来显著提升（MBA 上约 24%）。
- 共享骨干比分开训练效果好（F1 平均提升 5 个点）。
- 使用异常概率加权的预测损失优于普通 MSE 损失。
- 定性结果显示 A2P 预测的信号能保留异常尖峰，而基线平滑掉异常。

## 7. 优点

- **任务创新**：首次精确定义并解决了“预测未来异常时刻”的 AP 任务，比仅预测“近期是否有异常”更实用。
- **方法论新颖**：提出 AAF 学习异常关联、SAP 利用可学习提示池合成异常，两者均是本文独创。
- **统一框架**：共享骨干降低了参数量，同时实现预测和检测，且推理时无需多余模块，效率高。
- **实验扎实**：多种数据集、多种评价指标、充分的消融，且开源代码。
- **性能优越**：在多个场景下显著超越 naive 组合基线，尤其长序列预测（Lout=400）提升更大。

## 8. 不足与局限

- **异常模拟依赖**：AFP 中的异常注入基于预训练重建误差和特定类型，可能无法覆盖真实世界所有异常模式；SAP 的提示池大小 M 需要手动设定，过大可能过拟合。
- **数据集限制**：主要数据集异常比例和长度差异大（如 WADI 只有 27 个异常段），结果可能受噪声影响；未在极大规模（如 1000 维）或极长输出序列（如 1000）上验证。
- **计算开销**：预训练阶段需要额外训练 AAF 和 APP，相比直接端到端训练更复杂；但作者已说明训练时间可接受。
- **未讨论迁移性**：未展示在无标签数据或少标签情况下的表现，实际应用中异常标签可能稀缺。
- **超参数敏感性**：部分数据集（MBA）对提示池大小 M 较敏感，需调参。

（完）
