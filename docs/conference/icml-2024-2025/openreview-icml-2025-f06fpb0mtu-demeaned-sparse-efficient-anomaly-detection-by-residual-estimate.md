---
title: "Demeaned Sparse: Efficient Anomaly Detection by Residual Estimate"
title_zh: 去均值稀疏：基于残差估计的高效异常检测
authors: "Yifan Fang, Yifei Fang, Ruizhe Chen, Haote Xu, Xinghao Ding, Yue Huang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=F06FPb0Mtu"
tags: ["query:anomaly-id"]
score: 7.0
evidence: 基于频域的异常检测方法，具有理论保证
tldr: 图像异常检测方法常缺乏可解释的理论保证。本文提出基于去均值傅里叶变换（DFT）的异常检测检验，在因子模型框架下从理论上证明了检测有效性，并给出了渐近理论，解释为何能同时在图像和像素级别检测异常。基于该检验设计了DFS模块，显著提升了无监督异常检测性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-f06fpb0mtu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 835, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f06fpb0mtu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 835, \"height\": 640, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f06fpb0mtu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1775, \"height\": 770, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f06fpb0mtu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f06fpb0mtu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1732, \"height\": 669, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f06fpb0mtu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1778, \"height\": 1773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f06fpb0mtu/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1784, \"height\": 1878, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-f06fpb0mtu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1757, \"height\": 619, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f06fpb0mtu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1754, \"height\": 546, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f06fpb0mtu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1756, \"height\": 877, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f06fpb0mtu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 851, \"height\": 147, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f06fpb0mtu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1759, \"height\": 572, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f06fpb0mtu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1759, \"height\": 568, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f06fpb0mtu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1757, \"height\": 484, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f06fpb0mtu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1755, \"height\": 709, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f06fpb0mtu/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1753, \"height\": 605, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f06fpb0mtu/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1756, \"height\": 710, \"label\": \"Table\"}]"
motivation: 现有频域图像异常检测方法缺乏可解释的理论框架。
method: 提出去均值傅里叶变换（DFT）检验，结合因子模型框架，并导出DFS模块。
result: 在无监督异常检测任务中显著提升性能，并提供渐近理论保证。
conclusion: 为图像异常检测提供了一个有理论保证的高效方法。
---

## Abstract
Frequency-domain image anomaly detection methods can substantially enhance anomaly detection performance, however, they still lack an interpretable theoretical framework to guarantee the effectiveness of the detection process. We propose a novel test to detect anomalies in structural image via a Demeaned Fourier transform (DFT) under factor model framework, and we proof its effectiveness. We also briefly give the asymptotic theories of our test, the asymptotic theory explains why the test can detect anomalies at both the image and pixel levels within the theoretical lower bound. Based on our test, we derive a module called Demeaned Fourier Sparse (DFS) that effectively enhances detection performance in unsupervised anomaly detection tasks, which can construct masks in the Fourier domain and utilize a distribution-free sampling method similar to the bootstrap method. The experimental results indicate that this module can accurately and efficiently generate effective masks for reconstruction-based anomaly detection tasks, thereby enhancing the performance of anomaly detection methods and validating the effectiveness of the theoretical framework.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题背景**：现有频域图像异常检测方法虽能提升性能，但缺乏可解释的理论框架来保证检测过程的有效性。图像异常检测广泛应用于工业质检、医疗影像等场景，但异常样本稀少且多样，使得无监督方法成为主流。重建式异常检测假设模型无法准确重建训练中未出现的异常结构，通过比较原始图像与重建图像的残差来检测异常。
- **核心动机**：作者将图像异常视为一种“结构性变化”，类比时间序列分析中的Chow检验、Ljung-Box检验等。受Fu et al. (2023)在因子模型中使用DFT进行结构变化检测的启发，但原方法不适用于图像（需要处理二维横截面维度）。本文提出在因子模型框架下，利用去均值傅里叶变换（DFT）对残差进行投影，构建假设检验，并导出渐近理论，解释为何能在图像级别和像素级别检测异常，并给出理论下界。
- **整体含义**：为频域异常检测方法提供了严格的理论基础，将统计检验与深度学习重建网络结合，提出Demeaned Fourier Sparse（DFS）模块，有效提升无监督异常检测性能。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- **因子模型**：每个像素\(X_{hw}\)由公共因子\(F_w\)和因子载荷\(\lambda_{hw}\)以及特设误差\(\varepsilon_{hw}\)生成：  
  \[
  X_{hw} = \lambda_{hw}^\top F_w + \varepsilon_{hw}
  \]
  假设正常图像载荷为常数\(\lambda_{h0}\)，异常则意味着\(\lambda_{hw}\)变化。
