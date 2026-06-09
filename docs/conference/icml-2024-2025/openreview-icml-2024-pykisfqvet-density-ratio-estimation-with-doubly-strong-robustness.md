---
title: Density Ratio Estimation with Doubly Strong Robustness
title_zh: 双重强鲁棒性的密度比估计
authors: "Ryosuke Nagumo, Hironori Fujisawa"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=PykISfqvet"
tags: ["query:anomaly-id"]
score: 6.0
evidence: 对异常值具有鲁棒性的密度比估计方法
tldr: 针对密度比估计易受异常值影响的问题，本文提出基于加权KL散度和γ散度的两种方法（Weighted DRE和γ-DRE），通过对异常样本加权削弱其影响，实现对参考分布和目标分布双重鲁棒。数值实验表明新方法比现有方法更鲁棒，可用于异常检测等任务。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-pykisfqvet/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 842, \"height\": 842, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-pykisfqvet/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1677, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-pykisfqvet/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1382, \"height\": 579, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-pykisfqvet/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1740, \"height\": 767, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-pykisfqvet/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1426, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-pykisfqvet/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1429, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-pykisfqvet/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1426, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-pykisfqvet/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1741, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-pykisfqvet/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1777, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-pykisfqvet/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1502, \"height\": 423, \"label\": \"Table\"}]"
motivation: 现有密度比估计方法对异常值敏感，本文旨在开发对双分布异常均鲁棒的方法。
method: 提出Weighted DRE（凸优化）和γ-DRE（DC优化），引入权重函数减弱异常值影响。
result: 实验显示两种方法在异常污染下均比传统方法更鲁棒，γ-DRE在强污染下表现更好。
conclusion: 提出的双重鲁棒密度比估计方法可有效抑制异常值，扩展了密度比估计的应用。
---

## Abstract
We develop two density ratio estimation (DRE) methods with robustness to outliers. These are based on the divergence with a weight function to weaken the adverse effects of outliers. One is based on the Unnormalized Kullback-Leibler divergence, called Weighted DRE, and its optimization is a convex problem. The other is based on the γ-divergence, called γ-DRE, which improves a normalizing term problem of Weighted DRE. Its optimization is a DC (Difference of Convex functions) problem and needs more computation than a convex problem. These methods have doubly strong robustness, which means robustness to the heavy contamination of both the reference and target distributions. Numerical experiments show that our proposals are more robust than the previous methods.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：密度比估计（DRE）是直接估计两个概率密度函数比值的方法，广泛应用于变化检测、异常检测、协变量偏移适应等。但在实际应用中，参考分布和目标分布都可能被异常值污染（如传感器数据中的离群点），此时传统DRE方法估计偏差大、不稳定。现有鲁棒方法（如Trimmed DRE）仅假设仅参考分布被污染且异常值对应的密度比更大，局限性很强。
- **动机**：开发同时对参考分布和目标分布均具有强鲁棒性（即“双重强鲁棒性”）的DRE方法，且鲁棒性不依赖于异常比例大小。
- **整体含义**：通过引入权重函数减弱异常值影响，理论上证明估计偏差可被控制到很小，实验验证在多种污染场景下性能显著优于已有方法。

## 2. 方法论
### 核心思想
- 在Bregman散度或γ-散度中引入一个权重函数 \(w(x)\)，使异常值所在区域的贡献被抑制。权重函数需比密度比函数（如 \(\exp(\theta^\top h(x))\)）衰减更快，以忽略异常分布。

### 两种具体方法
#### （1）Weighted DRE（基于UKL散度）
- **目标函数**：最小化带权的无归一化Kullback-Leibler（UKL）散度，表达式为：
  \[
  \hat{D}_{\text{UKL}}(r, r_\theta; w) = -\frac{1}{n_p}\sum_i \theta^\top h(x_i^{(p)}) w(x_i^{(p)}) + \frac{1}{n_p}\sum_i w(x_i^{(p)}) \cdot \log\left(\frac{1}{n_q}\sum_j \exp(\theta^\top h(x_j^{(q)})) w(x_j^{(q)})\right)
  \]
- **优化**：该函数关于 \(\theta\) 是凸的，可通过梯度下降或拉格朗日对偶方法高效求解。
- **缺点**：需要估计归一化项 \(C\)（由参考和目标样本共同计算），在强污染下可能不准确。

#### （2）γ-DRE（基于γ-散度）
- **目标函数**：最小化带权的γ-交叉熵（无需估计归一化项）：
  \[
  \hat{d}_\gamma(r, r_\theta; w_q) = -\frac{1}{\gamma}\log\left(\frac{1}{n_p}\sum_i \exp(\gamma\theta^\top h(x_i^{(p)})) w(x_i^{(p)})\right) + \frac{1}{1+\gamma}\log\left(\frac{1}{n_q}\sum_j \exp((1+\gamma)\theta^\top h(x_j^{(q)})) w(x_j^{(q)})\right)
  \]
