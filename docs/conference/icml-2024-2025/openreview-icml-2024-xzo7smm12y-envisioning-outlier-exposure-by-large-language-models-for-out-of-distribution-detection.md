---
title: Envisioning Outlier Exposure by Large Language Models for Out-of-Distribution Detection
title_zh: 通过大型语言模型设想异常暴露用于分布外检测
authors: "Chentao Cao, Zhun Zhong, Zhanke Zhou, Yang Liu, Tongliang Liu, Bo Han"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=xZO7SmM12y"
tags: ["query:anomaly-id"]
score: 6.0
evidence: 利用大型语言模型进行异常值暴露的离群检测
tldr: 本文提出EOE方法，利用大型语言模型的专家知识和推理能力，在不访问真实异常数据的情况下；通过想象潜在异常暴露，增强CLIP模型的零样本分布外检测能力；实验表明该方法在开放场景下显著优于现有方法，为异常检测提供了新思路。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-xzo7smm12y/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xzo7smm12y/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1756, \"height\": 639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xzo7smm12y/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 838, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xzo7smm12y/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 839, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xzo7smm12y/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 841, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xzo7smm12y/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1778, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xzo7smm12y/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1781, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xzo7smm12y/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 870, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xzo7smm12y/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1263, \"height\": 701, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xzo7smm12y/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1689, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xzo7smm12y/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 622, \"height\": 286, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xzo7smm12y/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1709, \"height\": 706, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xzo7smm12y/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1718, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xzo7smm12y/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1717, \"height\": 692, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xzo7smm12y/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1663, \"height\": 1304, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1748, \"height\": 1102, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1615, \"height\": 453, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1382, \"height\": 337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1749, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1682, \"height\": 1743, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1642, \"height\": 1740, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1542, \"height\": 678, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1432, \"height\": 814, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1667, \"height\": 679, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 971, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1766, \"height\": 631, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1130, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1432, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1578, \"height\": 681, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1577, \"height\": 810, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1577, \"height\": 807, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1714, \"height\": 812, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1578, \"height\": 813, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1637, \"height\": 1079, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1595, \"height\": 1335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1599, \"height\": 547, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1335, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1327, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1509, \"height\": 339, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xzo7smm12y/table-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1774, \"height\": 301, \"label\": \"Table\"}]"
motivation: 现有零样本OOD检测依赖封闭集标签，限制了CLIP对开放标签空间的识别能力。
method: 利用LLM的推理能力，在不使用真实异常数据的情况下，生成潜在的异常暴露描述，引导CLIP学习更广泛的分布特征。
result: 在多个OOD基准上，EOE显著提升了零样本检测的准确率和鲁棒性。
conclusion: LLM辅助的异常暴露想象是一种有效的零样本OOD检测策略。
---

## Abstract
Detecting out-of-distribution (OOD) samples is essential when deploying machine learning models in open-world scenarios. Zero-shot OOD detection, requiring no training on in-distribution (ID) data, has been possible with the advent of vision-language models like CLIP. Existing methods build a text-based classifier with only closed-set labels. However, this largely restricts the inherent capability of CLIP to recognize samples from large and open label space. In this paper, we propose to tackle this constraint by leveraging the expert knowledge and reasoning capability of large language models (LLM) to Envision potential Outlier Exposure, termed EOE, without access to any actual OOD data. Owing to better adaptation to open-world scenarios, EOE can be generalized to different tasks, including far, near, and fine-grained OOD detection. Technically, we design (1) LLM prompts based on visual similarity to generate potential outlier class labels specialized for OOD detection, as well as (2) a new score function based on potential outlier penalty to distinguish hard OOD samples effectively. Empirically, EOE achieves state-of-the-art performance across different OOD tasks and can be effectively scaled to the ImageNet-1K dataset. The code is publicly available at: https://github.com/tmlr-group/EOE.

---

## 论文详细总结（自动生成）

