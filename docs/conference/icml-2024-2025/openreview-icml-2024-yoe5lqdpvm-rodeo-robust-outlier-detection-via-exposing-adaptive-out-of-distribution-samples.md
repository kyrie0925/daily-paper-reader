---
title: "RODEO: Robust Outlier Detection via Exposing Adaptive Out-of-Distribution Samples"
title_zh: RODEO：通过暴露自适应分布外样本实现鲁棒异常检测
authors: "Hossein Mirzaei, Mohammad Jafari, Hamid Reza Dehbashi, Ali Ansari, Sepehr Ghobadi, Masoud Hadi, Arshia Soltani Moakhar, Mohammad Azizmalayeri, Mahdieh Soleymani Baghshah, Mohammad Hossein Rohban"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=yOe5lqDPvM"
tags: ["query:anomaly-id"]
score: 8.0
evidence: 通过自适应异常样本实现鲁棒异常检测
tldr: 该论文针对对抗环境下异常检测鲁棒性不足的问题，提出RODEO方法，通过结合异常暴露与对抗训练生成多样化的训练异常样本。实验表明该方法在标准与对抗场景下均显著提升检测性能，其核心思想可迁移至海洋数据的异常检测任务。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-yoe5lqdpvm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 864, \"height\": 686, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-yoe5lqdpvm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1775, \"height\": 1033, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-yoe5lqdpvm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1672, \"height\": 721, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-yoe5lqdpvm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1772, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-yoe5lqdpvm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1787, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-yoe5lqdpvm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 884, \"height\": 884, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-yoe5lqdpvm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1733, \"height\": 2121, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-yoe5lqdpvm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1736, \"height\": 2136, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-yoe5lqdpvm/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1733, \"height\": 2135, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-yoe5lqdpvm/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1731, \"height\": 2132, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-yoe5lqdpvm/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1737, \"height\": 2136, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-yoe5lqdpvm/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1731, \"height\": 2138, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-yoe5lqdpvm/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1732, \"height\": 1639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-yoe5lqdpvm/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1733, \"height\": 1626, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-yoe5lqdpvm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1773, \"height\": 486, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-yoe5lqdpvm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 872, \"height\": 477, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-yoe5lqdpvm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 872, \"height\": 482, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-yoe5lqdpvm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1767, \"height\": 574, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-yoe5lqdpvm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1774, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-yoe5lqdpvm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1768, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-yoe5lqdpvm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1773, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-yoe5lqdpvm/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1774, \"height\": 349, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-yoe5lqdpvm/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1764, \"height\": 1011, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-yoe5lqdpvm/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1738, \"height\": 1073, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-yoe5lqdpvm/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1772, \"height\": 1465, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-yoe5lqdpvm/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1764, \"height\": 687, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-yoe5lqdpvm/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1762, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-yoe5lqdpvm/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1778, \"height\": 846, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-yoe5lqdpvm/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1386, \"height\": 110, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-yoe5lqdpvm/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1409, \"height\": 109, \"label\": \"Table\"}]"
motivation: 现有异常检测方法在对抗环境下性能下降。
method: 采用数据驱动策略，集成异常暴露与对抗训练生成有效异常样本。
result: 在多个图像数据集上显著提升了鲁棒异常检测性能。
conclusion: 为鲁棒异常检测提供了有效范式，可扩展到海洋数据异常检测。
---

## Abstract
In recent years, there have been significant improvements in various forms of image outlier detection. However, outlier detection performance under adversarial settings lags far behind that in standard settings. This is due to the lack of effective exposure to adversarial scenarios during training, especially on unseen outliers, leading detection models failing to learn robust features. To bridge this gap, we introduce RODEO, a data-centric approach that generates effective outliers for robust outlier detection. More specifically, we show that incorporating outlier exposure (OE) and adversarial training could be an effective strategy for this purpose, as long as the exposed training outliers meet certain characteristics, including diversity, and both conceptual differentiability and analogy to the inlier samples. We leverage a text-to-image model to achieve this goal. We demonstrate both quantitatively and qualitatively that our adaptive OE method effectively generates ''diverse'' and ''near-distribution'' outliers, leveraging information from both text and image domains. Moreover, our experimental results show that utilizing our synthesized outliers significantly enhances the performance of the outlier detector, particularly in adversarial settings.

