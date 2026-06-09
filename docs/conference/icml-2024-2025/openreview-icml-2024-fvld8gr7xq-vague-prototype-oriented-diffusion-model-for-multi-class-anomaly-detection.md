---
title: Vague Prototype-Oriented Diffusion Model for Multi-Class Anomaly Detection
title_zh: 面向模糊原型的多类异常检测扩散模型
authors: "Yuxin Li, Yaoxuan Feng, Bo Chen, Wenchao Chen, Yubiao Wang, Xinyue Hu, Baolin Sun, Chunhui Qu, Mingyuan Zhou"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=FvLd8Gr7xq"
tags: ["query:anomaly-id"]
score: 9.0
evidence: 基于扩散模型的多类无监督异常检测
tldr: 多类无监督异常检测中，重建模型常因异常信息泄露导致‘相同捷径’问题。本文提出VPDM，利用仅包含目标模糊信息的原型作为条件，防止异常信息渗透。在多个基准数据集上，VPDM显著优于现有方法，为多类异常检测提供了新范式。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-fvld8gr7xq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1687, \"height\": 787, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fvld8gr7xq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1555, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fvld8gr7xq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1548, \"height\": 499, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fvld8gr7xq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1199, \"height\": 2121, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fvld8gr7xq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1455, \"height\": 2150, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fvld8gr7xq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1464, \"height\": 1200, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fvld8gr7xq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1373, \"height\": 2155, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fvld8gr7xq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1459, \"height\": 2304, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fvld8gr7xq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1465, \"height\": 1318, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-fvld8gr7xq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 624, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fvld8gr7xq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1695, \"height\": 552, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fvld8gr7xq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 783, \"height\": 349, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fvld8gr7xq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1694, \"height\": 332, \"label\": \"Table\"}]"
motivation: 重建模型在多类异常检测中面临‘相同捷径’问题，导致异常输出。
method: 提出模糊原型导向的扩散模型，仅使用模糊信息避免异常泄露。
result: 在MVTec等数据集上达到SOTA性能。
conclusion: VPDM有效解决了多类异常检测中的关键难题。
---

## Abstract
Multi-class unsupervised anomaly detection aims to create a unified model for identifying anomalies in objects from multiple classes when only normal data is available. In such a challenging setting, widely used reconstruction-based networks persistently grapple with the "identical shortcut" problem, wherein the infiltration of abnormal information from the condition biases the output towards an anomalous distribution. In response to this critical challenge, we introduce a Vague Prototype-Oriented Diffusion Model (VPDM) that extracts only fundamental information from the condition to prevent the occurrence of the "identical shortcut" problem from the input layer. This model leverages prototypes that contain only vague information about the target as the initial condition. Subsequently, a novel conditional diffusion model is introduced to incrementally enhance details based on vague conditions. Finally, a Vague Prototype-Oriented Optimal Transport (VPOT) method is proposed to provide more accurate information about conditions. All these components are seamlessly integrated into a unified optimization objective. The effectiveness of our approach is demonstrated across diverse datasets, including the MVTec, VisA, and MPDD benchmarks, achieving state-of-the-art results.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）
- **问题**：多类无监督异常检测（Multi-class Unsupervised Anomaly Detection）旨在仅使用正常样本训练一个统一模型，检测来自多个类别的异常。现有基于重构的模型普遍存在“相同捷径”（identical shortcut）问题：当输入样本包含异常信息时，这些异常信息会渗透到重构条件中，导致模型能够成功重构异常样本，从而降低检测效果。
- **挑战**：在多类场景下，正常数据分布更加复杂，加剧了“相同捷径”问题。已有的扩散模型（如DiAD、LafitE）虽然通过丰富条件信息提高生成质量，但条件中仍可能保留异常信息，无法从根本上解决问题。
- **核心思想**：受人类记忆检索机制启发（先回忆形状、颜色等模糊元素，再逐步补充细节），本文提出**Vague Prototype-Oriented Diffusion Model (VPDM)**，利用仅包含目标模糊信息的原型作为初始条件，从输入层排除异常信息，然后通过条件扩散模型逐步添加细节，彻底避免“相同捷径”问题。

## 2. 方法论：核心思想、关键技术细节
### 核心思想
- 使用**模糊原型**（vague prototypes）作为生成条件。原型仅包含基本形状、颜色等低级信息，不包含异常细节。
- 设计一种**新型条件扩散模型**，将模糊条件融入前向和反向过程，使得生成从模糊开始，逐步添加细节。
- 引入**Vague Prototype-Oriented Optimal Transport (VPOT)** 方法，通过最优传输（OT）学习原型，提供更精确的条件信息。

### 关键技术细节（公式与算法流程用文字说明）
1. **VPOT模型**：
   - 利用预训练EfficientNet提取特征 \( f \)。
   - 通过下采样器 \( T_{\text{down}} \) 对 \( f \) 进行低通滤波，获得模糊特征 \( f_{\text{down}} \)。
   - 初始化K个模糊原型 \( \beta \in \mathbb{R}^{K \times d} \)。
   - 将 \( f_{\text{down}} \) 的分布 \( P_f \) 与原型分布 \( P_\beta \) 之间的OT距离最小化，得到传输矩阵 \( T \)。
   - 用 \( T \) 加权原型得到模糊条件 \( y = T \times \beta \)，再经过上采样 \( T_{\text{up}} \) 得到 \( \hat{y} \)，用于引导扩散模型。
   - OT损失（含熵正则）作为优化目标的一部分。

