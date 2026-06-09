---
title: Weakly Supervised Anomaly Detection via Dual-Tailed Kernel
title_zh: 基于双尾核的弱监督异常检测
authors: "Walid Durani, Tobias Nitzl, Claudia Plant, Christian Böhm"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=hxUGmRusz5"
tags: ["query:anomaly-id"]
score: 7.0
evidence: 提出了基于双尾核的弱监督异常检测框架
tldr: 针对弱监督异常检测中标记异常有限且多样性不足的问题，提出WSAD-DT框架。该框架引入正常样本和异常两类中心，利用轻尾核紧致建模类内点、重尾核保持类间间隔，并通过核正则化保留类内多样性。实验表明该方法在多个基准上优于现有弱监督方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-hxugmrusz5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 686, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hxugmrusz5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1140, \"height\": 542, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hxugmrusz5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1362, \"height\": 1279, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hxugmrusz5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1389, \"height\": 859, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-hxugmrusz5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 1312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hxugmrusz5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1353, \"height\": 810, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hxugmrusz5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1288, \"height\": 925, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hxugmrusz5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1750, \"height\": 676, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hxugmrusz5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1767, \"height\": 1316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hxugmrusz5/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1159, \"height\": 1380, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hxugmrusz5/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 884, \"height\": 706, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hxugmrusz5/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1410, \"height\": 1783, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hxugmrusz5/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1060, \"height\": 1604, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hxugmrusz5/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1766, \"height\": 1309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hxugmrusz5/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1766, \"height\": 1309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hxugmrusz5/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1059, \"height\": 1703, \"label\": \"Table\"}]"
motivation: 弱监督异常检测中标记的异常样本有限且无法覆盖异常多样性。
method: 提出WSAD-DT，引入双尾核方案：轻尾核压缩正常点，重尾核扩大异常间隔，并结合核正则化。
result: 在多个数据集上取得了先进的异常检测性能。
conclusion: 双尾核方法可有效在弱监督下分离正常与异常样本。
---

## Abstract
Detecting anomalies with limited supervision is challenging due to the scarcity of labeled anomalies, which often fail to capture the diversity of abnormal behaviors. We propose Weakly Supervised Anomaly Detection via Dual-Tailed Kernel (WSAD-DT), a novel framework that learns robust latent representations to distinctly separate anomalies from normal samples under weak supervision. WSAD-DT introduces two centroids—one for normal samples and one for anomalies—and leverages a dual-tailed kernel scheme: a light-tailed kernel to compactly model in-class points and a heavy-tailed kernel to main- tain a wider margin against out-of-class instances. To preserve intra-class diversity, WSAD-DT in- corporates kernel-based regularization, encouraging richer representations within each class. Furthermore, we devise an ensemble strategy that partition unlabeled data into diverse subsets, while sharing the limited labeled anomalies among these partitions to maximize their impact. Empirically, WSAD-DT achieves state-of-the-art performance on several challenging anomaly detection benchmarks, outperforming leading ensemble-based methods such as XGBOD.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：在弱监督异常检测中，标记的异常样本数量极少（通常 <5%），且这些异常往往仅覆盖有限种类的异常行为，导致模型难以泛化到未见过的异常类型。
- **研究动机**：现有方法（如 DeepSAD、DevNet）依赖单一中心或单尾分布，容易造成表示坍塌或对异常多样性建模不足；而经典边际理论强调类内紧凑与类间大间隔，但单一核函数无法同时满足两者。
- **整体含义**：提出一种基于双尾核的弱监督框架，通过为正常和异常分别设置中心，并利用轻尾核（Light-tailed Kernel）实现类内紧密聚类、重尾核（Heavy-tailed Kernel）保持类间大间隔，有效提升稀疏标签下的分离能力。

### 2. 论文提出的方法论
- **核心思想**：学习映射函数 \(f_\theta : X \to Z\)，在潜空间中设置两个中心 \(c_0\)（正常）、\(c_1\)（异常）；通过双尾核分离损失驱动样本靠近自己的中心、远离另一个中心；辅以核正则化项防止坍塌；并设计集成策略增强鲁棒性。
- **关键技术细节**：
  - **双尾核分离损失**：对每个样本，定义到自身中心的距离 \(d_{in}\) 和到对立中心的距离 \(d_{out}\)；使用轻尾核（高斯核）作用于 \(d_{in}\) 以获得高相似度，使用重尾核（t-分布核）作用于 \(d_{out}\) 以保持非零梯度；损失函数为：
    \[
    \ell(\theta; x,y) = -\ln\frac{K_{\text{light}}(d_{in})}{K_{\text{light}}(d_{in}) + K_{\text{heavy}}(d_{out})}
    \]
    该形式相当于软最大化式，使样本更相似于自身中心。
  - **核正则化（多样性损失）**：在每个类内计算平均成对指数相似度 \(k(C;\theta)\)，最小化 \(L_{\text{diversity}}=k(\text{正常})+k(\text{异常})\)，惩罚过密聚类，强制保留类内变异。
  - **集成策略**：将未标注数据集 \(D_U\) 随机划分为 \(M\) 个不相交子集，每个子集与相同的少量标注异常 \(D_L\) 合并，训练 \(M\) 个模型；测试时取各模型异常得分的平均值。默认 \(M=5\)。
