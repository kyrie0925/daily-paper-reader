---
title: "CostFilter-AD: Enhancing Anomaly Detection through Matching Cost Filtering"
title_zh: CostFilter-AD：通过匹配代价过滤增强异常检测
authors: "Zhe Zhang, Mingxiu Cai, Hanxiao Wang, Gaochang Wu, Tianyou Chai, Xiatian Zhu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=6p2wsBeYSs"
tags: ["query:anomaly-id"]
score: 7.0
evidence: 基于代价过滤的无监督图像异常检测
tldr: 现有无监督异常检测方法在特征匹配环节不够精确。本文将经典匹配任务中的代价过滤概念引入异常检测，通过构建输入与正常样本间的匹配代价体，并过滤不匹配区域来提升检测效果。在多个工业图像数据集上，CostFilter-AD显著提高了异常定位精度。该方法为基于重构和嵌入的异常检测提供了一种通用增强模块。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-6p2wsbeyss/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6p2wsbeyss/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1743, \"height\": 726, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6p2wsbeyss/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1757, \"height\": 630, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6p2wsbeyss/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 894, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6p2wsbeyss/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1761, \"height\": 331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6p2wsbeyss/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1762, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6p2wsbeyss/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1603, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6p2wsbeyss/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1603, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6p2wsbeyss/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1439, \"height\": 2232, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6p2wsbeyss/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1714, \"height\": 2234, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6p2wsbeyss/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1447, \"height\": 1890, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6p2wsbeyss/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1731, \"height\": 1662, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1774, \"height\": 630, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1771, \"height\": 534, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 863, \"height\": 679, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 845, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 861, \"height\": 414, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 863, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 858, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1774, \"height\": 716, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1775, \"height\": 725, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1772, \"height\": 723, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1771, \"height\": 722, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1769, \"height\": 750, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1772, \"height\": 608, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1770, \"height\": 596, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1772, \"height\": 611, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1769, \"height\": 617, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1052, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1295, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1164, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6p2wsbeyss/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1336, \"height\": 400, \"label\": \"Table\"}]"
motivation: 无监督异常检测中的特征匹配不准确导致次优检测。
method: 构建匹配代价体积并进行代价过滤，筛选出异常区域。
result: 在MVTec等数据集上异常检测和定位指标均提升明显。
conclusion: 代价过滤是提升异常检测匹配精度的有效通用手段。
---

## Abstract
Unsupervised anomaly detection (UAD) seeks to localize the anomaly mask of an input image with respect to normal samples.
Either by reconstructing normal counterparts (reconstruction-based) or by learning an image feature embedding space (embedding-based), existing approaches fundamentally rely on image-level or feature-level matching to derive anomaly scores. Often, such a matching process is inaccurate yet overlooked, leading to sub-optimal detection. To address this issue, we introduce the concept of cost filtering, borrowed from classical matching tasks, such as depth and flow estimation, into the UAD problem. We call this approach CostFilter-AD. Specifically, we first construct a matching cost volume between the input and normal samples, comprising two spatial dimensions and one matching dimension that encodes potential matches. To refine this, we propose a cost volume filtering network, guided by the input observation as an attention query across multiple feature layers, which effectively suppresses matching noise while preserving edge structures and capturing subtle anomalies. Designed as a generic post-processing plug-in, CostFilter-AD can be integrated with either reconstruction-based or embedding-based methods. Extensive experiments on MVTec-AD and VisA benchmarks validate the generic benefits of CostFilter-AD for both single- and multi-class UAD tasks. Code and models will be released at https://github.com/ZHE-SAPI/CostFilter-AD.

---

## 论文详细总结（自动生成）

# CostFilter-AD 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：无监督异常检测（Unsupervised Anomaly Detection, UAD）依赖于输入图像与正常样本之间的图像级或特征级匹配来推导异常分数。然而，现有方法（无论是基于重构的还是基于嵌入的）在匹配过程中普遍存在**内在的匹配噪声**（如模糊边缘、假阳性/假阴性、重构中的“identical shortcut”问题），导致检测性能次优。这一问题长期被忽视，成为制约UAD精度的关键瓶颈。
- **动机**：受双目立体匹配、深度估计、光流估计等经典视觉匹配任务中广泛应用**代价过滤（Cost Volume Filtering）**技术的启发，作者将其引入UAD领域，旨在显式地抑制匹配噪声、保留边缘结构并捕捉细微异常。
- **整体含义**：重新将UAD问题形式化为一个**三步流程**——特征提取、匹配代价体积构建、代价体积过滤；并提出一种通用的后处理插件 **CostFilter-AD**，可无缝集成到重构型和嵌入型UAD方法中，显著提升检测和定位精度。

