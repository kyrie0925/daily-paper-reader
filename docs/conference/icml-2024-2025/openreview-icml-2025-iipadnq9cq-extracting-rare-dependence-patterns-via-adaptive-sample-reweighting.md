---
title: Extracting Rare Dependence Patterns via Adaptive Sample Reweighting
title_zh: 通过自适应样本重加权提取罕见依赖模式
authors: "Yiqing Li, Yewei Xia, Xiaofei Wang, Zhengming Chen, Liuhua Peng, Mingming Gong, Kun Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=iIPAdNq9cq"
tags: ["query:anomaly-id"]
score: 7.0
evidence: 通过自适应样本重加权检测罕见依赖模式，可用于数据异常识别
tldr: 现有检测方法常忽略数据分布小区域中出现的罕见依赖模式，这掩盖了变量间的真实依赖结构。本文提出一种结合核独立检验与自适应样本重要性加权的测试方法，通过给表现显著依赖的数据点赋予更高权重来放大模式，从而成功检测这些罕见依赖。理论分析和实验表明该方法能有效发现隐藏的依赖结构，为异常识别提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-iipadnq9cq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 857, \"height\": 240, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iipadnq9cq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 852, \"height\": 237, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iipadnq9cq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 852, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iipadnq9cq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1773, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iipadnq9cq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1772, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iipadnq9cq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1297, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iipadnq9cq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 827, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iipadnq9cq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 832, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iipadnq9cq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1293, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iipadnq9cq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 805, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iipadnq9cq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1040, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iipadnq9cq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1243, \"height\": 414, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-iipadnq9cq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 602, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iipadnq9cq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1477, \"height\": 1259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iipadnq9cq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 821, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iipadnq9cq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1195, \"height\": 626, \"label\": \"Table\"}]"
motivation: 现有测试方法在数据分布小区域中难以检测微妙的依赖模式。
method: 结合核独立检验与自适应样本重要性加权，突出显示依赖显著的数据点。
result: 理论分析和实验验证了方法能有效检测罕见依赖模式。
conclusion: 该方法扩展了异常检测能力，适用于依赖结构发现。
---

## Abstract
Discovering dependence patterns between variables from observational data is a fundamental issue in data analysis. However, existing testing methods often fail to detect subtle yet critical patterns that occur within small regions of the data distribution--patterns we term rare dependence. These rare dependencies obscure the true underlying dependence structure in variables, particularly in causal discovery tasks. 
To address this issue, we propose a novel testing method that combines kernel-based (conditional) independence testing with adaptive sample importance reweighting. By learning and assigning higher importance weights to data points exhibiting significant dependence, our method amplifies the patterns and can detect them successfully. Theoretically, we analyze the asymptotic distributions of the statistics in this method and show the uniform bound of the learning scheme. Furthermore, we integrate our tests into the PC algorithm, a constraint-based approach for causal discovery, equipping it to uncover causal relationships even in the presence of rare dependence. Empirical evaluation of synthetic and real-world datasets comprehensively demonstrates the efficacy of our method.

---

## 论文详细总结（自动生成）

# 论文总结：Extracting Rare Dependence Patterns via Adaptive Sample Reweighting

## 1. 核心问题与整体含义
- **研究动机**：传统独立性检验（如 HSIC）在检测“罕见依赖”（rare dependence）时效果不佳。罕见依赖是指两个变量之间的依赖关系仅在数据分布的一个很小区域（例如 x≈0 附近）显著，而在大部分区域被噪声掩盖。这种模式在经济学、心理学、医学等真实场景中常见，若误判为独立会影响因果发现等下游任务。
- **整体含义**：本文试图通过自适应地重加权样本，放大那些仅在小区域内显著的依赖信号，从而提高检验的统计功效，避免遗漏关键依赖关系。

## 2. 方法论
- **核心思想**：学习一个重加权函数 β(C)（C 为参考变量，通常取 X 或 Y），使得在加权后的分布下，核依赖测度（如 HSIC 或条件 HSIC）最大化，从而突出依赖显著的子样本。
- **关键技术细节**：
  - **Reweighted HSIC (RHSIC)**：定义重加权 HSIC 为 \(\text{HSIC}_\beta(X,Y) = \| \mathbb{E}[\beta(X)(\psi_X - \mathbb{E}[\beta(X)\psi_X]) \otimes (\phi_Y - \mathbb{E}[\beta(X)\phi_Y])] \|^2_{\text{HS}}\)。其样本估计为 \(\frac{1}{n^2} \mathrm{Tr}[\mathbf{K}_X \mathbf{H}_\beta \mathbf{K}_Y \mathbf{H}_\beta]\)，其中 \(\mathbf{H}_\beta = \mathbf{D}_\beta (\mathbf{I} - \frac{1}{n}\mathbf{1}\mathbf{1}^\top \mathbf{D}_\beta)\)。
  - **优化目标**：在训练集上学习 β(·)，通过最小化 \(-\log \hat{J}_\beta + \lambda_1 \|\omega\|^2 + \frac{\lambda_2}{n}\sum_i (\beta_i - 1)^2\)，约束 \(\beta_i \ge 0, \sum \beta_i = n\)。其中第一项为负对数归一化 HSIC，第二项为 RKHS 平滑正则，第三项为方差正则以防止极端权重。
  - **数据分裂**：为避免过拟合，将样本随机分成训练集（用于学习 β）和测试集（用于计算统计量并做置换检验），分裂比例设为 0.5。
  - **条件独立性版本 (RKCIT)**：类似地，定义重加权条件 HSIC，使用核岭回归残差估计条件期望，目标函数形式相同。
  - **因果发现扩展 (RD-PC)**：将 RKCIT 嵌入 PC 算法，并引入两条规则 (Rule 1 & Rule 2) 以处理罕见依赖带来的假阳性边（如 V 结构导致的误导），最终恢复 Markov 等价类。

