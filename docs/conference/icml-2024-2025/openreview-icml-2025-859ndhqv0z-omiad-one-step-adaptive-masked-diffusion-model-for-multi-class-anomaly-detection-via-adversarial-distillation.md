---
title: "OmiAD: One-Step Adaptive Masked Diffusion Model for Multi-class Anomaly Detection via Adversarial Distillation"
title_zh: OmiAD：通过对抗蒸馏的一步自适应掩码扩散模型用于多类异常检测
authors: "Yaoxuan Feng, Wenchao Chen, Yuxin Li, Bo Chen, Yubiao Wang, Zixuan Zhao, Hongwei Liu, Mingyuan Zhou"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=859NdHQv0Z"
tags: ["query:anomaly-id"]
score: 7.0
evidence: 提出了一步掩码扩散模型用于多类异常检测
tldr: 针对扩散模型在工业异常检测中推理速度慢的问题，提出OmiAD一步掩码扩散模型。通过自适应掩码策略动态调整掩码模式，鼓励模型将异常重建为正常，并利用对抗分数蒸馏压缩多步模型为单步。在工业数据集上实现了实时推理且保持高检测精度。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-859ndhqv0z/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 887, \"height\": 980, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-859ndhqv0z/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1687, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-859ndhqv0z/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1692, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-859ndhqv0z/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1500, \"height\": 2198, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-859ndhqv0z/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1507, \"height\": 1886, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-859ndhqv0z/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1511, \"height\": 1539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-859ndhqv0z/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1504, \"height\": 2231, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-859ndhqv0z/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1506, \"height\": 2222, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-859ndhqv0z/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1502, \"height\": 2304, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-859ndhqv0z/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1505, \"height\": 1831, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-859ndhqv0z/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1509, \"height\": 1183, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-859ndhqv0z/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1504, \"height\": 2307, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-859ndhqv0z/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1504, \"height\": 2303, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-859ndhqv0z/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1512, \"height\": 1248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-859ndhqv0z/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1631, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-859ndhqv0z/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-859ndhqv0z/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1770, \"height\": 751, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-859ndhqv0z/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1770, \"height\": 598, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-859ndhqv0z/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1769, \"height\": 605, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-859ndhqv0z/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1771, \"height\": 492, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-859ndhqv0z/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1774, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-859ndhqv0z/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1774, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-859ndhqv0z/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1774, \"height\": 1318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-859ndhqv0z/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1776, \"height\": 1053, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-859ndhqv0z/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 903, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-859ndhqv0z/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1045, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-859ndhqv0z/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 675, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-859ndhqv0z/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1340, \"height\": 189, \"label\": \"Table\"}]"
motivation: 扩散模型迭代去噪导致推理速度慢，不适用于实时工业异常检测。
method: 提出OmiAD，包括自适应掩码扩散模型和对抗分数蒸馏，实现单步异常检测。
result: 在MVTec等数据集上，OmiAD在保持高精度的同时大幅提升推理速度。
conclusion: 一步扩散模型可满足工业异常检测的实时性要求。
---

## Abstract
Diffusion models have demonstrated outstanding performance in industrial anomaly detection. However, their iterative denoising nature results in slow inference speed, limiting their practicality for real-time industrial deployment. To address this challenge, we propose OmiAD, a one-step masked diffusion model for multi-class anomaly detection, derived from a well-designed multi-step  **A**daptive  **M**asked  **D**iffusion  **M**odel (AMDM) and compressed using  **A**dversarial  **S**core  **D**istillation (ASD). OmiAD first introduces AMDM, equipped with an adaptive masking strategy that dynamically adjusts masking patterns based on noise levels and encourages the model to reconstruct anomalies as normal counterparts by leveraging broader context, to reduce the pixel-level shortcut reliance. Then, ASD  is developed to compress the multi-step diffusion process into a single-step generator by score distillation and incorporating a shared-weight discriminator effectively reusing parameters while significantly improving both inference efficiency and detection performance. The effectiveness of OmiAD is validated on four diverse datasets, achieving state-of-the-art performance across seven metrics while delivering a remarkable inference speedup.

---

## 论文详细总结（自动生成）

好的，请看以下基于论文内容生成的详细中文总结。

### 论文核心问题与整体含义

1.  **研究动机与背景**：
    *   **问题**：工业异常检测中，扩散模型虽然性能优异，但其迭代去噪的本质导致推理速度极慢，严重阻碍了其在实时工业场景中的部署。此外，现有基于重建的方法普遍存在“身份捷径”（identical shortcut）问题，即模型过度依赖局部像素级特征，在重建时无意中保留了异常信息。
    *   **目标**：提出一种既能解决“身份捷径”问题，又能实现一步快速推理的扩散模型框架，用于多类无监督异常检测。

### 论文提出的方法论

1.  **核心思想**：
    *   通过**自适应掩码扩散模型 (AMDM)** 引导模型关注全局上下文，以缓解快捷学习问题；再通过**对抗分数蒸馏 (ASD)** 将多步扩散模型压缩为单步生成器，实现快速推理。

