---
title: "Ex-VAD: Explainable Fine-grained Video Anomaly Detection Based on Visual-Language Models"
title_zh: Ex-VAD：基于视觉语言模型的可解释细粒度视频异常检测
authors: "Chao Huang, Yushu Shi, Jie Wen, Wei Wang, Yong Xu, Xiaochun Cao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=xAhUoyb5eU"
tags: ["query:anomaly-id"]
score: 7.0
evidence: 基于视觉语言模型的可解释细粒度视频异常检测
tldr: 视频异常检测通常只做粗略分类，缺乏细粒度解释。本文提出Ex-VAD，利用视觉语言模型提取帧级描述，再通过大语言模型生成视频级异常解释，同时实现细粒度分类和解释。实验表明，该方法在多个基准上取得了更好的可解释性和检测性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-xahuoyb5eu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 885, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xahuoyb5eu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1738, \"height\": 1080, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xahuoyb5eu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 860, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xahuoyb5eu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 855, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xahuoyb5eu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1766, \"height\": 1696, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-xahuoyb5eu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 822, \"height\": 518, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xahuoyb5eu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 851, \"height\": 514, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xahuoyb5eu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1767, \"height\": 659, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xahuoyb5eu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 853, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xahuoyb5eu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 862, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xahuoyb5eu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 867, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xahuoyb5eu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 872, \"height\": 316, \"label\": \"Table\"}]"
motivation: 现有视频异常检测缺乏细粒度分类和可解释性。
method: 结合VLM帧级描述和LLM视频级解释实现可解释异常检测。
result: 在多个数据集上提高了可解释性且检测性能更优。
conclusion: Ex-VAD推动了可解释视频异常检测的发展。
---

## Abstract
With advancements in visual language models (VLMs) and large language models (LLMs), video anomaly detection (VAD) has progressed beyond binary classification to fine-grained categorization and multidimensional analysis. However, existing methods focus mainly on coarse-grained detection, lacking anomaly explanations. To address these challenges, we propose Ex-VAD, an Explainable Fine-grained Video Anomaly Detection approach that combines fine-grained classification with detailed explanations of anomalies. First, we use a VLM to extract frame-level captions, and an LLM converts them to video-level explanations, enhancing the model's explainability. Second, integrating textual explanations of anomalies with visual information greatly enhances the model's anomaly detection capability. Finally, we apply label-enhanced alignment to optimize feature fusion, enabling precise fine-grained detection. Extensive experimental results on the UCF-Crime and XD-Violence datasets demonstrate that Ex-VAD significantly outperforms existing State-of-The-Art methods.

---

## 论文详细总结（自动生成）

# 论文《Ex-VAD: Explainable Fine-grained Video Anomaly Detection Based on Visual-Language Models》详细总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：传统视频异常检测（VAD）主要进行粗粒度二分类或多分类，只能判断视频是否异常，无法提供异常的具体类型和原因，缺乏可解释性。在实际应用（如安防监控、医疗监测）中，决策者需要知道“发生了什么”以及“为什么发生”，而现有方法难以满足。
- **背景**：视觉语言模型（VLM）和大语言模型（LLM）的发展为细粒度分类和可解释检测提供了新可能。部分工作利用VLM/LLM实现无训练检测或可解释检测，但或依赖纯文本而忽视视觉信息，或需要复杂微调。本文旨在同时实现**细粒度异常分类**和**异常解释**，提升检测准确性和可理解性。

## 2. 方法论
### 核心思想
- 提出 **Ex-VAD**，一个结合VLM和LLM的可解释细粒度视频异常检测框架。通过三个模块协同工作：异常解释生成模块（AEGM）提供文本解释；多模态异常检测模块（MADM）融合视觉与文本特征进行粗粒度检测；标签增强对齐模块（LAAM）实现细粒度分类。

### 关键技术细节
1. **AEGM（Anomaly Explanation Generation Module）**
   - **字幕提取与清洗**：从视频中均匀采样N帧，使用VLM（BLIP-2）生成帧级描述，再通过图像-文本对齐（余弦相似度）选择最相关的描述，去除噪声。
   - **基于LLM的解释生成**：将清洗后的帧级描述输入LLM（LLaMA-3），通过提示词生成视频级异常解释（包含是否异常及原因）。
2. **MADM（Multimodal Anomaly Detection Module）**
   - 视觉特征：使用CLIP图像编码器提取帧特征，再通过LGT-Adapter（局部全局时序适配器）建模时序依赖。
   - 文本特征：将AEGM生成的异常解释文本通过CLIP文本编码器提取特征。
   - 融合与分类：视觉特征与文本特征相加，送入包含FFN、FC和Sigmoid的二分类器，得到异常分数。
3. **LAAM（Label Augment and Alignment Module）**
   - **标签增强集构建**：利用LLM（GPT-4）对每个异常类别生成m个描述性句子，通过余弦相似度选择与原始标签最相似的top-k个句子，与原始标签嵌入融合，形成增强标签嵌入。
   - **细粒度分类**：计算多模态融合特征与所有增强标签嵌入的相似度，通过MIL-Align机制（选取top-k相似度取平均）得到类别预测，使用交叉熵损失对齐。
