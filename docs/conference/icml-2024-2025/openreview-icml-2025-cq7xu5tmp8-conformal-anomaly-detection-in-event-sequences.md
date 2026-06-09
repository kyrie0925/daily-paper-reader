---
title: Conformal Anomaly Detection in Event Sequences
title_zh: 事件序列中的保形异常检测
authors: "Shuai Zhang, Chuan Zhou, Yang Liu, Peng Zhang, Xixun Lin, Shirui Pan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Cq7XU5tmP8"
tags: ["query:anomaly-id"]
score: 8.0
evidence: 事件序列异常检测，控制假阳性率
tldr: 连续时间事件序列的异常检测缺乏假阳性率控制。本文提出CADES方法，基于保形推理和时序重标定理设计两种互补的非一致性分数，结合Bonferroni校正实现有限样本下的FPR控制。实验表明CADES能有效检测各类异常模式，同时提供统计保证。该方法为安全关键应用中的可靠异常检测提供了理论保障。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-cq7xu5tmp8/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 843, \"height\": 331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cq7xu5tmp8/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 325, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cq7xu5tmp8/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1587, \"height\": 418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cq7xu5tmp8/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 787, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cq7xu5tmp8/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 786, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cq7xu5tmp8/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 784, \"height\": 419, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cq7xu5tmp8/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 768, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cq7xu5tmp8/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1284, \"height\": 447, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-cq7xu5tmp8/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1687, \"height\": 372, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cq7xu5tmp8/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 805, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cq7xu5tmp8/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 897, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cq7xu5tmp8/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 808, \"height\": 150, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cq7xu5tmp8/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 984, \"height\": 438, \"label\": \"Table\"}]"
motivation: 现有事件序列异常检测方法无法控制假阳性率，缺乏可靠性保证。
method: 基于保形推理与时序重标定理，设计两个非一致性分数并使用Bonferroni校正。
result: 在合成与真实事件序列数据上，CADES有效控制了FPR并优于现有方法。
conclusion: CADES为事件序列异常检测提供了首个可证明FPR控制的方法。
---

## Abstract
Anomaly detection in continuous-time event sequences is a crucial task in safety-critical applications. While existing methods primarily focus on developing a superior test statistic, they fail to provide guarantees regarding the false positive rate (FPR), which undermines their reliability in practical deployments. In this paper, we propose CADES (Conformal Anomaly Detection in Event Sequences), a novel test procedure based on conformal inference for the studied task with finite-sample FPR control. Specifically, by using the time-rescaling theorem, we design two powerful non-conformity scores tailored to event sequences, which exhibit complementary sensitivities to different abnormal patterns. CADES combines these scores with Bonferroni correction to leverage their respective strengths and addresses non-identifiability issues of existing methods. Theoretically, we prove the validity of CADES and further provide strong guarantees on calibration-conditional FPR control. Experimental results on synthetic and real-world datasets, covering various types of anomalies, demonstrate that CADES outperforms state-of-the-art methods while maintaining FPR control.

---

## 论文详细总结（自动生成）

### 论文中文详细总结

#### 1. 核心问题与整体含义（研究动机与背景）
- **问题**：连续时间事件序列（如服务器日志、金融交易、地震记录）的异常检测在安全关键应用中至关重要。现有方法（如基于KS统计量、3S统计量的方法）仅关注设计更优的检验统计量，但无法控制**假阳性率（FPR）**，这严重限制了其在实践中的可靠性。
- **动机**：安全关键场景（如医疗诊断、欺诈检测）要求异常检测方法具有可证明的FPR控制能力。保形推理（Conformal Inference）提供了灵活的框架，但此前尚未被应用于事件序列的异常检测。
- **整体目标**：提出一种基于保形推理的事件序列异常检测方法，能够在不牺牲检测能力的前提下，提供有限样本下的FPR控制（包括边际FPR和更强的校准条件FPR）。

