---
title: Causality-Aware Contrastive Learning for Robust Multivariate Time-Series Anomaly Detection
title_zh: 因果感知对比学习用于鲁棒多元时间序列异常检测
authors: "HyunGi Kim, Jisoo Mok, Dongjun Lee, Jaihyun Lew, Sungjae Kim, Sungroh Yoon"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=EGpueKe6TP"
tags: ["query:anomaly-id"]
score: 8.0
evidence: 因果感知对比学习用于鲁棒多元时间序列异常检测
tldr: 针对现有多元时间序列异常检测方法对变量间因果关系利用不足导致鲁棒性欠缺的问题，本文提出因果感知对比学习框架CAROTS。该方法通过两种数据增强器分别生成保持和破坏因果关系的样本，作为正负样本进行对比学习，从而学习到更鲁棒的特征表示。实验表明，CAROTS在多个基准数据集上显著提升了异常检测的鲁棒性和准确性，为时间序列异常检测提供了新的因果视角。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-egpueke6tp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1781, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-egpueke6tp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1787, \"height\": 574, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-egpueke6tp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 867, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-egpueke6tp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 869, \"height\": 265, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-egpueke6tp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1788, \"height\": 889, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-egpueke6tp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 965, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-egpueke6tp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1377, \"height\": 440, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-egpueke6tp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 837, \"height\": 476, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-egpueke6tp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 795, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-egpueke6tp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 857, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-egpueke6tp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 868, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-egpueke6tp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1466, \"height\": 403, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-egpueke6tp/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1767, \"height\": 970, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-egpueke6tp/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 818, \"height\": 550, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-egpueke6tp/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1726, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-egpueke6tp/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 822, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-egpueke6tp/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 582, \"height\": 352, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-egpueke6tp/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 618, \"height\": 312, \"label\": \"Table\"}]"
motivation: 多元时间序列异常检测中，变量间因果关系利用不足导致检测不够鲁棒。
method: 提出CAROTS流程，通过两个数据增强器获取因果保持和干扰样本，进行对比学习。
result: 在多个基准数据集上提升了异常检测的鲁棒性和性能。
conclusion: 将因果关系纳入对比学习是提升时间序列异常检测的有效途径。
---

## Abstract
Utilizing the complex inter-variable causal relationships within multivariate time-series provides a promising avenue toward more robust and reliable multivariate time-series anomaly detection (MTSAD) but remains an underexplored area of research. This paper proposes Causality-Aware contrastive learning for RObust multivariate Time-Series (CAROTS), a novel MTSAD pipeline that incorporates the notion of causality into contrastive learning. CAROTS employs two data augmentors to obtain causality-preserving and -disturbing samples that serve as a wide range of normal variations and synthetic anomalies, respectively. With causality-preserving and -disturbing samples as positives and negatives, CAROTS performs contrastive learning to train an encoder whose latent space separates normal and abnormal samples based on causality. Moreover, CAROTS introduces a similarity-filtered one-class contrastive loss that encourages the contrastive learning process to gradually incorporate more semantically diverse samples with common causal relationships. Extensive experiments on five real-world and two synthetic datasets validate that the integration of causal relationships endows CAROTS with improved MTSAD capabilities. The code is available at https://github.com/kimanki/CAROTS.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：多变量时间序列异常检测（MTSAD）在工业控制、医疗健康等关键系统中至关重要。现有方法（如基于重构或对比学习的方法）主要关注数据值或分布的表面差异，而忽略了变量间复杂的因果依赖关系。当正常波动（如热浪导致空调长时间开启）与真正异常（因果关系被破坏）表现相似时，这些方法容易产生误报，鲁棒性不足。
- **核心问题**：如何利用变量间稳定的因果关系来区分正常变异和真正的异常？异常通常表现为因果关系的破坏（例如，损坏的空调不随温度变化而开关）。作者假设正常数据中的因果关系在时间上保持一致，而异常会打破这种一致性。
- **整体含义**：将因果关系引入对比学习框架，可以提升异常检测的鲁棒性和准确性，为MTSAD提供新的因果视角。

## 2. 方法论

### 核心思想
提出CAROTS框架，通过两个数据增强器分别生成“因果保持样本”（正常变化）和“因果干扰样本”（模拟异常），然后利用对比学习训练编码器，使正常和异常样本在潜在空间中基于因果关系分离。同时引入“相似性过滤单类对比损失”（SOC Loss）来逐步纳入更多语义多样的正样本。