---

## 论文详细总结（自动生成）

## 论文详细中文总结

### 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：现有的图像异常检测（Outlier Detection）方法在标准设置下已有显著进步，但在对抗攻击（adversarial attacks）环境下性能急剧下降，有时甚至低于随机检测。主要原因是训练中缺乏对异常样本的对抗场景暴露，尤其对未见过的异常样本，导致模型无法学到鲁棒特征。
- **核心挑战**：如何生成有效的训练异常样本，使其同时具备 **多样性**、**近分布性**（near-distribution）、且与正常样本在概念上可区分但也具有类比性，以辅助对抗训练提升鲁棒性。
- **整体含义**：提出一种数据驱动的自适应异常暴露方法，通过结合异常暴露（OE）和对抗训练，显著提升异常检测模型在对抗环境下的鲁棒性。

### 2. 方法论

- **核心思想**：利用文本到图像扩散模型，根据正常样本的标签信息，自适应地生成多样且近分布的异常样本，用于对抗训练。
- **关键技术细节**：
  - **步骤1：近分布异常标签提取（Near-Outlier Label Extraction）**：使用Word2Vec和CLIP文本编码器，从正常样本标签出发，检索语义相近但不同的候选标签，并设置标签相似度阈值（基于ImageNet验证集计算）过滤掉过于相似的标签。同时加入负属性形容词（如“broken”、“cracked”）以生成像素级异常标签，增强多样性。
  - **步骤2：自适应异常生成（Adaptive Generation）**：采用预训练的GLIDE扩散模型，将正常样本作为起始点（而非随机噪声），从时间步 t0 ~ U(0.3T, 0.6T)开始反向去噪。去噪过程中，利用 **CLIP Guidance** 损失函数：
    \[
    L_{guidance}(x_{gen}, y_{n-outliers}) = -D(E_I(x_{gen}), E_T(y_{n-outliers}))
    \]
    其中 D(⋅,⋅) 为余弦相似度，E_I 和 E_T 分别为CLIP图像和文本编码器。通过梯度引导，逐步将正常样本向异常标签方向转换。
  - **步骤3：过滤生成图像**：计算生成图像与正常标签的CLIP相似度，若超过阈值（基于ImageNet计算的CLIP分数均值得出），则认为属于正常分布，予以剔除。
  - **步骤4：对抗训练**：使用原始正常样本（K类）和生成的异常样本（标记为第K+1类）混合形成训练集，采用PGD-10进行对抗训练，优化交叉熵损失。
- **算法流程**（文字说明）：输入正常样本集和验证集，提取近分布异常标签 → 对每个正常样本随机选择一个异常标签，从随机时间步开始扩散并施加CLIP引导 → 过滤掉未超出阈值的生成样本 → 将生成异常加入训练集，进行对抗训练（Adam + PGD-10） → 测试时使用第K+1个logit作为异常分数。

### 3. 实验设计

- **使用数据集与场景**：涵盖三大异常检测场景：
  - **新颖性检测（Novelty Detection, ND）**：每个类别逐一作为正常类，其余为异常。数据集包括CIFAR10、CIFAR100、MNIST、FashionMNIST、SVHN、MVTecAD、Head-CT、BrainMRI、Tumor Detection、Covid19、ImageNet-30。
  - **开放集识别（Open-Set Recognition, OSR）**：随机将类别按60/40分正常/异常，重复5次。数据集：MNIST、FashionMNIST、CIFAR10、CIFAR100。
  - **分布外检测（Out-of-Distribution Detection, OOD）**：CIFAR10或CIFAR100作为正常集，多种OOD数据集作为测试（如MNIST、TinyImageNet、Places365、LSUN、iSUN、Birds、Flowers、COIL-100等）。