#### 2. 方法论：核心思想、关键技术细节
- **核心思想**：利用**时间重标定理**将原始事件序列转换为标准泊松过程（SPP）的多个独立实现，然后基于转换后的数据设计两种互补的**非一致性分数**，并通过**Bonferroni校正**结合这两种分数进行假设检验。
- **关键技术细节**：
    1. **时间重标与拼接**：对于带标记的事件序列 \(X = \{(t_i, m_i)\}\)，使用基于训练数据的神经TPP模型估计条件强度函数 \(\lambda_m^*(t)\)，通过积分得到重新缩放的时间 \(\Lambda_m^*(t)\)，并将各标记的重新缩放序列拼接成一个SPP实现 \(Z = (\tau_1, \dots, \tau_N)\)，观测区间为 \([0, V]\)。
    2. **非一致性分数设计**：
        - \(s_{arr}(X)\)：衡量归一化到达时间 \(\tau_i / V\) 的核密度估计（KDE）与均匀分布 \(U[0,1]\) 之间的KL散度，对事件数减少敏感。
        - \(s_{int}(X)\)：衡量间隔时间 \(w_i = \tau_i - \tau_{i-1}\) 的KDE与指数分布 \(\text{Exponential}(1)\) 之间的KL散度，对均匀间隔敏感。
        - 两者互补，克服了KS统计量对事件数不敏感、3S/Q+统计量对均匀间隔不敏感的问题。
    3. **双边p值与Bonferroni校正**：
        - 针对每个分数计算双边保形p值（如 \(p_{arr}(X_{test}) = 2 \min\{p_{arr}^l, p_{arr}^r\}\)），因为过大或过小的分数都可能指示异常。
        - 使用Bonferroni校正合并两个p值：\(p_{cor}(X_{test}) = \min\{ 2(1+\varepsilon) p_{arr}, 2(1+\varepsilon) p_{int} \}\)，其中 \(\varepsilon \ge 0\) 用于控制校准条件FPR。
        - 若 \(p_{cor}(X_{test}) \le \alpha\)，则判定序列为异常（OOD）。
- **理论保证**：
    - **命题3.3**：\(p_{cor}\) 是有效p值，保证了边际FPR控制（\(P_{H_0}(\text{declare OOD}) \le \alpha\)）。
    - **定理3.4**：在分数连续分布和校准集大小满足一定条件（Beta分布CDF约束）下，以概率 \(1-\delta\) 保证校准条件FPR \(\le \alpha\)（即 \(P( P_{H_0}(\text{declare OOD} \mid D_{cal}) \le \alpha ) \ge 1-\delta\)）。

#### 3. 实验设计
- **数据集与场景**：
    - **GOF测试（9种备择分布）**：在标准泊松过程（SPP）上测试，包括 DecreasingRate、IncreasingRate、InhomogeneousPoisson、Stopping、RenewalA、RenewalB、Hawkes、SelfCorrecting、Uniform。每种备择分布用一个可检测性参数 \(\eta \in [0,1]\) 控制偏离程度。
    - **合成数据集（4种）**：ServerStop、ServerOverload、Latency、SpikeTrains，覆盖不同异常模式（主机下线、流量重路由、延迟增大、标记交换）。
    - **真实数据集**：
        - **LOGS**：服务器日志，8种标记，包含5种注入故障（如包损坏、包重复、前端延迟、全服务延迟）。
        - **STEAD**：地震事件序列，4个地点（San Mateo, CA作为ID，其余3个作为OOD）。
- **Benchmark与对比方法**：
    - GOF测试对比：KS到达、KS间隔、Chi-squared、3S、Q+、Q–统计量。
    - OOD检测对比：除上述统计量外，还对比了Log-likelihood、MultiAD-Q+、MultiAD-Q–。
    - 所有对比方法均使用相同的神经TPP模型架构（LogNormMix）和训练流程。