### 关键技术细节
1. **因果发现**：使用基于预测的因果发现模型（如CUTS+）从正常训练数据中学习因果矩阵A和因果函数集{f^i}。该模型通过最小化预测均方误差和稀疏正则化得到A。
2. **因果保持增强器（CPA）**：
   - 随机选择M个原因变量集合C，加入高斯噪声。
   - 利用因果预测器F_{θ,A}预测与C直接相关的效应变量E的新值。
   - 替换E的原始值为预测值，得到正样本（保持因果关系）。
3. **因果干扰增强器（CDA）**：
   - 从C开始，通过深度优先搜索（DFS）提取子图，并以概率p随机终止。
   - 对子图中变量注入随机偏置（打破因果关系），得到负样本（模拟异常）。
4. **对比学习**：
   - 在一个mini-batch中，原始样本G1经CPA得到G2，同时G1和G2经CDA分别得到G3和G4。
   - 正样本集GP = G1 ∪ G2，负样本集GN = G3 ∪ G4。
   - 使用编码器E_φ(·)提取特征，采用相似性过滤单类对比损失（SOC）。
5. **相似性过滤单类对比损失（SOC）**：
   - 对每个锚点样本，仅保留与其余弦相似度≥阈值α的正样本参与损失计算。
   - 随着训练进行，α线性增加（例如从0.5到0.9），允许更多语义多样的正样本被纳入，避免强制所有正样本坍缩成一个簇。
   - 损失函数：L = 1/(2B) Σ_{i=1}^{2B} (1/|P_i|) Σ_{j∈P_i} -log( exp(S_{i,j}) / (exp(S_{i,j}) + Σ_{k∈N_i} exp(S_{i,k})) )，其中P_i是过滤后的正样本索引，N_i是对应的负样本索引。
6. **异常评分**：
   - 结合两个分数：对比学习嵌入距离（A_CL）= 测试样本与正样本质心μ_P的距离；因果预测误差（A_CD）= 因果预测器的MSE。
   - 对两个分数进行Z-标准化后求和得到最终异常评分A(X_t) = A_CL^{norm} + A_CD^{norm}。

## 3. 实验设计

- **数据集**：
  - **真实世界**：SWaT、WADI、PSM、SMD（两个子集2-1和3-7）、MSL（两个子集P-14和P-15）。这些数据集来自水处理、工业监控、航天器、服务器等不同领域，具有复杂的变量间依赖关系。
  - **合成数据集**：Lorenz96（非线性因果关系）和VAR（线性因果关系），均包含四种异常类型（Point Global, Point Contextual, Collective Trend, Collective Global），异常难度可通过因子λ控制。
- **Benchmark**：与多种代表性方法对比，包括：
  - 重构类：AnomalyTransformer、TimesNet、USAD。
  - 对比学习类：SimCLR、SSD、CSI、CTAD、CARLA。
- **评估指标**：AUROC、AUPRC、F1分数（最佳F1，不采用点调整方式）。
- **实现细节**：
  - 训练/验证/测试划分：20%训练数据作为验证集；使用滑动窗口（窗口大小10，批量大小256）；训练30个epoch。
  - 编码器：默认LSTM（单层）；也测试了GRU和iTransformer。
  - 温度参数τ=0.1；相似性过滤阈值α从0.5线性增至0.9。
  - 合成数据Lorenz96和VAR窗口大小分别为2和4。

## 4. 资源与算力

论文中提及：
- 训练在单张NVIDIA A40 GPU上完成。
- 对比了不同模型训练时间：CAROTS约25分钟（SWaT数据集），其他方法如TimesNet约56分钟，SimCLR约6分钟。
- 未明确说明GPU数量、具体内存使用或总训练时长（如所有实验总耗时），但提及使用3个随机种子进行重复实验。

## 5. 实验数量与充分性