- **算法流程**：初始化中心和网络参数；对每个集成模型，在批量上计算分离损失 + 多样性损失（通过子采样降低复杂度）；梯度更新；最终对所有模型得分取均值作为异常得分。

### 3. 实验设计
- **数据集**：使用 AdBenchmark 中的 30 个真实世界数据集，涵盖表格数据、图像数据（MNIST-C、MVTec-AD）、网络入侵等，维度从 3 到 512，样本数从 129 到 567k。
- **Benchmark**：按 70% 训练 / 30% 测试划分，训练集中仅标注 5%（或至少 5 个）异常，余下的未标注数据假设以正常为主但可能包含污染（在消融中研究）。
- **对比方法**：DeepSAD、DevNet、FeaWAD、GANomaly、PReNet、RoSAS、XGBOD，均使用作者提供的默认超参数。
- **评价指标**：AUC-ROC 和 AUC-PR，采用三折重复实验取平均值，Wilcoxon 符号秩检验（Holm-Bonferroni校正）统计显著性。
- **消融实验**：
  - 单核 vs. 双尾核（附录 K）
  - 集成数量（1、3、5）
  - 标注比例（1%、5%、10%）
  - 训练数据污染率（0%~100%）
  - 超参数敏感性（带宽、自由度、多样性项系数）

### 4. 资源与算力
- 文中明确提到实验硬件：**Intel Core i7-10700K CPU（3.8 GHz）和 32 GB RAM**，未提及任何 GPU 型号或数量。
- 训练参数：所有模型训练 100 个 epoch，批量大小 64，学习率 1e-3。可扩展性测试（图 2）显示 WSAD-DT 使用 5 个集成时，在最大 512k 样本数据集上训练时间在可接受范围内（约数千秒）。
- 未报告GPU训练时长或具体能耗。因此，算力需求属于中等，但未提供精确的GPU使用信息。

### 5. 实验数量与充分性
- **实验数量**：主实验覆盖 30 个数据集；消融实验包括核类型（3种）、集成数量（3种）、标注比例（3种）、污染率（8个级别在8个数据集上）、超参数扫描（4个参数各3~4个值）等，总计超 200 组实验条件。
- **充分性评价**：
  - 数据集多样性高（低维、高维、图像、表格、大规模），覆盖不同异常率。
  - 对比基线全面，包括经典弱监督方法和集成方法。
  - 消融实验系统，验证了每个设计组件的必要性。
  - 统计检验（Wilcoxon）证实显著性。
  - **潜在不足**：未在时序、图结构等非表格数据上验证；部分基线（GANomaly、FeaWAD）在大数据集上超时或报错，但作者已注明，不影响主要比较。

### 6. 论文的主要结论与发现
- WSAD-DT 在 AUC-ROC 上平均排名 1.27，在 23/30 数据集上取得第一；在 AUC-PR 上平均排名 1.70，显著优于所有对比方法。
- 双尾核设计（轻尾+重尾）同时实现了类内紧凑性和类间大间隔，而单一核无法兼顾。
- 多样性正则化有效防止了表示坍塌，提升了泛化能力。
- 集成策略（共享标注异常、划分未标注数据）比传统集成（XGBOD）更有效，对污染具有鲁棒性。
- 方法在标注极少（1%）时仍保持领先，且对超参数不敏感。

### 7. 优点
- **理论支撑充分**：用 Lemma 证明了轻尾核在类内梯度更强、重尾核在类间梯度持久，以及单一核无法同时满足。
- **设计新颖**：双尾核损失函数形式简洁（软最大比值），与经典边际理论直觉吻合。
- **稳健性高**：多样性项和集成策略增加了对标签噪声、数据污染和超参数变化的鲁棒性。
- **实验全面且公平**：代码基于 DeepOD 统一框架，超参数保持为文献默认值，进行了多种消融。
- **实用价值**：适用于只有极少标注异常的工业场景，如欺诈检测、医疗诊断。

### 8. 不足与局限
- **实验覆盖范围**：仅针对静态表格和图像嵌入数据，未覆盖时序、图结构或流数据，限制了在物联网、时序监控等领域的直接应用。
- **应用局限**：
  - 当异常类型极其多样且无中心聚集性时，单异常中心可能不足。
  - 若未标注数据污染率极高（>50%），性能下降但仍比基线好。
- **超参数调优**：尽管默认值表现良好，但轻尾核带宽、重尾核自由度等仍需要根据数据集微调，未提供自动化选择机制。
- **计算开销**：集成策略线性增加训练时间，但作者已指出 \(M=5\) 是折衷。
- **未明确提及GPU资源**，可能限制了读者对可扩展性的准确判断。
- **对比方法缺失**：未与最近的基于Transformer或时序的异常检测方法比较（如OmniAnomaly，但该类方法非弱监督场景）。

（完）
