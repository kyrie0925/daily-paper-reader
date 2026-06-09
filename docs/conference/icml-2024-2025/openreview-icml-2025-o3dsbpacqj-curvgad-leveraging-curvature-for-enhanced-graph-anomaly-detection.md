---
title: "CurvGAD: Leveraging Curvature for Enhanced Graph Anomaly Detection"
title_zh: CurvGAD：利用曲率增强图异常检测
authors: "Karish Grover, Geoffrey J. Gordon, Christos Faloutsos"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=O3dsbpAcqJ"
tags: ["query:anomaly-id"]
score: 7.0
evidence: 基于曲率的图异常检测
tldr: 现有图异常检测忽略了几何异常。本文提出CurvGAD，利用混合曲率图自编码器同时重建边曲率（几何）和结构/属性。通过两个并行管线分别捕捉曲率相关和不变异常，增强了异常的可解释性。实验表明CurvGAD能发现传统方法遗漏的几何离群点，在图异常检测基准上取得领先。该工作为图异常检测开辟了利用曲率的新方向。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-o3dsbpacqj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1768, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o3dsbpacqj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 828, \"height\": 1364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o3dsbpacqj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 834, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o3dsbpacqj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1686, \"height\": 830, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-o3dsbpacqj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 724, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o3dsbpacqj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 745, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o3dsbpacqj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1772, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o3dsbpacqj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1769, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o3dsbpacqj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1624, \"height\": 2233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o3dsbpacqj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1466, \"height\": 346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o3dsbpacqj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1767, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o3dsbpacqj/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1764, \"height\": 461, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o3dsbpacqj/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1413, \"height\": 360, \"label\": \"Table\"}]"
motivation: 图异常检测方法忽略曲率表征的几何异常。
method: 构建混合曲率自编码器，分别进行曲率等价和不变的重建。
result: 在多个数据集上检测出新的几何异常，整体性能优于现有方法。
conclusion: 曲率信息能有效提升图异常检测的全面性。
---

## Abstract
Does the intrinsic curvature of complex networks hold the key to unveiling graph anomalies that conventional approaches overlook? Reconstruction-based graph anomaly detection (GAD) methods overlook such geometric outliers, focusing only on structural and attribute-level anomalies. To this end, we propose CurvGAD - a mixed-curvature graph autoencoder that introduces the notion of curvature-based geometric anomalies. CurvGAD introduces two parallel pipelines for enhanced anomaly interpretability: (1) Curvature-equivariant geometry reconstruction, which focuses exclusively on reconstructing the edge curvatures using a mixed-curvature, Riemannian encoder and Gaussian kernel-based decoder; and (2) Curvature-invariant structure and attribute reconstruction, which decouples structural and attribute anomalies from geometric irregularities by regularizing graph curvature under discrete Ollivier-Ricci flow, thereby isolating the non-geometric anomalies. By leveraging curvature, CurvGAD refines the existing anomaly classifications and identifies new curvature-driven anomalies. Extensive experimentation over 10 real-world datasets (both homophilic and heterophilic) demonstrates an improvement of up to 6.5% over state-of-the-art GAD methods. The code is available at: https://github.com/karish-grover/curvgad.

---

## 论文详细总结（自动生成）

# 论文总结：CurvGAD：利用曲率增强图异常检测

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：现有基于重建的图异常检测（GAD）方法主要关注结构异常（如异常连接）和属性异常（如异常特征值），却忽略了图的内在几何特性，即**图曲率（graph curvature）**所揭示的几何离群点。这导致模型无法捕捉由曲率异常（如瓶颈节点、层次扩散结构）引起的异常模式。
- **背景**：真实世界的图往往具有混合曲率（部分区域负曲率、部分正曲率），而现有方法（如GCN、GAT）工作在单一欧几里得空间，无法适应复杂拓扑；此外，许多方法默认同配性假设，在异配图上表现不佳。
- **本文目标**：首次提出**基于曲率的几何异常**概念，并构建混合曲率图自编码器CurvGAD，同时重建几何（曲率）和非几何（结构、属性）信息，从而检测更广泛的异常，并提升可解释性。

## 2. 论文提出的方法论
- **核心思想**：解耦异常类型，通过两个并行管线分别处理几何异常和非几何异常。
- **技术细节**：
  - **曲率等变几何重建管线**：
    - 编码器：将输入特征投影到**混合曲率乘积流形**（包含双曲、球面、欧几里得分量），使用基于Chebyshev多项式的谱滤波器组（含多个低通和高通滤波器），适应同配和异配图。
    - 解码器：基于高斯核（定义在流形测地距离上）重建边曲率矩阵，异常表现为较大的重建误差。
  - **曲率不变结构与属性重建管线**：
    - 预处理：对输入图应用**离散Ollivier-Ricci流**，迭代调整边权重直到边曲率趋于一致（统一曲率），消除曲率干扰。
    - 编码器：在正则化后的图上使用相同的Chebyshev滤波器，但限制在欧几里得空间中（流形简化）。
    - 解码器：分别使用sigmoid内积重建邻接矩阵，使用MLP重建特征矩阵。
  - **损失函数**：总损失 = 分类交叉熵损失 + 加权组合（曲率重建损失、邻接重建损失、特征重建损失），权重可学习。
  - **推理**：异常分数由三部分重建误差加权求和得到。