2. **条件扩散模型**：
   - 前向过程终点：\( p(x_T | \hat{y}) = \mathcal{N}(\hat{y}, I) \)，从模糊条件开始。
   - 前向过程各步：\( q(x_t | x_{t-1}, \hat{y}) = \mathcal{N}(x_t \mid \sqrt{1-\beta_t}x_{t-1} + (1-\sqrt{1-\beta_t})\hat{y}, \beta_t I) \)。
   - 直接从 \( x_0 \) 采样：\( q(x_t | x_0, \hat{y}) = \mathcal{N}(x_t \mid \sqrt{\alpha_t}x_0 + (1-\sqrt{\alpha_t})\hat{y}, (1-\alpha_t)I) \)。
   - 后验分布 \( q(x_{t-1} | x_0, x_t, \hat{y}) \) 的均值由 \( x_0, x_t, \hat{y} \) 线性组合，方差为 \( \tilde{\beta}_t I \)（具体系数见论文式15）。
   - 模型训练优化ELBO + OT损失。

3. **统一优化**：
   - \( \mathcal{L} = \mathcal{L}_{\text{ELBO}} + \mathcal{L}_{\text{OT}} \)。
   - 训练过程中，预训练EfficientNet冻结，仅优化原型 \( \beta \) 和去噪网络 \( \epsilon_\theta \)。

4. **推理**：
   - 对测试样本提取 \( \hat{y} \)，从 \( \mathcal{N}(\hat{y}, I) \) 采样 \( x_T \)，然后按逆向过程逐步去噪得到重构样本 \( x_0^{\text{rec}} \)。
   - 异常定位图：\( S = \| x_0 - x_0^{\text{rec}} \|_2 \)（在特征空间计算后上采样）。
   - 异常检测分数：取 \( S \) 的平均池化最大值。

## 3. 实验设计
### 数据集与基准
- **MVTec-AD**：10个物体类、5个纹理类，共5354张图像（3629正常+1725测试，含正常与异常）。
- **VisA**：12个子集（复杂结构、多实例、单实例），共10821张图像（9621正常+1200异常）。
- **MPDD**：6类金属零件，888张正常训练，458张测试。

### 对比方法
- 基础方法：US、PSVDD、PaDiM、MKD、DRAEM、RD4AD、RevDistill、PatchCore、FastFlow。
- 统一模型：UniAD、HVQ-Trans。
- 扩散方法：DiAD。
- 评价指标：图像级和像素级AUROC。

### 实验设置
- 图像尺寸224×224，特征图尺寸32×32。
- EfficientNet-b4提取多尺度特征（272通道）。
- 原型数K=50，下采样倍数N=4。
- 扩散步数T=1000，线性噪声调度 \( \beta_1=10^{-4}, \beta_T=0.02 \)。
- Adam优化器，学习率0.001，批大小32。

## 4. 资源与算力
- 论文在Implementation Details中提到：所有实验在**NVIDIA RTX 3090 24GB GPU**上完成，使用PyTorch框架。
- **未明确说明**训练时长、GPU数量、总耗时等具体算力消耗信息。

## 5. 实验数量与充分性
- **主实验**：在3个数据集（MVTec-AD、VisA、MPDD）上进行异常检测和定位评估，共报告3张主表（表1、表2、表4）。
- **消融实验**：表3对MVTec-AD进行6组消融（去除模糊操作、去掉OT、去掉OT损失、替换DDPM、替换N(0,I)起点、去掉VPOT等），充分验证各模块贡献。
- **定性分析**：提供大量可视化结果（图2~9），包括重构结果、特征可视化、与SOTA对比等。
- **附录**：包含推导、更多定量结果（MPDD）、视觉消融（附录F）等。
- **充分性**：实验设计较为全面，覆盖多类、多数据集、多基线，消融实验充分，结果客观。但未进行超参数敏感性分析（如原型数K、下采样N等）。

## 6. 主要结论与发现
- VPDM在所有三个数据集上均达到**state-of-the-art**性能。
  - MVTec-AD：检测AUROC 98.4%，定位AUROC 97.8%。
  - VisA：检测94.2%，定位98.9%。
  - MPDD：检测96.9%，定位98.6%。
- 消融实验表明：
  - 模糊操作、原型、OT、OT损失、专用扩散模型均对性能有显著贡献。
  - 若用标准DDPM替代专用扩散模型，性能下降22.05%。
  - 若去掉VPOT，性能下降30.49%。
- VPDM从根本上缓解“相同捷径”问题，通过模糊条件防止异常信息渗透。

## 7. 优点
1. **新颖的思路**：从人类记忆检索机制出发，首次提出利用模糊原型避免异常信息泄露，而非在后期抑制异常。
2. **技术整合巧妙**：将低通滤波、最优传输、条件扩散模型有机融合，形成统一优化框架。
3. **出色的实验验证**：在三个挑战性数据集上全面对比，消融实验设计合理，可视化工具体现模型行为。
4. **代码开源**：有助于复现和后续研究。

## 8. 不足与局限
1. **实验场景局限**：仅在工业缺陷检测数据集（MVTec-AD、VisA、MPDD）上验证，未涉及医疗图像、视频监控等其他领域，泛化性未知。
2. **计算资源未明确**：未报告训练时间、推断速度、参数量等，难以评估实际部署成本。
3. **超参数敏感性未知**：未探讨原型数量K、下采样倍数N、扩散步数T等关键超参数的影响。
4. **模糊原型可能丢失正常细节**：低通滤波可能滤除对正常样本识别有用的纹理信息，导致生成质量在极端情况下受限。
5. **缺乏与实时性相关的讨论**：多步扩散过程推断较慢，文中未分析推理效率或加速策略。

（完）
