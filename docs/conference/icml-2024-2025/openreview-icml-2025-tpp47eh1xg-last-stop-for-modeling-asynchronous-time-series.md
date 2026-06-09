---
title: LAST SToP for Modeling Asynchronous Time Series
title_zh: LAST SToP：异步时间序列建模的新型提示设计
authors: "Shubham Gupta, Thibaut Durand, Graham W. Taylor, Lilian Bialokozowicz"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=TpP47EH1xG"
tags: ["query:anomaly-id"]
score: 7.0
evidence: 基于LLM的异步时间序列异常检测，采用随机软提示
tldr: 异步时间序列（事件时间戳不规则）在真实世界中常见，但现有LLM方法未充分利用其自然语言事件描述。本文提出针对异步时间序列的提示设计，利用事件描述中的语言信息，并引入随机软提示机制以提升性能。方法可扩展至异常检测和缺失值推算等任务。实验表明，该方法在多个领域优于现有基线。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tpp47eh1xg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 868, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpp47eh1xg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 828, \"height\": 231, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpp47eh1xg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1730, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpp47eh1xg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 852, \"height\": 299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpp47eh1xg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 846, \"height\": 742, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpp47eh1xg/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 689, \"height\": 816, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpp47eh1xg/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 842, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpp47eh1xg/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1512, \"height\": 457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpp47eh1xg/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1766, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpp47eh1xg/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1659, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpp47eh1xg/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1410, \"height\": 699, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpp47eh1xg/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1755, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpp47eh1xg/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1543, \"height\": 491, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tpp47eh1xg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 1089, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpp47eh1xg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1769, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpp47eh1xg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1359, \"height\": 472, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpp47eh1xg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1358, \"height\": 471, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpp47eh1xg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1253, \"height\": 472, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpp47eh1xg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1780, \"height\": 389, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpp47eh1xg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1781, \"height\": 391, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpp47eh1xg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1782, \"height\": 648, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpp47eh1xg/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1772, \"height\": 1279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpp47eh1xg/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1766, \"height\": 1352, \"label\": \"Table\"}]"
motivation: 异步时间序列的事件描述丰富，但现有LLM方法未能充分利用其自然语言信息。
method: 提出随机软提示和针对异步时间序列的提示设计，利用LLM世界知识。
result: 在异常检测和推算任务上性能显著提升。
conclusion: 该方法扩展了LLM在异步时间序列分析中的应用。
---

## Abstract
We present a novel prompt design for Large Language Models (LLMs) tailored to **Asynchronous Time Series**. Unlike regular time series, which assume values at evenly spaced time points, asynchronous time series consist of timestamped events occurring at irregular intervals, each described in natural language. Our approach effectively utilizes the rich natural language of event descriptions, allowing LLMs to benefit from their broad world knowledge for reasoning across different domains and tasks. This allows us to extend the scope of asynchronous time series analysis beyond forecasting to include tasks like anomaly detection and data imputation. We further introduce **Stochastic Soft Prompting**, a novel prompt-tuning mechanism that significantly improves model performance, outperforming existing finetuning methods such as QLORA. Through extensive experiments on real-world datasets, we demonstrate that our approach achieves state-of-the-art performance across different tasks and datasets.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：异步时间序列（事件以不规则时间间隔发生，且事件描述为自然语言）的传统建模方法（如时间点过程 TPP）存在多个局限：① 只能处理少量预定义的类别；② 忽略事件间的交互；③ 丢失事件描述中的自然语言语义；④ 扩展到其他任务（异常检测、缺失值补全）需要大量理论工作。
- **研究动机**：现有 LLM 在时间序列上的应用主要针对规则采样的数值序列，未充分利用异步时间序列中事件描述的语言信息。本文旨在利用 LLM 的世界知识和语言理解能力，实现对异步时间序列的灵活建模，并扩展至多种下游任务。
- **整体含义**：提出 LASTS 框架，将异步时间序列编码为文本提示，使 LLM 能够基于自然语言推理，实现预测、异常检测和缺失值补全，并引入随机软提示（StoP）进一步提升性能。

## 2. 论文提出的方法论

- **核心思想**：
  - 将异步时间序列表示为 **`(时间间隔, 事件描述)`** 的文本序列，作为 LLM 的输入提示。
  - 通过 **提示结构**（系统提示 + 用户提示 + 助手提示）明确任务（预测/异常检测/补全）。
  - 提出 **随机软提示（Stochastic Soft Prompting, StoP）**，一种参数高效的微调方法。

- **关键技术细节**：
  - **LASTS 提示结构**：
    - 系统提示：描述任务和数据集。
    - 用户提示：事件序列，格式为 `(时间间隔, 事件描述)`，用逗号分隔。
    - 助手提示：训练时包含正确答案，推理时由 LLM 生成。
  - **随机软提示（StoP）**：
    - 在标准软提示（SP）基础上，训练时对每个批次**随机采样一个前缀长度 l**，仅使用软提示的前 l 个 token 进行前向和反向传播。
    - 推理时使用全部长度的软提示（如 400 个 token）。
    - 灵感：类似 Dropout、Stochastic Depth 和 Matryoshka Representations。
  - **对比方法**：LoRA/QLoRA、标准软提示（SP），均与 LASTS 提示结合使用。

