---
title: When and How Does In-Distribution Label Help Out-of-Distribution Detection?
title_zh: 分布内标签如何以及何时帮助分布外检测
authors: "Xuefeng Du, Yiyou Sun, Yixuan Li"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=knhbhDLdry"
tags: ["query:anomaly-id"]
score: 9.0
evidence: 理论分析分布内标签如何帮助分布外检测，这是异常检测核心任务
tldr: 分布外检测与经典异常检测的区别在于是否使用分布内标签，但何时以及如何利用标签提升性能尚未有严格分析。本文通过理论框架阐明了分布内标签在OOD检测中的作用，揭示了标签信息对检测精度的条件性影响。实验验证了理论发现，为设计更有效的异常检测方法提供了指导。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-knhbhdldry/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1776, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-knhbhdldry/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1751, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-knhbhdldry/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1764, \"height\": 526, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-knhbhdldry/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1755, \"height\": 569, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-knhbhdldry/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 489, \"height\": 159, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-knhbhdldry/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 816, \"height\": 137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-knhbhdldry/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1710, \"height\": 1807, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-knhbhdldry/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 647, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-knhbhdldry/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1032, \"height\": 161, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-knhbhdldry/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1754, \"height\": 571, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-knhbhdldry/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1489, \"height\": 565, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-knhbhdldry/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 505, \"height\": 337, \"label\": \"Table\"}]"
motivation: 分布外检测和异常检测中标签的作用缺乏严格理论理解。
method: 形式化分析分布内标签对OOD检测的理论影响，建立条件性结论。
result: 理论推导与实验验证了标签在特定条件下提升检测性能。
conclusion: 为结合标签的异常检测方法设计提供了理论基础。
---

## Abstract
Detecting data points deviating from the training distribution is pivotal for ensuring reliable machine learning. Extensive research has been dedicated to the challenge, spanning classical anomaly detection techniques to contemporary out-of-distribution (OOD) detection approaches. While OOD detection commonly relies on supervised learning from a labeled in-distribution (ID) dataset, anomaly detection may treat the entire ID data as a single class and disregard ID labels. This fundamental distinction raises a significant question that has yet to be rigorously explored: when and how does ID label help OOD detection? This paper bridges this gap by offering a formal understanding to theoretically delineate the impact of ID labels on OOD detection. We employ a graph-theoretic approach, rigorously analyzing the separability of ID data from OOD data in a closed-form manner. Key to our approach is the characterization of data representations through spectral decomposition on the graph. Leveraging these representations, we establish a provable error bound that compares the OOD detection performance with and without ID labels, unveiling conditions for achieving enhanced OOD detection. Lastly, we present empirical results on both simulated and real datasets, validating theoretical guarantees and reinforcing our insights.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在分布外（OOD）检测任务中，使用分布内（ID）标签进行监督学习与不使用标签的经典异常检测之间存在根本区别。论文探究的核心问题是：**ID标签在何时以及如何帮助提升OOD检测性能？**  
- **研究动机**：尽管OOD检测通常依赖带标签的ID数据集进行监督学习，而异常检测则可能将整个ID数据视为单一类别并忽略标签。然而，目前缺乏严格的理论分析来阐明标签信息对检测效果的真正影响。该问题对于理解并融合两个高度相关领域（异常检测与OOD检测）具有基础性价值。  
- **研究背景**：现有OOD检测方法多数依赖ID标签的监督，但缺乏对标签作用的理论刻画。同时，光谱图理论已被用于表示学习（如谱对比学习），但尚未应用于OOD检测中标签影响的分析。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 采用**图论方法**建模ID数据，通过图的邻接矩阵表示数据点之间的相似性，分别定义无标签情况下的自监督连接（基于数据增强）和有标签情况下的监督连接（利用类标签增强同类连接）。
- 对邻接矩阵进行**谱分解**，将每个数据点的表示等价为图中顶点的低维嵌入，该嵌入可通过**对比学习目标**端到端训练得到。
- 基于上述表示，推导ID数据和OOD数据的**闭式解**，并利用**线性探针误差**作为OOD检测性能的度量，进而比较有标签和无标签两种情况下的误差界。

