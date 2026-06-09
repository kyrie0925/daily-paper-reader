---
title: Near-Linear Time Approximation Algorithms for k-means with Outliers
title_zh: k-means带异常值的近线性时间近似算法
authors: "Junyu Huang, Qilong Feng, Ziyun Huang, Jinhui Xu, Jianxin Wang"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=EHjm3sXPFy"
tags: ["query:anomaly-id"]
score: 5.0
evidence: 带异常值的k-means的近似线性时间算法
tldr: k-means带异常值聚类问题在机器学习中广泛研究，但现有算法运行时间依赖数据纵横比。本文提出基于快速采样的近似线性时间算法，核心是Fast-Sampling组件，能够高效找到近似最优聚类中心。理论分析和实验表明，该算法在不牺牲精度的前提下大幅缩短了运行时间。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-ehjm3sxpfy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1670, \"height\": 1315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ehjm3sxpfy/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1668, \"height\": 1306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ehjm3sxpfy/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1673, \"height\": 1298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ehjm3sxpfy/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1674, \"height\": 1297, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1707, \"height\": 666, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1655, \"height\": 719, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1781, \"height\": 126, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1246, \"height\": 776, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1225, \"height\": 774, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1244, \"height\": 774, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1225, \"height\": 774, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1486, \"height\": 776, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1269, \"height\": 774, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1487, \"height\": 776, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1267, \"height\": 774, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1300, \"height\": 774, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1294, \"height\": 776, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1233, \"height\": 774, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1249, \"height\": 774, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1232, \"height\": 774, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1251, \"height\": 775, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1487, \"height\": 777, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1488, \"height\": 778, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1487, \"height\": 777, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1488, \"height\": 776, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1512, \"height\": 776, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1532, \"height\": 776, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1531, \"height\": 776, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1532, \"height\": 779, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1361, \"height\": 852, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1740, \"height\": 1084, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ehjm3sxpfy/table-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1086, \"height\": 972, \"label\": \"Table\"}]"
motivation: 现有k-means异常值算法运行时间依赖数据纵横比。
method: 提出基于采样的Fast-Sampling算法，近线性时间找到内点近似最优中心。
result: 在理论和实验中表现出高效率。
conclusion: 该算法解决了纵横比依赖问题。
---

## Abstract
The k-means with outliers problem is one of the most extensively studied clustering problems in the field of machine learning, where the goal is to discard up to z outliers and identify a minimum k-means clustering on the remaining data points. Most previous results for this problem have running time dependent on the aspect ratio Δ (the ratio between the maximum and the minimum pairwise distances) to achieve fast approximations. To address the issue of aspect ratio dependency on the running time, we propose sampling-based algorithms with almost linear running time in the data size, where a crucial component of our approach is an algorithm called Fast-Sampling. Fast-Sampling algorithm can find inliers that well approximate the optimal clustering centers without relying on a guess for the optimal clustering costs, where a 4-approximate solution can be obtained in time $O(\frac{ndk\log\log n}{\epsilon^2})$ with O(k/ϵ) centers opened and (1+ϵ)z outliers discarded. To reduce the number of centers opened, we propose a center reduction algorithm, where an O(1/ϵ)-approximate solution can be obtained in time $O(\frac{ndk\log \log n}{\epsilon^2} + dpoly(k, \frac{1}{\epsilon})\log(n\Delta))$ with (1+ϵ)z outliers discarded and exactly k centers opened. Empirical experiments suggest that our proposed sampling-based algorithms outperform state-of-the-art algorithms for the k-means with outliers problem.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将基于您提供的论文内容，对《Near-Linear Time Approximation Algorithms for k-means with Outliers》一文进行结构化、深入、客观的总结。

---

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：论文聚焦于“带异常值的 k-means 聚类”（k-means with outliers）问题。该问题的目标是在数据集中识别并丢弃至多 `z` 个异常点，然后对剩余数据进行标准的 k-means 聚类，以最小化聚类成本。
- **研究动机**：
    1.  **效率瓶颈**：以往大多数优秀的近似算法，其运行时间依赖于数据的**纵横比** (Aspect Ratio, Δ)，即数据点间最大与最小距离的比值。当 Δ 很大（如高维或分布极端的数据）时，算法效率会显著下降，限制其在大规模数据上的应用。
    2.  **猜测代价**：许多采样或局部搜索方法需要预先猜测一个“最优聚类成本”作为关键参数，这一过程不仅增加了计算负担，也导致算法对 Δ 产生依赖。
- **研究意义**：本文旨在设计一种运行时间与数据纵横比 Δ 无关的近似线性时间算法，解决了k-means with outliers问题中一个关键的效率和可扩展性障碍，为大规模含噪声数据的聚类提供了更实用的理论及实践方案。

### 2. 论文提出的方法论

本文的核心创新在于提出了一个名为 **Fast-Sampling** 的算法，并在此基础上结合 **Center-Reduction** 算法来优化最终结果。

