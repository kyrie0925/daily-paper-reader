---
title: "KAN-AD: Time Series Anomaly Detection with Kolmogorov–Arnold Networks"
title_zh: KAN-AD：基于Kolmogorov-Arnold网络的时间序列异常检测
authors: "Quan Zhou, Changhua Pei, Fei Sun, HanJing, Zhengwei Gao, Haiming Zhang, Gaogang Xie, Dan Pei, Jianhui li"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=LWQ4zu9SdQ"
tags: ["query:anomaly-id"]
score: 9.0
evidence: 基于KAN的时间序列异常检测方法
tldr: 时间序列异常检测通常使用预测模型，但这类模型容易过拟合微小波动。本文提出KAN-AD方法，利用Kolmogorov-Arnold网络将时间序列建模为光滑单变量函数的叠加，从而聚焦于正常模式的平滑局部特征。实验表明该方法能有效抵抗局部扰动，在多个基准数据集上获得更优的检测性能。这一工作为时间序列异常检测提供了新的视角，并展示了KAN在时序建模中的潜力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-lwq4zu9sdq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 865, \"height\": 109, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwq4zu9sdq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwq4zu9sdq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 555, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwq4zu9sdq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1163, \"height\": 614, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwq4zu9sdq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 871, \"height\": 275, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwq4zu9sdq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwq4zu9sdq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 438, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwq4zu9sdq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 361, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwq4zu9sdq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 572, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwq4zu9sdq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 569, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lwq4zu9sdq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 575, \"height\": 387, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-lwq4zu9sdq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 783, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwq4zu9sdq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1745, \"height\": 541, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwq4zu9sdq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 743, \"height\": 427, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwq4zu9sdq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 800, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwq4zu9sdq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 787, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lwq4zu9sdq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1833, \"height\": 417, \"label\": \"Table\"}]"
motivation: 现有时间序列异常检测方法基于预测模型易过拟合微小波动，需更关注正常行为的平滑局部模式。
method: 使用Kolmogorov-Arnold网络将时间序列建模为光滑单变量函数的组合，以拟合正常模式并抵抗局部干扰。
result: 在多个基准数据集上，KAN-AD比现有方法取得更好的检测性能，且对局部扰动鲁棒。
conclusion: KAN-AD有效利用函数光滑性提升异常检测准确率，为时序异常检测提供新范式。
---

## Abstract
Time series anomaly detection (TSAD) underpins real-time monitoring in cloud services and web systems, allowing rapid identification of anomalies to prevent costly failures. Most TSAD methods driven by forecasting models tend to overfit by emphasizing minor fluctuations. Our analysis reveals that effective TSAD should focus on modeling "normal" behavior through smooth local patterns. To achieve this, we reformulate time series modeling as approximating the series with smooth univariate functions. The local smoothness of each univariate function ensures that the fitted time series remains resilient against local disturbances. However, a direct KAN implementation proves susceptible to these disturbances due to the inherently localized characteristics of B-spline functions. We thus propose KAN-AD, replacing B-splines with truncated Fourier expansions and introducing a novel lightweight learning mechanism that emphasizes global patterns while staying robust to local disturbances. On four popular TSAD benchmarks, KAN-AD achieves an average 15% improvement in detection accuracy (with peaks exceeding 27%) over state-of-the-art baselines. Remarkably, it requires fewer than 1,000 trainable parameters, resulting in a 50% faster inference speed compared to the original KAN, demonstrating the approach's efficiency and practical viability.

---

## 论文详细总结（自动生成）

# 论文总结：KAN-AD: Time Series Anomaly Detection with Kolmogorov–Arnold Networks

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有基于预测模型的时间序列异常检测（TSAD）方法容易过拟合局部微小波动（如局部峰值和跌落），导致在训练数据含有噪声时检测性能显著下降。作者指出，有效的TSAD应当关注正常行为的**平滑局部模式**，而非精确拟合每个细节。
- **整体含义**：本文提出一种新的TSAD范式，利用Kolmogorov–Arnold表示定理将时间序列建模为光滑单变量函数的组合，从而实现对局部扰动的鲁棒性，同时保持高效性。

## 2. 论文提出的方法论

### 2.1 核心思想
- 基于观察：正常序列比异常序列具有更强的局部平滑性。通过将时间序列近似为光滑单变量函数的线性组合，过滤掉局部噪声，只保留正常模式。

### 2.2 关键技术细节
1. **替换B样条为截断傅里叶展开**：原始KAN使用B样条作为单变量函数，其局部化特性易过拟合异常。KAN-AD改用傅里叶级数（有限N项），具有良好的局部光滑性和全局周期性建模能力。
2. **引入周期增强单元**：为了弥补有限N项傅里叶级数无法建模小于1/N周期的缺陷，额外加入周期性三角函数（基于窗口索引的位置编码），与原始傅里叶级数共同构成多周期单变量函数集。
3. **常数项消除模块**：通过一阶差分预处理消除时间窗口均值的趋势波动，使模型专注于估计傅里叶系数，避免常数项A0对系数拟合的干扰。
4. **轻量级学习机制**：将正常模式重建转化为对单变量函数系数的估计，使用堆叠的1D卷积网络学习系数，参数极少（<1000）。