### 关键技术细节
1. **图构建**：
   - 无标签情况（u）：边权重由同一原始图像的两个增强视图的边际概率定义。
   - 有标签情况（l）：增加监督连接，即相同类别的两个原始图像的增强视图也构成正对，总邻接矩阵为无标签部分与监督部分的加权和。
2. **表示学习**：
   - 利用谱分解得到最优表示：`Z^(l) = [D^(l)]^{-1/2} V_k^(l) [Σ_k^(l)]^{1/2}`（ID数据）；OOD数据表示通过求解最小化问题得到闭式解：`Z^(l)_ood = [D^(l)_ood]^{-1/2} ˜A^(l)_OI V_k^(l) [Σ_k^(l)]^{-1/2}`。
   - 该表示等价于最小化一个对比学习损失（包含正对拉近项和负对拉远项）。
3. **误差界**：
   - 线性探针误差上界由回归残差给出：`R(Z_all) ≤ 2/(N+M) Tr((I - Z_all Z_all^†) y y^⊤)`。
   - 定义误差差值 `G = R(Z^(u)_all) - R(Z^(l)_all)`（无标签减有标签），推导其下界（Theorem 1）：
     - `G ≥ [C φ_l/(N+M)] · ϵ(p, q, ˜A^(u), ˜A^(u)_OI)`，其中ϵ依赖于ID数据内部连接稀疏度、OOD与ID的连接密度、以及语义连接强度。
   - Theorem 2（简化版）指出：当ID数据在无标签时连接稀疏、OOD数据靠近ID（近OOD场景）、且ID数据与标签数据的语义连接足够大时，标签带来的优势最明显。

## 3. 实验设计：数据集、场景与基准

### 数据集
- **ID数据集**：CIFAR-10, CIFAR-100。
- **OOD数据集**：
  - **远OOD**：SVHN, TEXTURES, PLACES365, LSUN-Resize, LSUN-C。
  - **近OOD**：CIFAR-10（当ID为CIFAR-100时），CIFAR-100（当ID为CIFAR-10时）。
- 此外，还使用**模拟数据**（图2示例）来可视化理论结果。

### 场景设置
- **线性探针OOD与测试OOD相同（P^test_ood = P^LP_ood）**：使用75%的OOD数据训练线性探针，剩余25%测试。
- **线性探针OOD与测试OOD不同（P^test_ood ≠ P^LP_ood）**：使用300K RANDOM IMAGES作为探针数据，其他标准OOD数据集作为测试。
- 对比方法：**无标签情况（unlabeled）** 与 **有标签情况（labeled）**，均训练ResNet-18特征提取器，然后线性探针分类ID vs OOD。

### Benchmark
- 主要对比**有标签 vs 无标签**的两类设置，未对比其他现有OOD检测方法（因为论文侧重点在于理论验证，而非竞赛性性能比较）。
- 补充实验：使用**k-NN后验分数**进行OOD检测（附录I），进一步验证结论的普适性。

## 4. 资源与算力

- 论文中未明确说明使用的GPU型号、数量或训练时长。仅提到训练ResNet-18 200个epoch（对比学习），线性探针50个epoch。在实验细节中未提及具体硬件资源（如单卡或多卡、GPU型号等）。
- 模拟数据实验（图2）使用自定义生成的小规模数据（每类40个点），算力需求小，但论文未报告所用设备。

## 5. 实验数量与充分性