## 3. 实验设计
- **数据集 / 场景**：
  - **合成数据**：三种生成方式 (DG I: 类似例子 1.1 的类高斯核依赖；DG II: 基于阈值 τ 的条件依赖；DG III: 使用第三个变量 Q 控制依赖出现)。测试独立性和条件独立性的 Type I error 与 Power。
  - **真实数据**：Sachs 流式细胞仪数据（11 个蛋白，n=853），测试 (PKA, PJNK) 对的依赖性；JPY/USD 汇率与联邦基金利率数据（1990-2010，n=251），以 F 为参考变量。
  - **因果发现实验**：随机生成 6 节点、10 条边的 DAG（Erdős–Rényi），构造 C 与其子节点之间的罕见依赖，共 30 个图。
- **基准方法**：
  - 独立性检验：HSIC, RDC, FHSIC, FisherScan, LFHSIC。
  - 条件独立性检验：KCIT, RCIT, CCIT, GCIT, GCM, NNLSCIT, LPCI 等。
  - 因果发现：原始 PC 算法 + KCIT 作为基线。
- **对比方式**：幂次测试（不同样本量 n、参数 σ 或 τ、条件变量维度），Type I error 和 Power，以及因果发现的 SHD 和 F1-score。

## 4. 资源与算力
- 论文未明确说明使用的 GPU 型号、数量或训练时长。仅提到代码发布在 GitHub（https://github.com/leeedwina430/RKCIT），且优化使用 scipy 库（最大迭代 50 次），推测在常规 CPU 上即可完成（因样本规模较小）。

## 5. 实验数量与充分性
- **实验数量**：较为充分。
  - 独立性检验：对 DG I 和 DG II 分别改变 σ、τ、样本量（500~3000）做了多组实验，各至少 100 次重复，报告平均结果。
  - 条件独立性检验：改变 Z 的维度（1~10）、τ 值，在不同合成场景下与多种基线对比。
  - 因果发现：30 个随机图，样本量从 300 到 700，报告平均 SHD 和 F1。
  - 真实数据：两个真实案例展示 p-value 对比。
  - 消融分析：验证了不同核函数、不同参考变量 C、不同分裂比例对性能的影响（见附录 H）。
- **公平性**：所有对比方法使用默认或推荐参数，高斯核用中位数启发式带宽；显著性水平 α=0.05；置换检验次数 B=2000。实验设计客观，与多种最新方法对比，结果具有说服力。

## 6. 主要结论与发现
- 提出的 RHSIC 和 RKCIT 在罕见依赖场景下显著优于现有方法，尤其在依赖区域极小时（τ→0）优势明显。
- 方法能良好控制 Type I error，且在合成与真实数据上均能检测到被传统方法忽略的依赖。
- 将 RKCIT 嵌入 PC 算法后（RD-PC），能纠正因罕见依赖导致的边缺失或错误，正确恢复因果结构。
- 学习到的权重具有可解释性，例如在金融数据中，高权重样本对应 2001 年互联网泡沫和 2008 年金融危机。

## 7. 优点
- **创新性**：首次提出通过自适应样本重加权来专门检测罕见依赖，解决了传统核检验在局部依赖场景下的瓶颈。
- **理论完备**：给出了重加权统计量的渐近分布（零假设下加权 χ²，备择假设下正态），以及学习框架的一致界（uniform bound），保证了泛化性。
- **扩展性强**：将方法自然延伸到条件独立性检验和因果发现，并设计了修正规则处理潜在混淆。
- **实验扎实**：在多种合成场景、真实数据、因果发现任务中验证，并附有大量消融分析，结果可靠。

## 8. 不足与局限
- **实验覆盖**：真实数据集规模较小（Sachs 853 样本，金融 251 样本），未在更大规模、高维真实数据上验证。
- **偏差风险**：需要人为选择参考变量 C（论文建议若只观测 X,Y 则分别以 X 和 Y 为 C 取较小 p-value），但若 C 选择不当可能失效（附录表 2 显示选择 X 时 power 很低）。实际应用中可能缺乏先验知识。
- **应用限制**：方法依赖核函数的选择（推荐高斯核），且数据分裂会损失样本效率（训练集和测试集各 50%），在小样本下可能影响性能。
- **理论局限**：均匀收敛界的证明假设核有界、β 连续 Lipschitz，对某些复杂函数空间（如神经网络）需额外论证；条件独立性版本的理论界作为未来工作暂未给出。
- **计算开销**：优化过程（使用 scipy 约束优化，最大 50 步）以及置换检验（2000 次）在样本稍大时可能耗时较长，文中未提供运行时间对比。

（完）