## 2. 方法论：核心思想、关键技术细节

### 2.1 核心思想

将UAD视为输入图像与正常模板（重构的正常图像或随机采样的正常样本）之间的全局匹配问题，通过构建**异常代价体积**（Anomaly Cost Volume）并利用**3D U-Net**进行过滤，从而抑制匹配噪声并精细化异常定位。

### 2.2 技术细节与流程

1. **模板获取**：
   - 对**重构型方法**（如扩散模型GLAD）：从去噪过程的不同步骤（包括最终步）采样多个中间重构作为模板；利用中间重构保留的低频正常信息弥补最终步可能引入的异常泄漏。
   - 对**嵌入型方法**（如AnomalDF）：从训练集中随机选取少量（N=3）正常样本作为模板，无需大型记忆库。

2. **特征提取**（图2(b)）：使用预训练DINO（ViT-B/8）提取输入图像和N个模板的多层特征 \( f_S, f_T \in \mathbb{R}^{L \times C \times H' \times W'} \)（L层数，C通道，H'×W'空间尺寸）。

3. **异常代价体积构建**（图2(c)）：
   - 对每个空间位置进行**全局余弦相似度匹配**（公式2），生成相似度体积 \( V \in \mathbb{R}^{D \times N \times L \times H'W'} \)（D = H'×W'为匹配维度）。
   - 转换为**异常代价体积** \( C = 1 - V \)（公式3），值越大表示异常概率越高。
   - 合并D和N维度为DN，得到 \( C \in \mathbb{R}^{(DN) \times L \times H' \times W'} \)。

4. **代价体积过滤**（图2(d)）：
   - 使用**3D U-Net**（以DN为通道、L为深度、H'×W'为空间）对C进行滤波。
   - **双流注意力引导**（图2(e)）：
     - **空间引导（SG）**：输入图像特征 \( f_S \) 提供边缘等细节信息。
     - **匹配引导（MG）**：初始异常图 \( \bar{M} \)（通过全局最小池化得到）引导关注异常相关匹配维度。
     - 通过**残差通道-空间注意力（RCSA）模块**（公式4）将引导信息注入滤波过程，实现渐进去噪和边缘保持。
   - 过滤后的体积经全局最小值池化、卷积和softmax，得到最终异常得分图 \( M \)。

5. **分类自适应适配器（Class-Aware Adaptor）**：对多类别任务，通过空间平均池化聚合深层代价体积特征，生成软分类logits，动态调节分割损失（focal loss中的γ参数），提升对困难类别和样本的泛化能力。

6. **训练与推理**：
   - 训练时，合成异常样本及其掩膜作为监督；损失函数包含Focal Loss、Soft-IoU Loss、SSIM Loss和Cross-Entropy Loss（公式5）。
   - 推理时，将CostFilter-AD的输出与基线异常图加权融合（权重λ∈[0,1]）。

## 3. 实验设计

### 3.1 数据集

- **MVTec-AD**：5,324张高分辨率图像，10个物体类+5个纹理类，提供正常训练样本和带像素级标注的缺陷测试样本。
- **VisA**：10,821张图像，12个子集（包括9,621张正常、1,200张异常），覆盖表面缺陷和结构异常（如错位、缺失部件）。
- **MPDD**：1,346张图像，6个金属零件类别。
- **BTAD**：2,830张图像，3个工业类别。

### 3.2 评估指标

图像级：I-AUROC、I-AP、I-F1max；像素级：P-AUROC、P-AP、P-F1max、AUPRO。主要报告AUROC。

### 3.3 对比方法

- **多类UAD基线**：GLAD（扩散）、HVQ-Trans（Transformer）、AnomalDF（嵌入，AnomalyDINO的全样本版）、UniAD、Dinomaly。
- **其他先进方法**：JNLD、OmniAL、DiAD、VPDM、MambaAD等。

### 3.4 实现细节

- 输入分辨率：GLAD/AnomalDF为256×256，HVQ-Trans为224×224。
- 模板数：N=3（除HVQ-Trans为N=1）。
- 特征层数L=4；使用DINO ViT-B/8或EfficientNet-B4。
- 代价体积剪裁：将匹配维度DN剪裁为前D个最小通道以降低显存。
- 训练：40 epochs，batch size 8，Adam优化器，初始lr=1e-3。

## 4. 资源与算力