## 3. 实验设计
- **数据集**（10个真实世界图，涵盖同配和异配）：
  - 社交媒体：Reddit、Weibo、Questions、T-Social
  - 电商：Amazon、YelpChi
  - 金融：T-Finance、Elliptic、DGraph-Fin
  - 协作：Tolokers
- **对比基线**（4类共16种）：
  - 传统GNN：GCN、GAT、GraphSAGE
  - 谱方法：ChebyNet、BernNet
  - 黎曼方法：HGCN、HGAT、κGCN、QGCN
  - 专用GAD方法：DOMINANT、AnomalyDAE、DCI、PCGNN、BWGNN、GADNR、ADAGAD
- **评价指标**：AUROC（曲线下面积）
- **实验设置**：传导式监督学习，按40%/20%/40%划分训练/验证/测试（部分数据集按原设置）；每个数据集10次随机分割取平均和95%置信区间。

## 4. 资源与算力
- 文中明确提及：所有实验在**NVIDIA A6000 GPU（48GB显存）**上运行。
- 未说明GPU数量、总训练时长或总能耗。
- **超参数**：总流形维度dP=48，学习率0.01，滤波器数量F=8，ORC参数δ=0.5，Ricci流学习率ϵ=0.01（默认配置）。
- **时间复杂度分析**：ORC近似为O(|E|)，Ricci流迭代约12–13次，总预处理复杂度O(|E|)；每轮训练在Reddit等中等图上约为几百毫秒（略高于GCN但远低于BGNN等复杂模型）。

## 5. 实验数量与充分性
- **充分性**：
  - 10个数据集覆盖不同领域、规模（节点数千至数百万）、同配/异配，验证通用性。
  - 对比16种基线，包含传统、谱、黎曼、专用GAD等最新方法，结果以平均AUROC ±置信区间报告，统计上稳健。
  - **消融实验**（见表2、表3）：
    - 变体：欧几里得版、无Ricci流、仅曲率等变管线、仅曲率不变管线、无监督版等。
    - 流形签名：测试多种乘积流形组合（如H24×S24、H8×S8×E32等）。
    - 每个消融在全部数据集上运行，共约10×7=70组实验。
  - 实验客观公平：所有基线使用官方或报告的最佳超参数，CurvGAD超参数统一（仅流形签名按启发式选择）。
- **结论**：实验充分证明了各组件（混合曲率、Ricci流、双管线）的必要性，以及CurvGAD在多种场景下的优势。

## 6. 主要结论与发现
- CurvGAD在所有10个数据集上均取得**最优AUROC**，平均提升最高达6.5%（在DGraph上）。
- 异配图上提升尤为显著（如T-Social、Elliptic、Tolokers），表明曲率信息对非局部依赖场景有效。
- 能发现传统方法遗漏的**曲率驱动异常**（如负曲率的假新闻传播、正曲率的瓶颈蛋白）。
- 双管线解耦提高了可解释性，可区分异常类型（几何 vs 非几何）。
- 无监督版本（移除分类损失）仍优于多数基线，说明曲率信息本身具有强判别力。

## 7. 优点
- **首创性**：首次将曲率异常概念引入图异常检测，开辟新方向。
- **方法优雅**：双管线设计分别处理几何和非几何异常，物理意义清晰。
- **鲁棒性**：混合曲率空间适应不同拓扑；Chebyshev滤波器组捕获多频带，自然处理同配和异配。
- **可解释性**：异常分数分解为三个重建项，能定位异常来源（结构/属性/几何）。
- **实验扎实**：在10个数据集上全面对比16个基线，并做大量消融，结果可信。

## 8. 不足与局限
- **Ollivier-Ricci曲率近似误差**：使用线性时间近似（基于Jost-Liu界限）而非精确计算，可能引入微小偏差。
- **Ricci流计算开销**：Ricci流迭代虽线性，但对亿级边图仍需数百次ORC计算，预处理成本较高。
- **流形签名选择依赖启发式**：Algorithm 2基于ORC分布聚类确定混合成分，并非自动优化，可能需要额外调参。
- **对纯同配或小图优势不明显**：在高度同配、几何结构简单的图上（如部分社交网络），提升可能有限，消融中Weibo几乎无提升。
- **鲁棒性未探讨**：未评估对对抗攻击（如有人为修改边来逃避检测）的抵抗力。
- **公平性与偏见风险**：论文在影响声明中提及潜在偏见（如对弱势群体过度标记为异常），但未在实验中进行偏差分析或缓解讨论。
- **代码已开源**（GitHub），有利于复现与扩展。

（完）