2.  **关键技术细节**：
    *   **自适应掩码扩散模型 (AMDM)**：在扩散过程的正向步骤中，对输入特征施加一个**动态调节的二进制掩码**。掩码概率 `p(t)` 随扩散时间步 `t` 的增加而增加（`p(t) = p_min + (p_max - p_min)·(t/T)^k`）。这迫使模型在噪声水平低时（掩码少）保留局部细节，在噪声水平高时（掩码多）依赖更广的上下文进行重建，从而切断对局部异常特征的依赖。
    *   **对抗分数蒸馏 (ASD)**：ASD 框架包含四个组件：**一步生成器 (gθ)**、**教师评分网络 (ϵϕ)**、**学生评分网络 (ϵψ)** 和**判别器 (D)**。教师网络（预训练的AMDM）生成知识，学生网络通过蒸馏学习其行为，同时复用学生网络的**编码器模块**作为共享权重的判别器，引入对抗损失（Diffusion GAN风格）来对齐生成样本与真实样本的噪声分布。蒸馏损失基于 Fisher 散度，并结合了 SiD 和 SiDA 的方法，最终优化目标为 `L_θ = γ(t)[(ϵψ-ϵϕ)·(ε-ϵϕ) - α||ϵψ-ϵϕ||²]` (公式27)，其中 ε 是真实噪声。
    *   **算法流程**：训练时交替优化学生网络 ψ 和生成器 θ。推理时，对输入图像提取特征，加噪后直接通过一步生成器重建，并通过比较重建与输入的差异生成异常得分图。

### 实验设计

1.  **数据集与场景**：
    *   四个主流工业异常检测数据集：
        *   **MVTec-AD**：15类物体与纹理，模拟真实生产场景。
        *   **VisA**：12类对象，大型数据集。
        *   **MPDD**：6类金属部件，检测制造缺陷。
        *   **Real-IAD**：30类，约15万张图像的大规模基准。

2.  **基准与对比方法**：
    *   对比了六种先进方法：**RD4AD**、**UniAD**、**SimpleNet**、**DeSTSeg**、**DiAD** 和 **HVQ-Trans**。其中 HVQ-Trans 为统一状态最优方法，DiAD 为扩散模型方法。

### 资源与算力

*   论文明确提到所有实验在 **NVIDIA RTX 4090 GPU**（24GB VRAM）上执行，并使用 PyTorch 2.1.0。训练细节包括使用 Adam 优化器，学习率 0.001，批大小 32。但**未明确报告具体的训练时长**。

### 实验数量与充分性

*   **实验丰富度**：进行了充分的实验。
    *   **主要结果**：在四个数据集上，对比七个指标（图像级 AU-ROC、AP、F1_max；像素级 AU-ROC、AP、F1_max、AU-PRO）均取得 State-of-the-Art。
    *   **推理速度比较**：与 Transformer、重建、扩散类方法对比，OmiAD 速度提升 7倍到200倍。
    *   **消融实验**：
        *   验证了固定屏蔽 vs 自适应屏蔽、不同蒸馏方法（ADD、Score Distillation、Adversarial Score Distillation）的影响。
        *   验证了初始扩散步数 `t_init` 的影响。
        *   验证了不同扩散模型架构（U-Net、DiT、U-ViT）的鲁棒性。
        *   验证了不同特征提取器（EfficientNet vs ResNet 变体）的鲁棒性。
    *   **可视化结果**：提供了大量重建与异常定位的定性比较图。
    *   **假阳性率分析**：额外计算了 FPR，展示其误报控制能力。
*   **充分性与公平性**：实验非常充分，覆盖了主要数据集、多种对比方法、速度和消融，客观地证明了方法的优越性。所有基线结果均引用自原文或复现，公平性较好。

### 论文的主要结论与发现

1.  **性能优异**：OmiAD 在四个数据集上，以较大优势超越了所有对比方法，尤其在 VisA、MPDD 和 Real-IAD 上，mAD 指标分别比 HVQ-Trans 高出 4.1%、9.7% 和 6.9%。
2.  **极快推理速度**：通过蒸馏实现一步推理，速度远超所有基线方法（比 Transformer 方法快 7-8倍，比扩散方法快数百倍），满足实时工业部署需求。
3.  **有效缓解快捷学习**：自适应掩码策略显著抑制了“身份捷径”问题，使模型能够更好利用全局上下文。
4.  **蒸馏增强性能**：对抗分数蒸馏不仅实现了压缩，其共享判别器还进一步提升了检测精度，甚至在某些指标上超越了蒸馏前的教师模型。

### 优点

1.  **方法创新性**：将自适应掩码策略、分数蒸馏和对抗训练巧妙结合，系统性地解决了扩散模型在异常检测中的两大核心痛点（效率与快捷学习）。
2.  **高效性**：提出的 ASD 框架不仅实现了极致的速度提升，还因共享判别器无需额外参数，保持了模型的轻量性。
3.  **鲁棒性与泛化性**：在多个不同规模、不同工业场景（物体、纹理、金属、复杂结构）的数据集上均取得最佳结果，并通过架构消融证明了方法的通用性。
4.  **实验完整性**：实验设计全面，包括速度、消融、FPR 分析，对方法的有效性进行了充分验证。

### 不足与局限

1.  **训练资源未量化**：论文未报告训练时长，虽然单步推理快，但训练效率（可能需要较长的蒸馏过程）未知。
2.  **教师模型依赖**：OmiAD 高度依赖高质量的预训练教师模型（AMDM），其最终性能受限于教师模型的质量。如果教师模型在某些类别或场景下性能不佳，蒸馏后可能无法完全弥补。
3.  **应用场景局限**：方法专门针对工业异常检测设计，假设只有正常样本可用。在更开放的异常检测场景（如图像异常检测、视频异常检测）或存在一类新类（Novelty Detection）的场景下，其通用性尚未在论文中验证。
4.  **理论分析深度**：虽然蒸馏过程借鉴了 SiD/SiDA 的理论，但对于自适应掩码策略为何有效（特别是对不同类别的微调）的理论分析可以进一步深入。

（完）