4. **损失函数**：总损失L = L_BCE（二分类）+ L_MCE（多分类交叉熵）+ λ·L_CTS（对比损失，拉远正常与异常类嵌入）。

## 3. 实验设计
### 数据集与场景
- **UCF-Crime**：1,900个未修剪视频（128小时），13类异常，训练/测试 = 1610/290，视频级标注用于训练，帧级标注用于测试。
- **XD-Violence**：4,754个未修剪视频（217小时），6类暴力行为，训练/测试 = 3954/800，视频级标注。

### 评估指标
- **粗粒度检测**：UCF-Crime使用**帧级AUC**，XD-Violence使用**帧级AP**。
- **细粒度检测**：**mAP@IoU**（阈值0.1~0.5，步长0.1），并报告平均mAP（AVG）。

### 对比方法
- **细粒度方法**：RealAD、RTFM、AVVD、DMU、CLIP-TSA、UMIL、VADCLIP、STPrompt等。
- **粗粒度方法**（含可解释或无训练）：LAVAD、VERA、VADOr，以及上述细粒度方法。
- 所有方法均使用CLIP ViT-B/16作为特征提取器（公平比较）。

## 4. 资源与算力
- 文中明确说明：**所有实验使用单张NVIDIA RTX A100 GPU**，基于PyTorch实现。
- **未说明**具体训练时长（如epoch数、总时间），但给出了推理时间（15.37ms/帧）和可训练参数量（9.97M）等效率数据。

## 5. 实验数量与充分性
### 实验组数
- **主要结果**：细粒度（表1、2）和粗粒度（表3）分别在两个数据集上报告。
- **消融实验**：
  - 模块消融（表4）：去除AEGM/LAAM对粗粒度AUC的影响。
  - AEGM内部对比（表5）：帧级Caption vs 视频级Explainable Text对细粒度mAP的影响。
  - LAAM内部对比（表6）：不同提示方式（[CLS]、a video of [CLS]、Learnable-Prompt、Label-Augment Prompt）的对比。
  - Top-k参数敏感性（图4）：k=1~10对粗粒度和细粒度结果的影响。
- **计算效率对比**（表7）：与RTFM、DMU、CLIP-TSA、VADCLIP比较可训练参数量、推理时间、MACs。
- **定性可视化**（图5）：展示异常分数曲线、真实异常区间、细粒度类别和解释。

### 充分性与公平性
- 实验覆盖**两个大规模公开数据集**，涵盖多种异常类型。
- 对比方法均为近年SOTA或代表性方法，且统一使用相同视觉骨干（CLIP ViT-B/16），确保公平。
- 消融实验设计合理，逐一验证关键组件贡献。
- 但**缺乏跨数据集泛化实验**（如在UCF上训练、XD上测试）和**更细粒度的异常定位（如像素级）评估**。

## 6. 主要结论与发现
- Ex-VAD在细粒度检测上显著优于所有对比方法：UCF-Crime上AVG mAP达10.15%（次优VADCLIP为8.83%），XD-Violence上AVG达28.23%（次优VADCLIP为24.70%）。
- 粗粒度检测上，Ex-VAD在UCF-Crime上AUC为88.29%（略低于TCVADS的88.58%），在XD-Violence上AP为86.52%（最高），同时支持细粒度分类和可解释性，是唯一同时具备这两项能力的模型。
- 消融实验证明：AEGM生成的高质量异常解释文本能有效提升检测性能（原始Caption反而有害）；LAAM的标签增强对齐显著优于固定提示和可学习提示。
- 模型在计算效率上平衡良好：仅9.97M可训练参数，推理速度15.37ms/帧，MACs仅12.04G，优于VADCLIP等。

## 7. 优点
- **兼具细粒度分类与可解释性**：首次在弱监督VAD中同时输出异常类别和自然语言解释，实用价值高。
- **模块化设计**：AEGM、MADM、LAAM各司其职，易于替换组件（如换用不同VLM/LLM）。
- **创新的标签增强对齐**：利用LLM生成丰富语义短语，克服了原始标签单一、语义匮乏的问题，有效提升细粒度分类。
- **轻量高效**：相比VADCLIP（35.17M参数），Ex-VAD仅9.97M可训练参数，推理更快，MACs更低。
- **实验全面**：在多个指标、多个数据集上验证，消融充分，代码将开源（推测）。

## 8. 不足与局限
- **粗粒度精度非最优**：在UCF-Crime上粗粒度AUC（88.29%）略低于TCVADS（88.58%），未给出解释，可能存在对生成文本质量的依赖。
- **依赖大型预训练模型**：需要VLM（BLIP-2）和LLM（LLaMA-3、GPT-4）进行离线或在线生成，增加了推理资源和延迟，实际部署可能受限。
- **弱监督假设**：仅适用于视频级标签的弱监督场景，未探索全监督或无监督设置。
- **未评估跨域泛化**：仅在两个数据集上评测，未测试模型在完全不同场景（如自动驾驶、工业质检）下的表现。
- **解释质量未定量评估**：虽然提供了解释示例，但未用自动指标（如BLEU、ROUGE）或人工评估解释的准确性和有用性。
- **细粒度定位精度有限**：mAP@IoU在较高IoU（如0.5）时仍较低（UCF-Crime 4.65%，XD-Violence 18.35%），说明时序定位精度有待提升。

（完）