- **实验数量**：
  - 主实验在5个真实世界数据集（共7个场景）和2个合成数据集上进行，共9个场景。
  - 合成数据集上额外进行了不同异常难度的分析（图3，λ=1.0~4.0）。
  - 超参数鲁棒性实验：温度τ（5个值）、批量大小B（4个值）。
  - 消融实验：移除CPA、CDA、相似性过滤、A_CL、A_CD等组件（主表4和扩展表10共9个数据集）。
  - 替代因果发现模型实验：NGC、CUTS、CUTS+（5个数据集）。
  - 不同编码器架构实验：LSTM、GRU、iTransformer（2个数据集）。
  - 相似性过滤阈值α调度实验（表9）。
  - CPA中噪声标准差σ实验（表11）。
  - 时间因果稳定性分析（表12，计算不同时间段的因果矩阵余弦相似度）。
- **充分性与公平性**：
  - 实验覆盖了多种真实复杂场景和具有明确因果关系的合成数据，评估全面。
  - 对比方法涵盖主流重构和对比学习基线，且所有基线均重新实现以保证公平。
  - 使用三个随机种子取平均值，报告标准差（表8），结果可重复。
  - 消融实验验证了每个组件的贡献，证实因果增强和SOC Loss的重要性。
  - 对关键超参数和编码器架构进行了鲁棒性测试，表明CAROTS不依赖特定设置。
  - 唯一的潜在偏差：所有数据集均为公开基准，但某些数据集（如WADI、MSL）异常比率极低，可能影响AUPRC等指标的解释。作者采用了非点调整的F1，符合近期建议。

## 6. 主要结论与发现

- CAROTS在几乎所有真实世界数据集和合成数据集上取得最佳或次优性能，尤其在WADI、MSL P-15等困难数据集上显著优于基线。
- 在合成数据集Lorenz96上，CAROTS在Point Global和Point Contextual异常检测上AUROC分别达到0.998和0.975，远超其他方法；在λ=1.0（最难）条件下，其他方法几乎失效，而CAROTS仍保持高性能（图3）。
- 相似性过滤单类对比损失（SOC）有效防止了正样本被强制压缩成一个簇，保留了语义多样性，提升了性能。
- 因果保持增强器（CPA）和因果干扰增强器（CDA）各自贡献显著，移除任一均导致性能下降。
- 对比学习嵌入距离A_CL是关键异常信号，因果预测误差A_CD作为辅助进一步提升了鲁棒性。
- CAROTS对超参数（温度、批量大小）、编码器架构（LSTM、GRU、iTransformer）和因果发现模型选择均表现稳定，实用性强。

## 7. 优点（方法或实验设计亮点）

- **方法创新性**：
  - 首次将因果关系显式融入对比学习框架用于MTSAD，提出因果保持/干扰增强策略，生成语义丰富的正负样本。
  - 提出相似性过滤单类对比损失（SOC），通过逐步放宽阈值，自适应地纳入多样化的正常样本，避免过拟合。
  - 结合双重异常评分（嵌入距离+预测误差），充分利用因果模型信息。
- **实验设计亮点**：
  - 包含合成数据集，可精确控制异常类型和难度，深入分析模型对因果关系的利用能力。
  - 对大量超参数和组件进行了鲁棒性分析，证明方法的稳定性和可迁移性。
  - 提供了因果矩阵在不同时间段的相似性分析（表12），验证了因果一致性假设。
  - 报告了训练时间，显示CAROTS效率与轻量基线相当，优于复杂模型。

## 8. 不足与局限

- **因果一致性假设**：假设正常数据中因果关系时间不变，但实际系统中可能存在缓慢或突然的因果漂移（如外部干预）。论文虽验证了短期稳定性，但未处理非平稳因果场景。
- **未处理混淆变量和外生变量**：模型仅考虑变量间的直接因果，未显式建模混淆因子（如未观测到的共同原因）或外生输入，可能引入偏差。
- **计算成本**：需要预训练一个因果发现模型（如CUTS+），虽然本文将其排除在对比学习训练时间外，但整体流程仍增加了额外阶段。
- **实验覆盖有限**：真实数据集只有5个（7场景），且均为公开基准；在一些低异常率数据集（如MSL P-15）上AUPRC较低（0.022），可能与类别极度不平衡有关，需进一步验证在更广泛场景下的表现。
- **可解释性**：虽然利用因果关系，但最终异常评分为两个分数的和，缺乏对具体哪条因果链被破坏的细粒度定位。
- **超参数敏感性**：相似性过滤阈值α的调度策略（初始值和增速）对性能有影响（表9），需要一定的调参。

（完）