- **算法流程（文字说明）**：
  1. 将异步时间序列事件转换为文本提示（系统提示 + 用户提示）。
  2. 对于每个训练批次，从均匀分布采样前缀长度 l。
  3. 将软提示截断为前 l 个连续 token，与文本提示拼接后送入 LLM。
  4. 计算下一 token 预测损失，仅更新软提示参数（冻结 LLM 主干）。
  5. 推理时使用完整软提示进行生成。

## 3. 实验设计

- **数据集**：
  - **文本动作数据集（3 个）**：Breakfast（177 类烹饪动作）、MultiTHUMOS（65 类人类活动）、EPIC-KITCHENS-100（约 20K 类自然语言描述的动作，复杂且丰富）。
  - **标准时间点过程数据集（5 个）**：Amazon（16 类）、Retweet（3 类）、Taxi（10 类）、Taobao（20 类）、StackOverflow（22 类）——这些数据集只有事件类别索引，无文本描述，用于验证方法通用性。

- **任务**：预测（下一个事件）、异常检测（识别序列中被替换的异常事件）、缺失值补全（预测被遮掩的事件）。

- **基准方法**：
  - 随机基线、Chronos（时间序列基础模型）、LLMTime、LLM Processes（基于 LLM 的时序预测方法）。
  - 五种经典 TPP 模型：RMTPP、NHP、SAHP、THP、AttNHP。

- **评估指标**：事件类型预测用 Macro-F1（因类别严重不平衡），时间预测用 MAE 或 RMSE。

## 4. 资源与算力

- **文中未明确说明**具体 GPU 型号、数量或训练总时长。
- 提及的配置：使用 **Llama-3-8B-Instruct** 作为骨干，QLoRA 的秩为 4，软提示长度为 400（约 1.6M 可训练参数，占 LLM 参数的 0.02%）。训练时 **StoP 比标准 SP 快约 25%**。

## 5. 实验数量与充分性

- **大量实验，覆盖多层维度**：
  - 三个任务 × 三个文本数据集（表 1），并报告 Macro-F1 和 MAE。
  - 五个标准 TPP 数据集上的预测任务（表 2），对比五种 TPP 模型。
  - 零样本与少样本分析（k=1,2,5,7,10，图 12，表 9）。
  - 模型规模缩放实验（1B, 3B, 8B，图 7/11）。
  - 消融实验：StoP vs 随机选取 token 的变体（图 10）；提示结构消融（事件顺序、时间表示、是否使用世界知识，附录 A.4）。
  - 提示分析：t-SNE 可视化、余弦相似度、前缀有效性（图 5、6、13）。
- **充分性判断**：实验设计严格，涵盖了多种任务、数据集、基线方法和消融分析，结果客观、公平。尤其是异常检测和缺失值补全任务首次在异步时间序列上下文中被 LLM 处理，对比充分。

## 6. 论文的主要结论与发现

- **LAStS 零样本性能显著优于其他零样本方法（Chronos、LLMTime、LLM Processes）**，尤其在具有丰富文本描述的 EPIC-KITCHENS 数据集上优势明显。
- **随机软提示（StoP）在所有任务和数据集上均优于标准软提示和 QLoRA**，平均 Macro-F1 提升约 12–13%，MAE 略有改善。StoP 不仅提升性能，还加速训练。
- **StoP 学习到粗到细的结构**：早期 token 编码任务级信息，后期 token 细化；任意前缀均可作为独立提示，便于资源受限部署。
- **与 TPP 模型对比**：在事件类型预测上全面领先（18 项评价中 13 项最优，17 项前二），但时间预测在某些数据集（如 Amazon）上不如 TPP 模型，因其缺少时间分布先验。
- **模型规模越大，效果越好**，说明 StoP 可随 LLM 发展持续受益。

## 7. 优点

- **创新性**：首个将 LLM 用于异步时间序列多任务（预测、异常检测、缺失值补全）的工作，突破了传统 TPP 只能做预测的限制。
- **提示设计巧妙**：利用自然语言事件描述，保留语义信息；提示结构简单通用。
- **随机软提示（StoP）高效且有效**：仅增加极少量参数，训练速度快，并能学习到具有结构化的提示向量，易于解释和部署。
- **实验全面**：覆盖多种数据类型（文本 vs 类别索引）、多个任务、多个基线，消融深入，结果可靠。
- **报告了模型大小缩放规律**，表明方法具有扩展性。

## 8. 不足与局限

- **时间预测精度不如强 TPP 模型**：由于没有对时间分布做显式建模，在时间预测上存在差距，尤其在 Amazon 等数据上（类别混杂导致时间模式复杂）。
- **对 LLM 依赖性强**：性能高度依赖 LLM 的预训练知识和推理能力，可能继承 LLM 的偏见或不准确性；在非文本（仅有索引）的数据上，优势减弱。
- **计算资源需求较高**：虽然参数高效，但仍需部署 8B 参数级 LLM 进行推理，在资源受限场景可能受限。
- **实验未覆盖高风险应用**：如医疗、金融等需要严格验证的领域未包含，文中虽提及隐私和伦理，但未做具体评估。
- **缺失对时间预测失败原因的深入分析**：仅猜测缺乏先验，未尝试混合模型进行改进。

（完）
