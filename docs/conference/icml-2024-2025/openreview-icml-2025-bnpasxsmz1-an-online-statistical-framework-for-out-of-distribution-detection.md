---
title: An Online Statistical Framework for Out-of-Distribution Detection
title_zh: 一种用于分布外检测的在线统计框架
authors: "Xinsong Ma, Xin Zou, Weiwei Liu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=BnPaSXSmz1"
tags: ["query:anomaly-id"]
score: 7.0
evidence: 基于在线假设检验的分布外检测框架
tldr: 现有分布外检测方法忽视决策规则的设计。本文提出g-LOND算法，从在线多重假设检验视角重新定义OOD检测，能够控制错误发现率且保证假阳性率渐进为零。理论分析和实验表明，该方法在多个基准上有效，为可靠性要求高的应用提供了理论保证的OOD检测方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-bnpasxsmz1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1733, \"height\": 990, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bnpasxsmz1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1762, \"height\": 989, \"label\": \"Table\"}]"
motivation: 现有OOD检测方法缺乏对错误发现率的理论控制。
method: 提出g-LOND算法，将OOD检测转化为在线多重假设检验问题。
result: 在多个数据集上，g-LOND有效控制FDR且FPR趋于零。
conclusion: g-LOND为可靠性要求高的应用提供了理论保证的OOD检测方案。
---

## Abstract
Out-of-distribution (OOD) detection  task  is significant   in  reliable and safety-critical applications.  Existing approaches primarily focus on developing  the powerful score function, but overlook the design of decision-making rules based on these score function. In contrast to prior studies, we rethink the OOD detection task from an perspective of online multiple hypothesis testing. We then propose a novel generalized  LOND (g-LOND) algorithm to solve the above problem. Theoretically, the g-LOND algorithm  controls false discovery rate  (FDR) at pre-specified level without the consideration for the dependence between the p-values. Furthermore, we prove that the false positive rate (FPR) of the g-LOND algorithm converges to zero in probability based on the  generalized Gaussian-like distribution family. Finally, the extensive experimental results verify the effectiveness of g-LOND algorithm for OOD detection.

---

## 论文详细总结（自动生成）

# 论文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：在安全关键应用中（如金融交易、自动驾驶），深度学习模型需要识别来自训练分布之外的输入（即分布外样本，OOD）。现有OOD检测方法主要专注于设计更强大的评分函数（如MSP、Energy、KNN等），但普遍忽视了对决策规则本身的理论设计——通常采用经验性阈值（如固定ID验证集上TPR为95%），缺乏严格的统计保证。作者指出，测试样本往往是流式到达的，因此需要一种具有理论保障的在线决策框架。
- **整体含义**：本文首次将OOD检测问题重新定义为在线多重假设检验问题，并提出了一种广义LOND（g-LOND）算法，能够在控制错误发现率（FDR）的同时，使假阳性率（FPR）渐近趋于零。这为高可靠性场景下的OOD检测提供了首个具有严格统计保证的决策规则。

## 2. 方法论：核心思想、关键技术细节、算法流程