- **优化**：这是一个DC（凸函数差）问题，可通过迭代求解：每次迭代求解一个凸子问题（利用Fenchel-Rockafellar对偶），计算量比凸问题大。
- **优点**：无需估计归一化项，提高了稳定性。

### 权重函数选择
- 推荐使用 \(w(x)=\exp\left(-\frac{\|x-\text{Med}\|_4^4}{\tau\cdot \text{MADN}^4}\right)\)，其中 Med 为中位数，MADN 为归一化中位绝对偏差，\(\tau\) 为超参数（通过实验或经验选择，使正常样本权重接近1，异常样本权重接近0）。

### 理论性质
- 在合理假设下（异常分布被权重函数充分抑制），两种方法的估计偏差与污染比例和异常项乘积同阶，即 \(\theta^\dagger - \theta^* = O(\varepsilon_r \nu)\)，实现“双重强鲁棒性”。

## 3. 实验设计
- **合成数据实验**：2维正态分布中，估计参考和目标分布的精度矩阵差（参数 \(\theta_{1,2}\)）。设置四种污染场景：干净、仅参考污染、仅目标污染、双重污染（污染比例各20%）。对比方法：标准DRE、Trimmed DRE、Weighted DRE、γ-DRE。数据集大小 \(n_p=n_q=100\)。
- **真实数据实验**：HASC Challenge 2011人类活动加速度传感器时间序列数据（3维），任务为变化检测（分割6类活动）。参数为3×3的二次型 \(\theta_{u,v}\)，使用弹性网络正则化。对比方法同上。数据集每段100个样本。
- **额外对比**（附录F）：与稳定DRE方法RuLSIF对比，在相同异常不同异常位置场景下测试。

## 4. 资源与算力
- **未明确说明**：论文未提及使用的GPU型号、数量或训练时长。所有实验基于CPU即可完成（二维合成数据和低维时间序列，参数规模小）。因此无法评估算力需求。

## 5. 实验数量与充分性
- **合成实验**：对9组不同真实参数（\(\theta_{1,2}\)从-1.6到1.6）进行100次重复，计算MSE和标准差，共4种污染设置（4×9=36组实验），结果以表格和热力图展示。实验覆盖了不同污染类型和参数范围，统计上较充分。
- **真实数据实验**：仅1个时间序列（120个时间点），定性展示参数随时间变化，未提供量化指标（如F1分数）。实验数量较少，但作为案例验证了方法在实际场景中的有效性。
- **消融/超参数研究**：无正式的消融实验或超参数敏感性分析。权重函数\(\tau\)和\(\gamma\)的选取仅给出示例说明，未系统讨论。
- **公平性**：Trimmed DRE的修剪分位数设为真实污染比例（0.2或0.9），属于“最佳条件”比较，而实际中很难预知真实比例，可能高估了其性能。γ-DRE的γ固定为0.01，Weighted DRE的\(\tau\)手动选取，缺乏自动调优。

## 6. 主要结论与发现
- Weighted DRE和γ-DRE在所有污染场景下都能准确估计密度比参数，而标准DRE和Trimmed DRE在双重污染或目标污染下严重偏离。
- γ-DRE通常比Weighted DRE具有更小的MSE，因其避免了归一化项的不稳定性。
- 在真实时间序列数据上，Weighted DRE和γ-DRE成功检测到活动变化点，且未受明显异常值干扰，而对比方法产生了虚假检测。
- 理论分析表明，两种方法对参考和目标分布的异常比例均不敏感（偏差只依赖于异常项\(\nu\)，与\(\varepsilon\)大小弱相关），实现了“双重强鲁棒性”。

## 7. 优点
- **理论创新**：首次提出针对双分布污染的强鲁棒DRE方法，并给出严格的偏差上界。
- **方法实用性**：Weighted DRE是凸优化，易于实现和扩展；γ-DRE虽非凸但可通过DC规划有效求解，且避免了估计归一化项。
- **实验验证干净**：在多种污染设置下与基线方法对比，结果清晰展示了鲁棒性优势。
- **权重设计**：基于中位数和MADN的权重函数具有实际可操作性，适用于高维数据。

## 8. 不足与局限
- **实验覆盖有限**：仅使用2维合成数据和1个时间序列数据集，未在更高维、更复杂的数据（如图像、文本）上验证。缺乏与其他先进鲁棒DRE（如基于深度学习的鲁棒方法）的比较。
- **超参数敏感**：权重函数中的 \(\tau\) 和 γ 的取值缺乏自动选择机制或敏感性分析，实际应用中可能需人工调参。
- **对比方法条件偏优**：Trimmed DRE使用了真实污染比例作为修剪分位数，而实际中难以获取，导致对比不公平。
- **时间序列实验缺少定量指标**：仅可视化展示，未计算精度、召回等指标，说服力不足。
- **可扩展性未讨论**：高维场景下计算DC规划迭代的代价可能较高，论文未分析时间复杂度。

（完）