- **核心思想**：
    - **Fast-Sampling**：旨在不依赖“最优聚类成本”猜测的情况下，高效地采样出能够良好逼近最优聚类中心的**内点（inliers）**。该算法通过一个两阶段采样策略来克服异常值对内点采样的干扰。
    - **Center-Reduction**：在 Fast-Sampling 的基础上，通过一个“中心约简”过程，将最初打开的大量中心（O(k/ε)个）减少到精确的 k 个，同时维持近似比。

- **关键技术细节**：
    1.  **Fast-Sampling 算法（Algorithm 1 & 2）**：
        - **阶段一：概率提升 (Oversampling Factor Estimation)**：
            - 第一步是找到一个“过采样因子”（Oversampling Factor, `l'`），使得所有数据点的**修剪后基于距离的采样概率之和**达到 `(1+ε)z`。
            - 通过算法 `OSE`（Algorithm 2）快速估算 `l'` 的下界和上界，然后通过二分搜索在区间 `[lf, max{εz·lf, 2lf}]` 内找到 `l'`。
            - 这一过程在没有最优成本信息的情况下，巧妙地确保了在采样中，异常值不会主导概率分布，而内点（特别是接近中心的内点）有足够的概率被选中。
        - **阶段二：概率归一化与采样**：
            - 使用第一阶段找到的 `l'` 计算每个点的采样概率 `t(l', x, C_i)`，然后进行归一化采样。
            - 理论证明（引理3.5和3.6），每次采样都有概率 `Ω(ε)` 选中一个能显著改善当前聚类效果的内点。通过重复 `O(k/ε)` 轮，即可得到一个 **4-近似**的解，同时打开 `O(k/ε)` 个中心并丢弃 `(1+ε)z` 个异常值。
            - 算法的运行时间为 `O(ndk log log n / ε²)`，完全不受 Δ 影响。

    2.  **Center-Reduction 算法（Algorithm 3）**：
        - 该算法将 Fast-Sampling 的结果作为一个初始的重加权实例。
        - 核心思路是“召回”那些被 Fast-Sampling 错误丢弃的内点。通过循环猜测并移除被误判的最近内点，然后调用一个能处理加权实例的经典近似算法（如LS++），算法能找到一个新的解。
        - 理论证明，这个新解可以做到 **O(1/ε)-近似**，且只打开**恰好 k 个中心**，同时仍能保证丢弃 `(1+ε)z` 个异常值。
        - 该算法的运行时间为 `O(ndk log log n / ε² + d·poly(k, 1/ε) log(nΔ))`，其中对 Δ 的依赖降到了最低项次。

    - **核心引理**：
        - **Lemma 3.4**：对于“坏”的最优聚类，其内部接近中心的数据点（`Tα`）的聚类成本相对较高，这使得它们能在采样中被有效选中。
        - **Lemma 3.6**：通过 `O(k/ε)` 次采样迭代，能以高概率消除所有或大部分坏簇，从而得到一个近似解。

### 3. 实验设计

- **数据集**：使用了5个真实世界数据集，涵盖了不同规模和维度。
    - **小到中等规模**：Skin (245K, 3维), Shuttle (43.5K, 9维)
    - **大规模**：SUSY (5M, 18维), KDDFULL (4.9M, 37维), SIFT (100M, 128维)
    - **异常值生成**：对 Skin, SUSY, SIFT 数据集，随机注入 1% 的异常值，并设置两种噪声跨度 (ξ=5 和 ξ=10)，得到如 Skin-5, SUSY-10 等变体。Shuttle 和 KDDFULL 则直接将其最小类作为异常值。
- **Benchmark 与方法对比**：
    - 对比了5种最新的快速近似算法：
        - **LS++** (Grunau & Rozhoň, 2022)：当前先进的局部搜索算法。
        - **NKmeans** (Im et al., 2020)：基于密度的滤波方法。
        - **RobustKmeans++** (Deshpande et al., 2020)：基于采样和重加权的方法。
        - **IKmeans** (本文简化版)：仅使用 Fast-Sampling。
        - **TIKmeans** (本文完整版)：结合 Fast-Sampling 和 Center-Reduction。
    - 还与基于异常检测（ECOD, IFOREST, Sampling）结合聚类（k-means++, LSDS++）的两阶段方法进行对比。

- **实验指标**：聚类成本（Cost）、召回率（Recall，识别出的真实异常点比例）、运行时间（Time）。

### 4. 资源与算力

- **明确说明**：论文中明确指出，实验是在一台拥有 **100 个 Intel Xeon Gold 6230 CPU 和 1TB 内存** 的机器上进行的。
- **未明确说明**：论文未提及是否使用了 GPU，也未提及单次或整体实验的具体训练时长（只在结果中给出了每个算法在每个数据集上的耗时）。

### 5. 实验数量与充分性