- **文中明确提及**：所有测量在单张**NVIDIA A100 GPU（40 GB）**上进行，batch size=1。
- **未明确说明**：训练总耗时、多卡并行情况、训练集全量训练所需的具体时数。但根据40 epochs和模型参数量（约43M额外参数）可推测训练规模适中。
- **总体评价**：算力需求合理，适合单卡场景，但未提供详细时间对比，稍显不足。

## 5. 实验数量与充分性

### 5.1 实验数量

- **多类UAD**：在MVTec-AD（15类）、VisA（12类）上分别与5个基线对比，共约10组主要对比（每个数据集每个基线±Ours）。
- **单类UAD**：在MVTec-AD和VisA上用统一多类模型评估GLAD单类结果（2组）。
- **更多基线与benchmark**：在MVTec-AD、VisA、MPDD、BTAD上进一步对UniAD和Dinomaly进行扩展（4个benchmark × 2个基线）。
- **消融实验**（表5）：对映射维度选择、模板类型（C0 vs. CN-1）、双流引导、各损失项进行逐一消融，共15组。
- **兼容性实验**（表6）：在重构型和嵌入型代价体积之间交叉训练/测试。
- **效率分析**（表7）：多基线对比参数量、FLOPs、显存、推理时间。
- **失效案例分析**（图4）。

### 5.2 充分性与公平性

- **充分性**：覆盖主流数据集、多种基线、多种评价指标，消融完整，定性可视化充分（KDE曲线、热力图、渐进去噪过程）。
- **公平性**：所有对比均保持基线原始设置（分辨率、预训练模型等），仅增加Ours模块；对于AnomalDF，统一采用动态3-shot采样以保证对比一致性；额外在原始full-shot设置下进行验证（表8），表明Ours在不同模板数和分辨率下均有效。
- **潜在偏差**：CostFilter-AD本身需要额外训练（40 epochs），而基线方法是冻结的；但这是插件式方法的正常代价，已通过效率分析显示额外开销可接受。

## 6. 主要结论与发现

1. **匹配噪声是UAD的核心障碍**：现有方法生成的异常热图常带有模糊边缘、假阳性/假阴性，使阈值化效果差；直接过滤最终得分图（如高斯滤波）不够有效。
2. **代价体积过滤有效抑制噪声**：通过构建全局匹配代价体积并用3D U-Net过滤，可保留边缘并捕捉细微异常，显著提升检测和定位性能。
3. **通用插件式设计**：CostFilter-AD可同时适用于重构型和嵌入型方法，并在多类和单类设置下均带来稳定提升。
4. **多模板和中间重构步骤有益**：使用多个模板（N>1）以及扩散模型中间去噪步骤可丰富特征表示，进一步提升效果。
5. **双流注意力引导是关键**：输入图像特征和初始异常图分别提供空间和匹配维度引导，两者互补，缺一不可。
6. **分类自适应适配器提升多类泛化**：通过动态调整损失权重，有效处理类别不平衡问题。

## 7. 优点

- **新颖视角**：首次将代价过滤概念系统引入UAD，指出并解决了匹配噪声这一长期被忽视的问题。
- **普适性强**：作为后处理插件，可与多种现有方法（重构、嵌入、扩散、Transformer）无缝集成，无需修改基线内部。
- **设计精巧**：双流注意力引导（输入特征+初始异常图）兼顾空间细节和匹配通道选择；RCSA模块通过残差连接保留细微异常信息。
- **实验扎实**：在4个数据集、超过10个基线、多种指标上验证；消融实验完整（每个组件、每种损失函数均验证）。
- **视觉解释性好**：提供KDE曲线、渐进去噪可视化、热力图对比，直观展示噪声抑制效果。

## 8. 不足与局限

- **依赖合成异常**：训练时需要合成异常样本（如GLAD使用Perlin噪声+随机遮挡），合成质量可能影响训练效果；在真实异常分布与合成分布差异大时可能泛化下降（图4失效案例中已体现）。
- **对代价体积质量敏感**：当模板特征与输入特征差异极大（如极低分辨率、视角严重不对齐），或输入特征本身不足以捕捉异常信号时，过滤后仍难以完全恢复（论文指出为未来工作方向）。
- **计算开销**：虽然文中报告额外显存和推理时间较小，但对于嵌入型方法（如AnomalDF），3D U-Net的FLOPs增加（+32.7G）相对基线（4.9G）比例较大，可能在资源受限设备上受限。
- **未展示实际工业部署场景**：实验仅基于公开数据集，未在真实产线数据或更具挑战性的长尾异常场景下验证。
- **消融实验缺少对模板数N的完整扫描**：仅默认使用N=3，未严格分析N=1,2,4,...时的性能变化曲线；附录中虽提到N=3，但未给出详细对比表格。

## （完）