- **假设检验**：基于残差\(\hat{\varepsilon}_{hw}\)构造复值经验过程\(\hat{C}(u,v)\)，利用去均值傅里叶变换\(\phi(u,v)\)投影，设计检验统计量\(\hat{D}\)。原假设\(H_0\)（无异常）下，\(\hat{C}\)逼近零谱；备择假设\(H_A\)下，出现非零谱。
- **渐近理论**：
  - 原假设下：\(\hat{C}(u,v) \Rightarrow H^{-1/2}W^{-1/2}G(u,v)\)（均值为零的高斯过程）。
  - 全局功效：当估计因子数\(K <\)真实因子数\(R\)时，\(\hat{D} > c_{HW}\)的概率趋于1，图像级检测有效。
  - 局部功效：在局部备择\(H_A(\tau_{HW})\)下，\(\tau_{HW}=H^{-1/2}W^{-1/2}\)时，检测下界成立，可检测微小异常。

### 关键技术细节
- **DFS模块**：将输入图像\(X\)通过傅里叶变换，学习一个二进制掩码\(M\)（通过Bernoulli采样和反sigmoid映射），对频谱的实部和虚部进行元素级相乘，实现“去均值”和“稀疏化”（削减主要信息，增加残差），再通过逆傅里叶变换得到\(\hat{X}\)，送入重建网络。
- **采样方法**：类似于Bootstrap的无分布采样：从[0,1]均匀分布中采样\(\omega\)，映射到可优化变量\(\hat{\omega}\)，通过sigmoid得到概率图\(p=\sigma(\hat{\omega})\)，加上来自(0,1)的样本\(s\)，生成掩码\(M = \sigma(\sigma(\hat{\omega})-s)\)。
- **优化损失**：总损失\(L = L_{Rec} + \alpha L_{Reg}\)，其中\(L_{Rec}\)包含L2损失、SSIM损失、多尺度梯度相似性损失；\(L_{Reg} = \|M\|_1\)用于稀疏化。前一半训练轮次使用正则项，后一半固定掩码只训练重建网络。

## 3. 实验设计

### 数据集
- **MVTec-AD**：5,354张彩色图像，10个物体类别+5个纹理类别，包含像素级标注。训练集3,629张正常图像，测试集1,725张（含正常和异常）。
- **VisA**：10,821张图像，12个物体（分为复杂结构、多实例、单实例三个域），训练集8,721张正常图像，测试集2,100张。

### 评估指标
- 图像级AUROC（Img-AUROC）、像素级AUROC（Pix-AUROC）、每区域重叠率（PRO）。使用这些指标替代统计检验的p值，以适应异常稀疏性。

### 对比方法
- 特征基方法：PatchCore、PyramidFlow、SSNF。
- 重建基方法：DRAEM、IFgNet、TransFusion。
- 额外设置“Ours-Base”（移除DFS模块，仅保留重建网络U-Net）以验证DFS模块效果。

### 实验内容
- **主要结果**：在MVTec-AD和VisA上报告三个指标的平均值和每类结果（表1、表2）。
- **分辨率变化实验**：在256×256、512×512、1024×1024下比较Ours-Base与Ours（表3），验证渐近全局功效。
- **超参数选择研究**（附录D）：改变采样函数（均匀分布 vs. 正态分布）、mask采样阈值均值\(\mu_s\)（0.1~0.9）、采样轮数N（5~35）、正则化系数\(\alpha\)等，观察性能变化（表5-表10）。
- **计算成本对比**（表4）：报告参数量和FLOPs。
- **定性结果**（图3、图4）：展示异常定位热力图和中间步骤可视化。

## 4. 资源与算力