#### 4. 资源与算力
- **GPU**：单张 NVIDIA RTX 3090 Ti。
- **框架**：PyTorch。
- **训练设置**：优化器Adam，学习率 \(10^{-3}\)，批次大小64，梯度裁剪5，最大训练轮数500，早停机制（5轮不改善则停止）。训练集与校准集各占一半。
- **未明确说明**：总训练时长、GPU数量、能耗等具体信息未提供。

#### 5. 实验数量与充分性
- **实验数量**：
    - GOF测试：9种备择分布 × 多个 \(\eta\) 值（通常10个），每种设置重复10次随机种子。
    - 合成数据：4种场景 × 多个 \(\eta\)，重复10次。
    - 真实数据：LOGS 5种故障，STEAD 3个OOD地点，重复5次（5种不同初始化）。
    - 消融实验：比较单一分数（CADES-arr、CADES-int）与组合（CADES）；比较右边p值与双边p值（CADES-arr-r vs CADES-arr）。此外还验证了FPR控制（图4）和TPR对比（表2）。
- **充分性与公平性**：
    - 覆盖多种异常模式（事件数变化、间隔均匀、标记转换、强度突变等），场景全面。
    - 所有方法使用相同的TPP模型、训练分割（Dtrain与Dcal）、校准方式，对比公平。
    - 指标包括AUROC、FPR、TPR，评估维度多样。
    - 消融实验明确展示了两个分数的互补性及双边p值的必要性。

#### 6. 主要结论与发现
- CADES在所有实验中均表现优异：GOF测试的9种场景下，CADES在多数情况下AUROC最高或接近最高；合成和真实数据上平均排名第一，显著超越基线。
- **FPR控制有效**：在LOGS和STEAD上，CADES的FPR始终低于目标水平 \(\alpha\)，而基线方法（如3S、MultiAD-Q+）在LOGS上严重超标。
- **消融证实设计合理**：组合两个分数优于单个分数；双边p值相比右边p值能正确检测均匀间隔类异常（如SelfCorrecting、Uniform场景）。
- 理论保证（边际和校准条件FPR控制）得到实验验证。

#### 7. 优点
- **理论贡献扎实**：首次将保形推理引入事件序列异常检测，并提供边际FPR和校准条件FPR的严格证明。
- **分数设计精巧**：基于时间重标定理和KL散度设计两个互补分数，有效解决了现有统计量的非可识别性问题（如对事件数不敏感、对均匀间隔不敏感）。
- **实用性强**：在多个合成和真实数据上验证，方法鲁棒，计算开销可接受（虽略高于基线但仍在合理范围）。
- **实验全面**：覆盖9种GOF场景、4种合成、2种真实数据，且包含多种对比方法和消融，结论可靠。

#### 8. 不足与局限
- **依赖校准集**：方法要求一个干净的校准集 \(D_{cal}\)，且校准集大小影响FPR控制质量（理论中需要一定大小才能高概率保证）。
- **计算开销**：相比3S、KS等简单统计量，CADES需要训练神经TPP模型并计算数值积分，推理时间略长（文中表4显示约比3S慢50%左右），但在可接受范围内。
- **模型依赖**：需要训练一个足够精确的TPP模型来近似真实强度函数；若模型拟合不佳，时间重标步骤的转换质量可能下降，从而影响检测性能。
- **仅序列级别异常**：方法检测整个序列是否异常，未涉及寻找序列内特定异常事件或时间点。
- **未考虑分布漂移**：假设训练/校准数据来自固定分布ID；若测试时分布发生漂移（covariate shift），需要自适应保形方法（论文未讨论）。
- **参数敏感**：KDE带宽 \(h_1, h_2\) 通过网格搜索确定，不同数据可能需要调参；Bonferroni校正中的 \(\varepsilon\) 依赖校准集大小，最坏情况下的保守性可能降低检测能力。

（完）