- **核心思想**：将每个测试样本的OOD检测视为一个假设检验问题（H0：样本来自ID分布，H1：样本来自OOD分布），所有样本按流式顺序依次检验。采用经验p值（基于校准集）作为统计量，并通过在线FDR控制算法决定是否拒绝每个H0。g-LOND算法改进了经典LOND算法，使之适用于依赖的p值（如经验p值）。
- **关键技术细节**：
  - **p值计算**：对测试样本 \(X_i^{test}\)，使用评分函数 \( \hat{s}(x) = \max_i g_i / \|g\| \)（MaxNorm logit），并基于校准集 \(T_{cal}\) 计算经验p值：\( p_i = \frac{\#\{j: \hat{s}(X_j^{cal}) \le \hat{s}(X_i^{test})\} + 1}{m+1} \)。
  - **g-LOND定义**：给定预设水平α，选择函数 \(f \in \mathcal{F}_1 \cup \mathcal{F}_2\)（例如 \(f(x)=x\) 或 \(f(x)=-1/\log x\)），以及正数序列 \(\{\gamma_i\}\) 满足 \(\sum \gamma_i = 1\)。定义动态显著性水平：\(\alpha_i = \alpha \gamma_i (D(i-1)+1)\)，其中 \(D(i) = \sum_{k=1}^i \mathbf{1}(f(p_k) \le \alpha_k)\)。若 \(f(p_i) \le \alpha_i\) 则拒绝 \(H_i\)（即宣布为OOD）。
  - **理论优势**：g-LOND无需p值独立或PRDS假设，即可控制FDR；并且证明在广义高斯类分布族下，FPR依概率收敛于0。
- **算法流程**（文字描述）：
  1. 使用训练集训练评分函数 \(\hat{s}\)（如MaxNorm）。
  2. 给定校准集 \(T_{cal}\) 和测试流 \(T_{test}\)。
  3. 对每个到达的测试样本 \(X_i^{test}\)，计算其经验p值 \(p_i\)。
  4. 根据当前累计拒绝数 \(D(i-1)\)，计算 \(\alpha_i\)。
  5. 若 \(f(p_i) \le \alpha_i\)，则判定为OOD；否则为ID。

## 3. 实验设计

- **数据集与场景**：
  - **ID数据**：CIFAR-100 和 ImageNet-200。
  - **OOD数据**：
    - 对于CIFAR-100：CIFAR-10、TinyImageNet、SVHN、Texture、Places365。
    - 对于ImageNet-200：SSB-hard、NINCO、iNaturalist、Textures、OpenImage-O。
- **基准与对比方法**：共对比了13种方法：MSP、ODIN、Gram、Energy、VIM、KNN、KLM、RankFeat、DICE、ASH、Cider、SHE、PALM。
- **评价指标**：实用指标（TPR、FPR、F1-score）和经典指标（FPR95、AUROC、AUPR）。
- **骨干网络**：CIFAR-100使用ResNet18；ImageNet-200使用ResNet50。

## 4. 资源与算力

- **论文未明确说明**：文中没有提及使用的GPU型号、数量、训练时长或总计算量。实验代码基于OpenOOD v1.5框架，但算力细节缺失。

## 5. 实验数量与充分性

- **实验数量**：主要包含2组ID数据（CIFAR-100、ImageNet-200），每组分别对5个不同的OOD数据集进行测试，共10个实验场景。每个场景报告了多个指标（TPR、FPR、F1、FPR95、AUROC、AUPR），且与13种基线方法对比。未进行消融实验（如不同f函数、不同γ序列的影响），但提供了理论证明来支撑方法有效性。
- **充分性评价**：实验覆盖了常用的图像OOD检测基准，对比方法全面，指标丰富。但缺少对非图像模态（如文本、序列）的验证，也未分析校准集大小对性能的影响。总体而言，实验设计较为规范，但可进一步扩展。

## 6. 主要结论与发现

- g-LOND算法在控制FDR的同时，显著降低了FPR（即误将ID判为OOD的比例），并提高了F1-score，尽管TPR略有下降，但实现了更好的TPR-FPR权衡。
- 例如，在CIFAR-100→Place365任务中，g-LOND将FPR从最佳基线的45.63%降至30.62%，F1从42.85%提升至52.87%；在ImageNet-200→SSB-hard任务中，FPR从67.06%降至53.72%，F1从37.87%提升至49.31%。
- 在经典指标上，g-LOND的FPR95大幅降低，AUROC和AUPR也有一定提升，说明整体检测质量更优。
- 理论上证明了g-LOND无需p值独立性假设即可控制FDR，且FPR渐近收敛于0。

## 7. 优点

- **理论创新**：首次将在线FDR控制引入OOD检测，提出g-LOND算法，消除了传统LOND对p值独立性的依赖，并给出FDR和FPR的严格理论保证。
- **方法新颖**：从统计假设检验视角重新定义OOD检测决策规则，而非仅关注评分函数，开辟了新思路。
- **实验全面**：在多个图像数据集上对比了13种主流方法，验证了方法有效性和鲁棒性。
- **实际意义**：对于在线流式数据场景（如自动驾驶、金融），该框架提供了可解释的统计决策，可直接应用。

## 8. 不足与局限

- **实验覆盖有限**：仅针对图像分类任务，未涉及文本、音频、时间序列等其他模态的OOD检测。也未包括大规模数据集（如ImageNet-1K）的实验。
- **未做消融分析**：缺乏对函数族 \(f\)、序列 \(\gamma_i\)、校准集大小等超参数的敏感性实验，方法的最优配置依赖经验选择。
- **理论假设限制**：FPR渐近性的证明依赖于广义高斯类分布族，实际中评分函数分布可能偏离此假设，无法保证在所有场景下FPR收敛。
- **未讨论计算开销**：经验p值计算需要维护校准集，对于极大规模流式数据，存储和更新校准集可能带来额外成本。
- **未与最新方法比较**：对比基线截至2023年，可能未包含2024-2025年的最新OOD检测方法（如某些基于扩散模型的方法）。

（完）