- **Benchmark**：对抗设置下采用 **PGD-1000**（10个随机重启，1000步）、**AutoAttack (AA)**、**Adaptive AutoAttack (A3)**，ϵ 分别设为8/255（低分辨率）和2/255（高分辨率）。同时报告clean设置结果。
- **对比方法**：包括标准方法（CSI、MSAD、Transformaly、PatchCore）、鲁棒方法（PrincipaLS、OCSDF、APAE、EXOE、ATOM、ALOE、ATD、PLP），以及基于CLIP的方法（EXOE、PLP）。消融实验中对比了其他OE生成方法（Gaussian Noise、ImageNet、MixUp、FITYMI、GOE、Dream-OOD）。

### 4. 资源与算力

- 论文明确说明：实验在 **RTX 3090 GPU** 上完成。
- 生成约1万张低分辨率或1千张高分辨率异常数据约需 **1小时**。
- 单类新颖性检测训练时间：低分辨率数据集每类约 **100分钟**；OOD检测约 **16小时**；OSR每实验约 **9小时**。
- 总体算力需求较高，但未给出总GPU数量。

### 5. 实验数量与充分性

- **实验数量丰富**：
  - ND场景：涵盖11个数据集、每数据集多类，平均AUROC报告；并附有每类详细结果（附表3、5）。
  - OSR场景：4个数据集，每个随机5次重复。
  - OOD场景：两组正常集，各9个OOD数据集。
  - 对抗攻击：3种强攻击（PGD-1000、AA、A3），同时包含黑盒攻击。
  - 消融实验：对比7种不同OE生成方法，并在ND设置下对各数据集报告结果，同时使用FDC指标衡量生成质量。
  - 理论分析部分：提供两个定理证明近分布和多样性的重要性。
- **充分性与客观性**：实验设计较为完整，对比方法充分，包含标准方法和前沿鲁棒方法，且自行统一了攻击强度和评估范围（针对所有测试样本，而非仅异常样本），体现了公平性。消融实验也有定量指标支撑。

### 6. 主要结论与发现

- 利用 **自适应生成的近分布、多样异常样本**进行对抗训练，能大幅提升异常检测在对抗攻击下的鲁棒性，在ND、OSR、OOD三个场景下，RODEO在对抗设置中AUROC比其他方法提高最高 **50%**，在clean设置下也保持竞争性。
- **OE样本需具备近分布性和多样性**，理论证明和实验均支持这一观点。
- 相比其他合成OE方法（如Dream-OOD），RODEO在近分布性和多样性上更优，因此在鲁棒检测中效果更佳。

### 7. 优点

- **创新性**：首次将CLIP引导扩散模型用于自适应异常样本生成，同时利用图像和文本信息，生成同时具备像素级和语义级异常的样本。
- **鲁棒性显著**：在多个强对抗攻击下性能远超现有方法，且对未见过的异常域（如医学图像）也能生成有效异常，泛化能力强。
- **理论支撑**：提供定理分析近分布和多样性对鲁棒检测的必要性，使方法有理论依据。
- **实验全面**：覆盖多种场景、多种攻击、多种对比方法，消融实验系统。

### 8. 不足与局限

- **Clean性能下降**：虽然鲁棒性提升很大，但clean设置下的性能（如ND平均83.7%）不如一些最优标准方法（如EXOE在CIFAR10上clean 99.6%）。这是鲁棒性与准确性的固有权衡，论文也承认。
- **依赖标签信息**：方法假设已知正常样本的文本标签，并需借助Word2Vec和CLIP进行标签提取。这限制了在完全无标签场景下的应用。
- **算力需求高**：生成和训练均需大量GPU资源，不利于资源受限场景。
- **实验覆盖偏差**：高分辨率数据集上（如MVTecAD）RODEO在对抗下性能较低（PGD仅14.9%），且生成异常质量FID较高；在SVHN等噪声大、纹理差异大的数据集上鲁棒提升也有限。
- **未在纯无监督设置下验证**：论文未讨论无标签时的替代方案。
- **阈值设定依赖验证集**：文本和图像过滤阈值通过ImageNet计算，可能对域偏移敏感。

（完）