- **实验数量**：实验非常充分。
    - **核心对比实验**：在8个数据集变体上（表2），对比了所有5种方法的成本、召回率和运行时间。
    - **参数敏感性分析**：在 Skin-5 和 Skin-10 上，对算法自身的三个参数 ε, η, δ 进行了详细的影响分析（附录C.1，图1-4）。
    - **鲁棒性分析**：在不同聚类数 `k`（5-50 不等）和不同异常值比例 `z`（1%-10% n）下，对多个数据集进行性能测试（附录C.2，表4-25）。
    - **中心数量影响分析**：测试了采样过程打开中心数量（`βk`）对最终召回率的影响（附录C.3，表26）。
    - **综合对比实验**：在8个数据集上（另加 HIGGS 数据集），与多种异常检测+聚类的两阶段方法进行对比（附录C.4，表27）。
    - **合成数据实验**：在可控的合成数据上，演示了当聚类数多、偏离大时，本文算法比 RobustKmeans++ 更有效的具体场景（附录C.5，表28）。

- **充分性与公平性**：
    - **充分性**：从标准对比到消融实验、参数敏感性、鲁棒性测试，覆盖了算法评估的多个维度，非常全面。
    - **客观性**：实验设置（如数据集划分、异常值生成方式、参数选择）均遵循了先前工作（Im et al., 2020; Deshpande et al., 2020）的惯例，保证了可比性。
    - **公平性**：所有算法都在同一硬件环境下运行，报告了最佳成本（10次运行中的最小值），并采用统一的异常值丢弃规则（丢弃离中心最远的`z`个点）。这些说明实验是公平的。

### 6. 论文的主要结论与发现

- **理论贡献**：成功设计了第一个运行时间不依赖数据纵横比 Δ 的 k-means with outliers 近似算法，打破了长久以来的性能瓶颈。具体实现了：
    - \( O(ndk \log\log n / \epsilon^2) \) 时间内实现 4-近似解（放松中心数）。
    - \( O(ndk \log\log n / \epsilon^2 + dpoly(k, 1/\epsilon) \log(n\Delta)) \) 时间内实现 O(1/ε)-近似解（精确中心数）。
- **实验贡献**：
    - **效率**：IKmeans 算法在大多数数据集上是最快的，尤其在大数据集 SIFT 上，比 RobustKmeans++ 快至少 50%。
    - **质量**：TIKmeans 算法在聚类成本和召回率上普遍优于或持平于其他先进算法，在多个数据集上成本降低了至少 4.4% 以上。
    - **鲁棒性**：算法在不同参数设定下表现稳定，且在复杂的合成数据场景下，相比 RobustKmeans++ 具有显著优势。

### 7. 优点

1.  **理论创新性强**：核心贡献是解决了算法运行时间对数据纵横比 Δ 的依赖问题，这是该领域的一个长期难点。
2.  **算法设计巧妙**：Fast-Sampling 的两阶段采样策略，巧妙地通过控制概率和来避免对最优成本的猜测，是该方法论的亮点。
3.  **理论分析完备**：提供了严谨的引理和定理证明，包括保证近似比、中心数、异常值丢弃数以及运行时间的详细推导。
4.  **实验验证全面**：从标准对比到多种消融和鲁棒性实验，论证充分，结论可信。代码和实验细节公开，结果可复现。
5.  **性能优异**：在实际大规模数据集上展示了速度和质量的显著优势，具有很高的实用价值。

### 8. 不足与局限

1.  **实验覆盖的潜在偏差**：虽然论文测试了多种真实和合成数据，但数据集的分布主要基于高斯噪声或注入点。算法的性能在**其他类型**的非高斯、流形结构或对抗性异常值下的表现尚未得到验证。
2.  **近似解与精确解的差距**：尽管理论上能达到 4-近似或 O(1/ε)-近似，但在某些对聚类精度要求极高的场景下，这仍与精确解（NP-Hard）有差距。论文未对比任何启发式的、非精确但可能质量更高的方法。
3.  **对分布假设的依赖**：虽然主要贡献在于无需分布假设，但在 Theorem 1.3 的变体中，为了获得更好的结果（只丢弃 z 个异常值），论文还是引入了“每个最优簇大小至少为 3z”的假设。这说明部分优势依赖于特定数据条件。
4.  **算法复杂度的权衡**：Center-Reduction 算法虽然能将中心数精确降为 k，但其运行时间又重新部分依赖于 Δ（`log(nΔ)` 项）。虽然依赖度已降到最低，但在 Δ 极大的极端情况下，这一部分的开销仍不可忽略。
5.  **横向对比的局限性**：实验对比主要集中在近年来的近似算法上，没有与成熟的、基于指数族模型（如 GMM）或隔离森林类（IFOREST）的传统异常检测 + 聚类两阶段方案进行更深入的对比（尽管在附录C.4做了，但主体对比仍是近似算法）。这可能让读者难以直接评估其与业界成熟方案的优势。

（完）