### 2.3 算法流程（文字说明）
- **映射阶段**：将输入时间窗口通过固定单变量函数族（原始值X、傅里叶级数Sn、周期增强Pn）映射到高维特征空间。
- **归约阶段**：使用堆叠1D卷积（含批归一化、GELU激活）对特征进行系数估计，并通过残差连接和降维卷积得到当前窗口的正常模式近似。
- **投影阶段**：通过单层线性MLP将当前窗口的正常模式映射到下一个时间点的预测值，与真实观测比较得到异常分数。

## 3. 实验设计

### 3.1 数据集
- **单变量时间序列（UTS）**：KPI、TODS、WSD、UCR（四个公开基准），涵盖互联网服务指标、合成数据、Web服务器指标、多领域真实异常。
- **多变量时间序列（MTS）**：SMD、MSL、SMAP、SWaT、PSM（五个常见基准）。

### 3.2 Benchmark与对比方法
- 对比了10种SOTA方法，包括：LSTMAD、FCVAE、SRCNN、FITS、TimesNet、OFA、TranAD、SubLOF、Anomaly Transformer、SAND、原始KAN。
- 评价指标：Best F1、Event F1、Delay F1、AUPRC，并采用点调整策略和事件级调整以避免性能膨胀。

## 4. 资源与算力

- 论文中**未明确说明GPU型号、数量或训练时长**，但提供了UCR数据集上的效率对比（Table 3）：
  - KAN-AD GPU时间为42秒，CPU时间为36秒，参数数量274。
  - 相比之下，原始KAN GPU时间66秒，参数1360；其他方法参数从几百到数千万不等。
- 可以推断KAN-AD在单GPU上即可快速完成训练，但具体硬件配置未提及。

## 5. 实验数量与充分性

- **实验组数充足**：包括4个UTS数据集的主实验、5个MTS数据集扩展实验、超参数敏感性实验、消融研究（常数项消除、单变量函数类型选择、函数分解机制贡献）、对训练数据中异常比例的鲁棒性实验、以及案例研究。
- **充分性与公平性**：所有基线方法均按原文超参数设置并复现；KAN-AD在不同随机种子下重复5次报告均值和标准差；消融实验覆盖了各设计组件；鲁棒性实验通过合成数据控制异常比例。整体设计客观、全面。

## 6. 论文的主要结论与发现

- KAN-AD在所有UTS数据集上平均Event F1提升15%，最高超过27%（TODS数据集上提升27%）。
- 参数效率极高：仅274个参数（比TranAD少25%），推理速度比原始KAN快50%。
- 对训练数据中的异常比例鲁棒：在异常比例从10%到40%的情况下，F1e保持稳定，而其他方法（如LSTMAD、TimesNet）显著下降。
- 在MTS场景中，通过通道独立策略取得平均Best F1 0.9076，超越所有对比方法，参数仅4491个（MSL上）。
- 傅里叶级数优于泰勒级数、切比雪夫多项式和B样条。

## 7. 优点

- **方法创新**：将KAN与傅里叶级数结合，克服B样条过拟合问题，设计周期增强和常数项消除模块，理论新颖且实用。
- **极致轻量**：参数极少（<1000），便于部署在资源受限环境。
- **鲁棒性强**：对训练数据中的异常高度鲁棒，解决了实际生产环境中训练数据不干净的难题。
- **实验全面**：覆盖单变量和多变量场景，消融研究充分，指标选取合理（Event F1避免性能膨胀）。
- **开源代码**：提升可复现性。

## 8. 不足与局限

- **实验局限性**：
  - 主要实验聚焦于单变量时间序列，多变量扩展仅采用简单的通道独立策略，未探索通道间交互关系。
  - 未在超大规模（如百万级时间序列）或真实云监控系统上验证可扩展性。
  - 未提供GPU型号和训练时长等详细资源消耗数据，不利于精确复现。
- **方法局限**：
  - 假设正常模式具有局部平滑性，对于高频正常波动（如快速变化但非异常的模式）可能效果受限。
  - 有限N项傅里叶级数虽配合周期增强，但在处理极不规则周期时仍有风险。
  - 常数项消除依赖一阶差分，可能丢失趋势信息（尽管作者认为这种损失无碍于异常检测）。
- **偏差风险**：UCR数据集在训练集中无异常样本，与其他数据集（含噪训练）的评估标准可能不一致；Event F1将异常段视为事件，可能低估长异常段的时序检测需求。

（完）
