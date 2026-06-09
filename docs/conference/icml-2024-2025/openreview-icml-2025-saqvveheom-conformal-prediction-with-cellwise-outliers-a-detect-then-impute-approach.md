---
title: "Conformal Prediction with Cellwise Outliers: A Detect-then-Impute Approach"
title_zh: 带有细胞级异常值的共形预测：先检测后插补的方法
authors: "Qian Peng, Yajie Bao, Haojie Ren, Zhaojun Wang, Changliang Zou"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=saqVVehEOM"
tags: ["query:anomaly-id"]
score: 8.0
evidence: 针对细胞级异常值的先检测后插补共形预测框架
tldr: 共形预测假设数据可交换，但特征中的细胞级异常值破坏该假设。本文提出先检测后插补框架，先对测试特征进行离群检测，然后插补被标记为异常的位置，并自适应地调整校准集。实验证明该方法在存在异常值时仍能保持共形预测的覆盖保证。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-saqvveheom/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1779, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-saqvveheom/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-saqvveheom/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 869, \"height\": 832, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-saqvveheom/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 875, \"height\": 764, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-saqvveheom/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 870, \"height\": 763, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-saqvveheom/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 868, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-saqvveheom/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 867, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-saqvveheom/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 866, \"height\": 280, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-saqvveheom/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 862, \"height\": 281, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-saqvveheom/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 865, \"height\": 282, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-saqvveheom/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1082, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-saqvveheom/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1081, \"height\": 536, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-saqvveheom/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1765, \"height\": 556, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-saqvveheom/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1262, \"height\": 732, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-saqvveheom/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1262, \"height\": 732, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-saqvveheom/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 866, \"height\": 620, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-saqvveheom/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 759, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-saqvveheom/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1539, \"height\": 1732, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-saqvveheom/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 870, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-saqvveheom/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 963, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-saqvveheom/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 712, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-saqvveheom/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 941, \"height\": 304, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-saqvveheom/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 996, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-saqvveheom/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1019, \"height\": 145, \"label\": \"Table\"}]"
motivation: 细胞级异常值破坏共形预测的交换性假设。
method: 提出先检测后插补框架，通过异常检测和插补处理受污染特征。
result: 该方法在保持覆盖保证的同时处理了异常值。
conclusion: 为共形预测在含异常值数据中的应用提供了理论保障方法。
---

## Abstract
Conformal prediction is a powerful tool for constructing prediction intervals for black-box models, providing a finite sample coverage guarantee for exchangeable data. However, this exchangeability is compromised when some entries of the test feature are contaminated, such as in the case of cellwise outliers. To address this issue, this paper introduces a novel framework called *detect-then-impute conformal prediction*. This framework first employs an outlier detection procedure on the test feature and then utilizes an imputation method to fill in those cells identified as outliers. To quantify the uncertainty in the processed test feature, we adaptively apply the detection and imputation procedures to the calibration set, thereby constructing exchangeable features for the conformal prediction interval of the test label. We develop two practical algorithms, $\texttt{PDI-CP}$ and $\texttt{JDI-CP}$, and provide a distribution-free coverage analysis under some commonly used detection and imputation procedures. Notably, $\texttt{JDI-CP}$ achieves a finite sample $1-2\alpha$ coverage guarantee. Numerical experiments on both synthetic and real datasets demonstrate that our proposed algorithms exhibit robust coverage properties and comparable efficiency to the oracle baseline.

---

## 论文详细总结（自动生成）

好的，遵照您的要求，以下是对该论文的详细中文总结。

---

### 论文总结：《带有细胞级异常值的共形预测：先检测后插补的方法》

#### 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：共形预测（Conformal Prediction, CP）是一种强大的不确定性量化工具，能为机器学习模型构建具有有限样本覆盖率保证的预测区间。其核心基石是**数据可交换性**假设。然而，当测试样本的特征中存在**细胞级异常值**（即特征的部分维度被污染），可交换性被破坏，标准CP的覆盖率保证会失效。例如，在医院利用康复患者数据训练的模型来预测新入院患者的发病率时，新患者的某些生物标志物可能因测量误差或自然变异而与训练集不同。
- **研究背景**：现有的应对非可交换数据的CP方法，如处理协变量漂移的加权共形预测（WCP），需要估计似然比，这在未知且难以估计的分布偏移（如细胞级异常值）下不适用。处理特征缺失的CP方法（如CP-MDA）假设缺失模式在标定集和测试集间可交换，这在本文场景中也不成立。
- **整体含义**：本研究首次探讨了在测试特征存在细胞级异常值时的预测推理问题，旨在开发一种新的CP框架，能在模型无关、分布无关的条件下，为受污染的测试数据构建有效的预测区间。