# 论文《Envisioning Outlier Exposure by Large Language Models for Out-of-Distribution Detection》中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：在开放世界场景中，机器学习模型常遇到分布外（OOD）样本，而现有零样本 OOD 检测方法（如基于 CLIP 的 MCM）仅使用封闭集 ID 类标签构建文本分类器，无法充分利用 CLIP 对开放标签空间的识别能力，尤其在处理困难 OOD 样本时表现欠佳。
- **动机**：作者发现，若加入真实 OOD 类标签，CLIP 的 OOD 检测性能大幅提升，但实际中无法获取真实 OOD 标签。因此提出利用大型语言模型（LLM）的专家知识和推理能力，在不访问任何真实 OOD 数据的前提下，**想象（Envision）潜在的异常暴露（outlier exposure）**，以增强 OOD 检测。
- **含义**：该方法名为 EOE，旨在为 CLIP 提供更广泛的标签空间先验，使其在开放场景下更好地区分 ID 和 OOD 样本，适用于远、近、细粒度三种 OOD 检测任务。

## 2. 方法论
### 核心思想
- 利用 LLM 基于视觉相似性规则生成潜在的异常类标签，再结合新的评分函数，在零样本设置下提升 OOD 检测能力。

### 关键技术细节
1. **LLM 提示设计**：针对三种 OOD 任务设计不同的提示模板：
   - **远 OOD**：先让 LLM 总结 ID 类别的大类，再生成与这些大类视觉相似但无直接关联的异常类。
   - **近 OOD**：对每个 ID 类别，要求 LLM 提供 l 个视觉相似但属于不同领域的异常类。
   - **细粒度 OOD**：直接要求 LLM 提供同一大类下不同的子类（如不同鸟种）。
2. **新评分函数**：定义匹配分数 \( s_i(x) = \frac{I(x) \cdot T(t_i)}{\|I(x)\|\|T(t_i)\|} \)，然后计算：
   \[
   S_{EOE}(x) = \max_{i \in [1,K]} \frac{e^{s_i(x)}}{\sum_{j=1}^{K+L} e^{s_j(x)}} - \beta \cdot \max_{k \in (K,K+L]} \frac{e^{s_k(x)}}{\sum_{j=1}^{K+L} e^{s_j(x)}}
   \]
   其中 \(K\) 为 ID 类数量，\(L\) 为生成的异常类数量，\(\beta\) 为超参数（默认 0.25）。通过减去异常类中最高 softmax 值来惩罚与异常类相似的样本。
3. **检测流程**：将 ID 标签和 LLM 生成的异常标签拼接后输入 CLIP 文本编码器，计算图像特征与所有文本特征的相似度，再应用 \(S_{EOE}\) 得到 OOD 分数，阈值 λ 设为 ID 数据 95% 真阳性率下的值。

## 3. 实验设计
### 数据集与场景
- **远 OOD**：ID 数据集包括 CUB-200-2011、Stanford-Cars、Food-101、Oxford-IIIT Pet、ImageNet-1K；OOD 数据集为 iNaturalist、SUN、Places、Texture（来自 MOS 基准）。
- **近 OOD**：ID 和 OOD 分别为 ImageNet-10 和 ImageNet-20（互为正/反）。
- **细粒度 OOD**：从 CUB-200、Stanford-Cars、Food-101、Oxford-IIIT Pet 中各取一半类别作为 ID，另一半作为 OOD。

### 基准方法对比
- **零样本方法**：MCM、CLIPN（额外预训练）、后验方法 Energy、MaxLogit。（注：CLIPN 需额外数据集训练，EOE 无需）
- **微调方法**：MSP、Energy (FT)、MOS、Fort et al.（公平性上 EOE 仍是零样本，与 MCM 最直接可比）
- **消融实验**：评分函数、LLM 提示类型、不同 LLM（GPT-3.5、LLaMA2-7B、Claude 2）、异常类数量、β 值、不同视觉 backbone 等。

