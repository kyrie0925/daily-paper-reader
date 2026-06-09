---
title: "Automatically Identify and Rectify: Robust Deep Contrastive Multi-view Clustering in Noisy Scenarios"
title_zh: 自动识别与纠正：噪声场景下的鲁棒深度对比多视图聚类
authors: "Xihong Yang, Siwei Wang, Fangdi Wang, Jiaqi Jin, Suyuan Liu, Yue Liu, En Zhu, Xinwang Liu, Yueming Jin"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=iFOXz5H2gB"
tags: ["query:anomaly-id"]
score: 5.0
evidence: 将多视图聚类中的噪声识别视为异常识别问题
tldr: 深度多视图聚类方法通常假设数据无噪声，但实际场景噪声普遍。本文提出AIRMVC框架，将噪声识别转化为异常识别问题，使用高斯混合模型分析，并设计混合纠正策略。实验表明，该方法在多个噪声场景下显著提升了聚类鲁棒性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ifoxz5h2gb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ifoxz5h2gb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 883, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ifoxz5h2gb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 800, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ifoxz5h2gb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1664, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ifoxz5h2gb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1650, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ifoxz5h2gb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1643, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ifoxz5h2gb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1681, \"height\": 831, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ifoxz5h2gb/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1626, \"height\": 542, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ifoxz5h2gb/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1697, \"height\": 871, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ifoxz5h2gb/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1685, \"height\": 1721, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ifoxz5h2gb/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1777, \"height\": 672, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ifoxz5h2gb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 734, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ifoxz5h2gb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1764, \"height\": 801, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ifoxz5h2gb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1762, \"height\": 800, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ifoxz5h2gb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 854, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ifoxz5h2gb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 914, \"height\": 892, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ifoxz5h2gb/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1743, \"height\": 698, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ifoxz5h2gb/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1377, \"height\": 374, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ifoxz5h2gb/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1742, \"height\": 698, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ifoxz5h2gb/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1687, \"height\": 1183, \"label\": \"Table\"}]"
motivation: 现有深度多视图聚类方法对噪声敏感，假设视图干净。
method: 将噪声识别建模为异常识别，采用GMM和混合纠正策略。
result: 在多个噪声数据集上，聚类性能显著优于基线。
conclusion: 为噪声环境下的多视图聚类提供了鲁棒方案。
---

## Abstract
Leveraging the powerful representation learning capabilities, deep multi-view clustering methods have demonstrated reliable performance by effectively integrating multi-source information from diverse views in recent years. Most existing methods rely on the assumption of clean views. However, noise is pervasive in real-world scenarios, leading to a significant degradation in performance. To tackle this problem, we propose a novel multi-view clustering framework for the automatic identification and rectification of noisy data, termed AIRMVC. Specifically, we reformulate noisy identification as an anomaly identification problem using GMM. We then design a hybrid rectification strategy to mitigate the adverse effects of noisy data based on the identification results. Furthermore, we introduce a noise-robust contrastive mechanism to generate reliable representations. Additionally, we provide a theoretical proof demonstrating that these representations can discard noisy information, thereby improving the performance of downstream tasks. Extensive experiments on six benchmark datasets demonstrate that AIRMVC outperforms state-of-the-art algorithms in terms of robustness in noisy scenarios. The code of AIRMVC are available at https://github.com/xihongyang1999/AIRMVC on Github.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **背景**：深度多视图聚类（Deep Multi-view Clustering）方法通过整合来自不同视图的多源信息，取得了可靠的性能。然而，现有方法大多建立在视图数据“无噪声”的假设上。
- **问题**：真实场景中噪声普遍存在（如传感器故障、数据损坏），导致模型性能显著下降，甚至不如单视图聚类。
- **目标**：本文提出**AIRMVC**（Automatic Identification and Rectification Multi-View Clustering）框架，旨在**自动识别并纠正噪声数据**，提升多视图聚类在噪声环境下的鲁棒性。

### 2. 论文提出的方法论

#### 核心思想
将噪声识别转化为**异常识别问题**，利用高斯混合模型（GMM）进行自动识别，并基于识别结果设计**混合纠正策略**和**噪声鲁棒对比机制**，从而生成可丢弃噪声信息的可靠表示。

#### 关键技术细节
- **噪声识别（Noisy Identification）**：
  - 使用编码器提取表示 \(E_v\)，通过MLP投影后建模为GMM：  
    \(p(E) = \sum_{k=1}^{K} p(q=k) \mathcal{N}(E|\mu_k,\sigma_k)\)，其中 \(q\) 为潜变量。
  - 将潜变量 \(q\) 与网络软预测 \(y\) 相关联，用EM算法更新GMM参数。
  - 引入**双组件GMM**，根据条件概率 \(\chi_{y=q|i}\) 自动区分干净样本（高均值）和噪声样本（低均值），得到清洁概率 \(\varphi_i\)。

- **混合纠正策略（Hybrid Rectification Strategy）**：
  - 利用清洁概率 \(\varphi_i\) 对软预测进行混合：  
    \(m_i^v = \varphi_i^v \times y_i^v + (1-\varphi_i^v) \times y_i^1\)（假设第一视图为干净视图）。
  - 通过交叉熵损失 \(L_{rs}\) 迫使噪声视图的预测向混合分布靠拢，从而纠正噪声。

- **噪声鲁棒对比机制（Noise-Robust Contrastive Mechanism）**：
  - 计算跨视图样本相似度 \(s(E_i^m, E_j^n)\)，并用软预测阈值 \(\tau\) 过滤不可靠的样本对。
  - 对比损失 \(L_{con}\) 仅对满足 \( (y_i^m)^T y_j^n \geq \tau \) 的样本对进行约束，减少噪声导致的正负样本错配。