#### 2. 提出的方法论

- **核心思想**：提出**先检测后插补共形预测**框架。核心策略是：首先对测试特征进行异常值检测，并用插补方法处理被标记为异常的位置。关键创新在于，为了量化处理后特征的不确定性并恢复可交换性，**自适应地对标定集中的每个样本应用相同的检测和插补逻辑**，从而构建出与处理后的测试特征可交换的新标定特征。

- **关键技术细节**：
    1.  **检测与插补（DI）过程**：基于训练集拟合检测程序（D）和插补程序（I）。对测试特征 \(\tilde{X}_{n+1}\)，检测出异常集 \(\tilde{O}_{n+1} = D(\tilde{X}_{n+1})\)，并插补得到处理后的特征 \(\check{X}^{DI}_{n+1} = I(\tilde{X}_{n+1}, \tilde{O}_{n+1})\)。
    2.  **Oracle方法（ODI-CP）**：假设已知真实异常集 \(O^*\)，并假设检测程序具有“一定检测”性质（确保所有真实异常都被检出）。该方法在标定集上构造特征 \(\check{X}^*_i = I(X_i, \hat{O}_i \cup O^*)\)（其中 \(\hat{O}_i = D(X_i)\)），这些特征与 \(\check{X}^{DI}_{n+1}\) 是可交换的，从而能提供标准覆盖率（\(1-\alpha\)）保证。它是后续方法的理想化基准。
    3.  **代理检测-插补CP（PDI-CP）**：由于真实 \(O^*\) 未知，用检测结果 \(\tilde{O}_{n+1}\) 替换。在标定集上构造特征 \(\check{X}_i = I(X_i, \hat{O}_i \cup \tilde{O}_{n+1})\)。然后基于残差 \(|\check{R}_i|\) 构建标准分割共形预测区间（SCP）。该方法简单，但覆盖率会因检测程序的误报（将正常值误判为异常）而产生偏差。
    4.  **联合检测-插补CP（JDI-CP）**：为提供稳健的覆盖保证，采用类似Jackknife+的方法。成对地构建可交换特征：对于每个标定样本 \(i\)，构建两个特征：\(\check{X}^{n+1}_i = I(\tilde{X}_{n+1}, \hat{O}_i \cup \tilde{O}_{n+1})\)（用标定集掩码处理测试特征）和 \(\check{X}^{i}_{n+1} = I(X_i, \hat{O}_i \cup \tilde{O}_{n+1})\)（用测试特征掩码处理标定特征）。最终区间由基于 \(\check{X}^{n+1}_i\) 的预测值和基于 \(\check{X}^{i}_{n+1}\) 的残差共同构成。该方法能在有限样本下保证 \(1-2\alpha\) 的覆盖率。

- **算法流程**：
    - **PDI-CP**：1. 对测试特征进行检测 (\(\tilde{O}_{n+1}\)) 和插补 (\(\check{X}^{DI}_{n+1}\))。2. 对标定集中每个样本进行检测 (\(\hat{O}_i\)) 和插补 (\(\check{X}_i = I(X_i, \hat{O}_i \cup \tilde{O}_{n+1})\))。3. 计算标定集残差。4. 构建标准SCP区间。
    - **JDI-CP**：1. 对测试特征进行检测 (\(\tilde{O}_{n+1}\))。2. 对标定集中每个样本，用其检测结果 \(\hat{O}_i\) 和 \(\tilde{O}_{n+1}\) 构建成对特征 \(\check{X}^{n+1}_i\) 和 \(\check{X}^{i}_{n+1}\)。3. 计算基于 \(\check{X}^{i}_{n+1}\)的残差。4. 基于 \(\check{X}^{n+1}_i\) 的预测值和相关残差构建Jackknife+区间。

#### 3. 实验设计

- **数据集/场景**：
    - **合成数据**：三种不同复杂度的回归设定，包括线性同方差、非线性/重尾噪声、相关特征/异方差/重尾噪声。
    - **真实数据**：
        - **UCI Airfoil数据集**：预测机翼的声压级。
        - **巴西风方向数据集**：预测每小时的风向。
        - **核黄素生产基因表达数据集**：预测核黄素产量（该数据集本身被认为存在细胞级异常值）。
    - **异常生成**：在合成和部分真实数据实验中，以概率 \(\epsilon\) 随机将测试特征的某些单元格替换为来自任意分布（如正态分布）的噪声值。

- **基准（Benchmark）方法**：
    1.  **Oracle Baseline**：假设已知真实异常位置 \(O^*\)，对测试和标定特征进行完美的掩码和插补，代表了理论上限。
    2.  **标准SCP**：直接对受污染的测试特征和未处理的标定特征使用标准分割共形预测。
    3.  **加权共形预测（WCP）**：尝试通过估计似然比来处理分布漂移。本文中的对比证实其在此场景下无效。