### 主要实验组数
1. **表1（Table 1）**：CIFAR-100作为ID，6个OOD数据集（5个远OOD、1个近OOD），报告FPR95、AUROC、线性探针误差。包含两种场景（P_equal和P_unequal），共约2×6×2=24组结果（有/无标签各半）。
2. **表7（Table 7，附录I）**：CIFAR-10作为ID，类似配置，共约24组。
3. **表8（Table 8，附录I）**：相同设置但使用k-NN分数，共约24组。
4. **表2、3、5、6**：验证Frobenius范数与误差差的关系（改变epoch或OOD类型）。
5. **表9（附录J）**：验证边界紧致性（模拟数据）。
6. **图2、3**：模拟数据可视化表示和误差差异。

### 充分性评估
- 覆盖了多种OOD类型（远/近）、两种ID数据集、两种评价指标（线性探针和k-NN），实验设计合理。
- 消融实验验证了理论中的条件（改变连接密度、语义连接强度），与理论一致。
- 存在一定局限：所有实验基于CIFAR类图像数据，未涉及更高分辨率或更大规模数据集（如ImageNet）；且仅使用ResNet-18一种架构，泛化性有待验证。总体而言，实验在理论验证维度充分，但在算法竞赛层面不够全面。

## 6. 论文的主要结论与发现

1. **ID标签在OOD检测中并非总是有利**，其好处取决于条件：
   - 当OOD数据与ID数据高度相似（近OOD场景）时，标签能显著提升检测性能（如AUROC提升12.3%）。
   - 当ID数据在无标签时内部连接稀疏（即缺乏自监督结构）时，标签作用更大。
   - 当每个ID数据与不同类的标签数据的语义连接较强时，标签收益更明显。
   - 在远OOD场景下，无标签的表示已经足够分离ID和OOD，标签带来的边际收益很小（如AUROC仅提升0.02%）。
2. 理论下界（Theorem 1, 2）成功预测了这些趋势，并在模拟和真实数据集上得到验证。
3. 研究结论有助于理解异常检测（无标签）与OOD检测（有标签）之间的本质联系。

## 7. 优点

1. **首次严格理论分析**：填补了ID标签对OOD检测影响的理论空白，给出了可证明的误差界。
2. **框架通用**：使用图论和谱分解方法，可推广到其他基于表示的检测任务。
3. **理论与实验紧密结合**：不仅推导了形式化条件，还在模拟数据和真实图像上验证了关键结论，且通过消融实验验证了每个理论条件（连接稀疏度、OOD距离等）。
4. **分析简洁直观**：通过模拟例图（图2、3）生动展示不同场景下的表示差异，帮助读者理解复杂理论。
5. **补充了后验OOD检测分数（k-NN）的验证**，表明结论不依赖于特定的线性探针方法。

## 8. 不足与局限

1. **数据规模和任务范围的局限**：所有实验仅限于CIFAR-10和CIFAR-100（32×32图像），未在ImageNet等高分辨率、大规模数据集上验证。同时仅使用ResNet-18一种模型，需验证在不同架构下的可迁移性。
2. **理论假设的强约束**：部分理论推导依赖特定假设（如Assumption 2要求q向量位于特定线性空间中），虽然论文声称已在真实数据中验证了谱间隙条件，但严格性有待更广泛检验。
3. **未纳入现有SOTA方法对比**：论文的核心目的是理解标签影响，而非提出新OOD检测方法。因此未与成熟的OOD检测方法（如能量分数、马氏距离等）进行性能基准比较，这可能在应用层面限制其实践指导价值。
4. **线性探针作为评价的局限性**：实际OOD检测常使用更复杂的分数（如KNN、MSP），虽然附录补充了KNN实验，但主结论基于线性探针误差，可能无法完全代表真实部署场景。
5. **对OOD数据的假设**：分析假设OOD表示基于与ID的相似性推导，但实际中OOD可能有未知结构，该推导可能偏离实际情况。
6. **未讨论标签噪声或缺失**：现实场景中ID标签可能含有噪声，论文未分析标签质量对结果的影响。

（完）