- **目标函数**：
  \[
  L = L_{rec} + \alpha L_{rs} + \beta L_{con}
  \]
  其中 \(L_{rec}\) 为自编码器重建损失，\(\alpha, \beta\) 为平衡超参数（实验中均设为1.0）。

- **理论证明**：定理4.1表明，通过最大化互信息 \(I(E; x^+)\) 学习到的表示 \(E^*\) 能够**保留干净信息、丢弃噪声信息**。

#### 算法流程（文字说明）
1. 预训练自编码器100轮。
2. 每轮训练：
   - **E步**：基于当前软预测更新GMM参数 \((\mu_k,\sigma_k)\) 及清洁概率 \(\varphi_i\)。
   - **M步**：
     - 编码器提取表示 \(E\)。
     - 根据 \(\varphi_i\) 计算混合软预测 \(m\)。
     - 计算重建损失 \(L_{rec}\)、纠正损失 \(L_{rs}\)、对比损失 \(L_{con}\)。
     - 总损失 \(L\) 反向传播，Adam优化器更新网络参数。
3. 输出聚类结果（k-means或谱聚类）。

### 3. 实验设计

- **数据集**：6个基准数据集 —— **BBCSport**（544样本，5类，2视图）、**WebKB**（1051，2类，2视图）、**Reuters**（1200，6类，5视图）、**UCI-digit**（2000，10类，3视图）、**Caltech101**（9144，102类，5视图）、**STL10**（13000，10类，4视图）。
- **噪声模拟**：在输入数据上随机添加噪声，比例设为 **10%、30%、50%、70%、90%**。
- **评价指标**：ACC（准确率）、NMI（归一化互信息）、PUR（纯度）。
- **对比方法**：11种深度多视图聚类方法，分为两类——
  - 经典方法：CoMVC、SiMVC、MFLVC、DealMVC、SURE、CANDY、TGM-MVC、SCE-MVC、DIVIDE。
  - 噪声鲁棒方法：RMCNC、MVCAN。
- **实现细节**：所有方法使用作者提供的源代码和默认配置；AIRMVC在PyTorch、NVIDIA A6000 GPU上运行；预训练100轮，正式训练400轮；Adam优化器，学习率1e-4或1e-5；超参数 \(\alpha=\beta=1.0\)，阈值 \(\tau=0.8\)。

### 4. 资源与算力

文中明确提到：**所有实验在 PyTorch 平台、单个 NVIDIA A6000 GPU 上完成**。但未说明训练总时长、GPU数量或具体耗时，因此无法量化算力消耗。

### 5. 实验数量与充分性

- **实验组数**：在6个数据集、5种噪声比例下，与11种基线方法对比（每个实验10次独立运行取平均），共约 \(6 \times 5 \times 12 = 360\) 组对比实验。
- **消融实验**：针对关键组件（噪声识别与纠正、鲁棒对比机制）进行去除实验；并设计了“直接融合噪声视图”“单视图”“直接纠正”等对照设置。
- **可视化**：t-SNE展示UCI-digit数据集上表示随训练轮数的演化。
- **超参数敏感分析**：对 \(\alpha, \beta, \tau\) 进行了详细扫描。
- **客观性与公平性**：所有基线使用原代码/默认配置，保证对比公平；实验覆盖多种噪声比例和数据集类型，结论稳健。

### 6. 论文的主要结论与发现

- AIRMVC在所有数据集和大多数噪声比例下**显著优于**所有对比方法，尤其在**高噪声比例（如70%、90%）** 下优势更加明显。
- 在BBCSport（10%噪声）上，ACC比最优基线提升 **2.39%**，NMI提升 **9.64%**，PUR提升 **1.46%**。
- 噪声识别与纠正模块对性能提升贡献最大（消融实验中去掉该模块降幅最大）。
- 可视化表明：随着训练推进，聚类结构逐渐清晰，证明AIRMVC能有效挖掘潜在簇结构。
- 理论证明支持：对比学习可使表示丢弃噪声信息，保留干净信息。

### 7. 优点

1. **问题创新**：首次将多视图噪声识别形式化为**异常识别问题**，并利用GMM双组件自动区分干净与噪声样本。
2. **混合纠正策略**：基于清洁概率动态融合干净视图和当前视图的软预测，既纠正噪声又不丢失互补信息。
3. **噪声鲁棒对比机制**：通过软预测阈值过滤不可靠样本对，大幅提升对比学习样本构建的准确性。
4. **理论支撑**：提供严谨的互信息理论证明，说明学到的表示能丢弃噪声信息。
5. **实验充分**：在6个数据集、5种噪声比、11种基线方法上全面评估，消融与敏感性分析完备。

### 8. 不足与局限

1. **假设限制**：论文假设**第一视图为干净视图**（借鉴前人工作），但在实际中第一视图也可能包含噪声，该假设不总是成立。
2. **噪声类型单一**：仅模拟了随机噪声，未涵盖缺失噪声、对抗噪声等更复杂场景。
3. **计算开销不明**：未分析模型在大规模数据集（如Caltech101有102类）上的训练时间、内存占用，可能影响实际部署。
4. **极端噪声性能**：在90%噪声下虽然仍优于基线，但ACC和NMI绝对值较低（如BBCSport ACC仅39.52%），仍有较大提升空间。
5. **理论假设较强**：定理证明中假设 \(I(x;y|x^+)\leq \vartheta\) 和 \(I(x;y'|x^+)>\eta\)，这些条件的满足性在实际中难以验证。

（完）