- **对比方法**：
    - 论文提出的 **PDI-CP** 和 **JDI-CP**。
    - 在消融实验中，还对比了 **Naive-DI**（简单地对标定和测试数据使用相同的掩码）和 **Conservative-JDI (C-JDI)**（使用所有标定和测试特征检测结果的并集作为掩码）。

#### 4. 资源与算力

- 文中**未明确提及**所使用的GPU型号、数量或总训练时长。实验主要是基于CPU完成的中等规模（500-1000个样本）的传统机器学习模型（如B-spline）和简单神经网络，对算力需求不高。

#### 5. 实验数量与充分性

- **实验数量**：论文进行了**大量**实验来全面验证方法的有效性。
    - **合成数据**：在三种不同设定下，测试了不同污染概率（0.1, 0.15, 0.2），不同检测方法（DDC, One-class SVM, cellMCD），不同插补方法（均值、kNN、MICE），不同检测阈值，以及对不同非一致性评分（如CQR）的兼容性。总计上百个场景（每个场景200次随机试验）。
    - **真实数据**：在三个真实数据集上进行验证。
    - **消融实验**：对比了Naive-DI和C-JDI方法，以证明策略的有效性。
- **充分性**：实验**相当充分且设计严谨**。它们覆盖了方法论中的关键变量（污染率、检测器、插补器、阈值），并在合成和真实数据上都得到了验证。对比的基准方法（Oracle, SCP, WCP）合适，能够清晰地展示所提方法的优越性。
- **公平性**：实验设置规范，所有结果均为多次独立试验的平均值，提高了可靠性。对WCP方法进行了公平的说明，并解释了其在某些情况下失效的原因。

#### 6. 主要结论与发现

- 本文提出的**PDI-CP**和**JDI-CP**方法能**有效处理测试特征中的细胞级异常值**，构建出具有稳健覆盖率保证的预测区间。
- **JDI-CP**提供了**有限样本的 \(1-2\alpha\) 覆盖率保证**，在假设“一定检测”条件下，是分布无关的。这是主要的理论贡献。
- 所提方法在**经验覆盖率**上非常接近Oracle Method，且**区间长度大致相当**，表明其效率损失不大。
- 相比之下，标准SCP和WCP方法在存在细胞级异常值时**覆盖率严重不足**（甚至产生无限宽的劣质区间）。
- **JDI-CP**比**PDI-CP**更为稳健，特别是在检测程序可能产生大量误报时，它的覆盖率控制更好。

#### 7. 优点

- **理论严谨**：为提出的算法提供了坚实的理论分析，包括有限样本覆盖保证（JDI-CP）和精细化覆盖误差界（PDI-CP）。
- **方法通用**：提出的框架可以“包裹”任意的现有主流检测和插补算法，具有很强的模块化和通用性。
- **问题新颖**：首次系统性地将共形预测应用于细胞级异常值这一复杂且实际的问题上。
- **实验全面**：通过广泛的数值实验验证了方法的有效性和鲁棒性，覆盖了多种数据场景和算法组件组合。
- **分布无关**：理论结果是在分布无关的假设下成立的，这使得方法非常稳健。

#### 8. 不足与局限

- **核心假设强**：
    1.  **“一定检测”假设**：理论结果（尤其是JDI-CP的有限样本保证）依赖于检测程序能检测出所有真实异常。这在实践中可能需要设置非常激进的阈值，可能导致大量误报，影响区间效率。
    2.  **“孤立检测”假设**：部分覆盖率分析假设每个坐标的检测是独立的。论文虽在非隔离检测情况下做了误差分析，但理论保证会有所退化。
- **\(1-2\alpha\) 保证**：JDI-CP的覆盖保证是 \(1-2\alpha\) 而非标准的 \(1-\alpha\)，这是一个理论上的保守性代价。虽然这比无法保证要好，但在实践中可能意味着需要设置更低的 \(\alpha\) 来达到目标覆盖率。
- **插补方法依赖**：理论的误差界依赖于插补误差（如均值插补的 \(E_i\)）和模型对输入变化的敏感性（\(S_{\hat{\mu}}\)）。复杂的插补方法虽然效果可能更好，但理论分析会更困难。
- **应用限制**：该方法是为**测试特征**存在细胞级异常而设计的，未考虑标定集也存在异常的情况（虽然实验中对其鲁棒性进行了初步测试）。此外，方法主要针对回归问题，对分类问题的适应性和理论保证需要进一步验证。

---

（完）