### 评估指标
- FPR95（越低越好）、AUROC（越高越好），额外报告 AUPR。

## 4. 资源与算力
- 论文未明确说明具体使用的 GPU 型号、数量及训练时长。仅提及实验运行在 **NVIDIA A100 80GB PCIe GPU** 和 **AMD EPYC 7H12 CPU** 上，使用 PyTorch 1.13。由于 EOE 无需训练（仅推理），算力需求主要集中在 CLIP 特征提取和 LLM 文本生成上，文中未量化 LLM 的调用成本。

## 5. 实验数量与充分性
- **实验数量**：覆盖 3 类任务（远/近/细粒度），每类任务多个 ID 数据集，共至少 5 个大尺度远 OOD 实验 + 近 OOD 2 组 + 细粒度 4 组；消融实验包括评分函数、提示策略、LLM 型号、异常类数量、β 值、backbone（ViT-B/16、ViT-L/14、RN50、RN101 等）、鲁棒性测试（ImageNet-Sketch、ImageNet-C）等，总计超过 30 组表格。
- **充分性与公平性**：对比方法包括当前最先进的零样本和微调方法，使用相同 CLIP backbone 保持公平；消融系统全面；但部分对比方法（如 CLIPN）需要额外训练集，而 EOE 不需，公平性有一定偏差（论文已用灰色标注）。总体实验充分，客观性良好。

## 6. 主要结论与发现
- EOE 在所有三种 OOD 任务上均超越现有零样本方法，尤其远 OOD 平均 FPR95 仅 **0.21%**，相比 MCM 提升 2.47%；ImageNet-1K 上 FPR95 从 42.77% 降至 30.09%。
- 近 OOD 平均 FPR95 从 11.20% 降至 **9.07%**；细粒度 OOD 从 68.72% 降至 **60.52%**。
- 使用 T-SNE 可视化表明，即使生成的异常类未命中真实 OOD 类，也能将视觉相似的 OOD 样本聚类到幻想类中，从而有效区分。
- EOE 对 LLM 型号、异常类数量、β 值稳健，且可扩展到 ImageNet-1K 等大规模数据集。

## 7. 优点
- **新颖视角**：首次提出利用 LLM 的专家知识“想象”潜在异常类，无需真实 OOD 数据，解决零样本 OOD 检测的核心限制。
- **简洁有效**：无需额外训练或微调，仅通过提示工程和简单评分函数即可大幅提升性能。
- **泛化性强**：适用于远、近、细粒度三种不同场景，并且兼容多种视觉语言模型（CLIP、GroupViT、AltCLIP、ALIGN）和 LLM（GPT-3.5、LLaMA2、Claude 2）。
- **可解释性**：T-SNE 可视化直观展示了异常类如何帮助聚类 OOD 样本，提供语义层面的解释。
- **开源**：代码公开，便于复现。

## 8. 不足与局限
- **对 LLM 知识的依赖**：若 ID 类别超出 LLM 知识范围（如极端专业类别），LLM 可能无法提供合适的异常候选。论文建议采用预处理查询或描述性引导，但未充分验证。
- **任务类型假设**：需要预知 OOD 检测任务类型（远/近/细粒度）以选择合适的提示。论文虽用“远”提示在所有任务上测试仍优于 MCM，但提示方案并非完全统一。
- **计算成本**：虽无训练开销，但每次推理需额外调用 LLM 生成异常类（虽可离线缓存），且需处理更多文本编码（K+L 个），增加了少量推理时间。
- **实验覆盖**：未在更多真实世界复杂场景（如自动驾驶、医疗影像）中验证；未讨论对开放集识别（OSR）之外的其他异常定义（如语义 vs. 非语义）的适应性。
- **风险偏差**：LLM 生成的异常类可能带有训练数据中的偏见，若 OOD 样本恰好与这些偏见相关，可能引入误报。

（完）