- **GPU**：所有实验在单张NVIDIA RTX 3090 GPU上完成。
- **训练设置**：输入分辨率256×256，重建网络为vanilla U-Net，训练800个epoch，batch size=2，Adam优化器（初始学习率1e-4，在640和720 epoch衰减0.2倍）。正则化系数\(\alpha=1e-6\)。
- 未明确说明总训练时长或模型数量，但单卡单次训练可在合理时间内完成（800 epochs，batch size 2）。

## 5. 实验数量与充分性

- **数量**：在MVTec-AD（15类）和VisA（12类）上进行了全面的定量和定性比较；消融实验涵盖了超参数（采样函数、\(\mu_s\)、N、\(\alpha\)）、分辨率变化（3种）、计算成本对比等。还包括定性可视化（多个示例）。
- **充分性**：
  - 对比方法涵盖了近年代表性方法（特征基和重建基），且包含自身消融（Ours-Base）。
  - 消融实验系统性强，验证了DFS模块的有效性、理论下界（PRO提升明显）、以及超参数稳定性。
  - 但实验未涉及其他类型的异常检测数据集（如医疗、视频），也未与其他理论驱动的异常检测方法（如基于噪声模型的）进行比较。此外，所有实验使用同一重建网络（U-Net），未尝试不同骨架，可能影响泛化性。

## 6. 主要结论与发现

- **理论有效**：提出的基于DFT的假设检验具有渐近正态性、全局功效和局部功效，能够从理论上保证图像级和像素级异常检测的有效性。
- **DFS模块提升显著**：相比Ours-Base，在MVTec-AD上Img-AUROC提升3.65%，Pix-AUROC提升1.73%，PRO提升9.14%；在VisA上分别提升1.46%、0.56%、5.02%。PRO的大幅提升证实了局部功效理论（对微小异常敏感）。
- **超参数鲁棒**：采样函数、\(\mu_s\)、N在较宽范围内性能稳定。
- **计算效率**：参数量和FLOPs明显低于大多数重建基方法（如DRAEM、IFgNet、TransFusion），接近PatchCore的特征提取部分。
- **分辨率可推广**：在更大分辨率下，DFS模块能保持较好性能，而基线退化严重，验证了全局（大样本）下的检测能力。

## 7. 优点

- **理论创新**：首次将因子模型的结构变化检验系统应用于图像异常检测，并给出完整的渐近分布证明，填补了频域方法缺乏理论保证的空白。
- **方法简洁有效**：DFS模块通过可学习的傅里叶掩码实现去均值和稀疏化，无需额外数据增强或外部先验，通用性强，可嵌入任意重建网络。
- **实验设计严谨**：
  - 包含自身消融（Ours-Base），直接验证模块贡献。
  - 消融研究覆盖关键超参数，且显示鲁棒性。
  - 在不同分辨率下的实验验证了渐近理论（图像越大，优势越明显）。
- **代码可复现性**：使用公开数据集、标准网络U-Net、固定随机种子等，有利于复现。

## 8. 不足与局限

- **实验覆盖有限**：
  - 仅使用MVTec-AD和VisA两个工业数据集，未涉及医学影像、视频异常、自然图像异常等场景，通用性有待验证。
  - 重建网络仅使用U-Net，未尝试其他架构（如Autoencoder、Diffusion模型），DFS模块的通用性未被充分检验。
- **计算资源**：虽效率优于多数重建方法，但800个epoch的训练周期较长，且未提供训练时间的具体数值。
- **理论假设可能过于严格**：如假设残差形成鞅差序列、因子载荷协方差正定等，实际图像数据可能不完全满足，但实验显示对真实数据仍有效。
- **对比方法公平性**：对比方法中有些使用了外部数据或预训练模型（如DRAEM使用合成异常、PatchCore使用ImageNet预训练），而本文方法仅用正常图像训练，虽在部分指标上领先，但对比条件不完全一致。
- **定性结果仅展示少量案例**：可视化仅选取几个典型样本，未能全面反映各类异常（特别是伪阴性情况）的定位效果。
- **超参数选择**：\(\alpha=1e-6\)和mask固定时机（第400 epoch）是否有理论依据？消融实验表明\(\alpha\)在1e-6附近最佳，但对于其他网络或数据集可能需要重新调整。

（完）
