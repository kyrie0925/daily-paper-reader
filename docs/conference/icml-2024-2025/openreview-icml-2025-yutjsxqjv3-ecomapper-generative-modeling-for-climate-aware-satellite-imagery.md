---
title: "EcoMapper: Generative Modeling for Climate-Aware Satellite Imagery"
title_zh: EcoMapper：用于气候感知卫星影像的生成式建模
authors: "Muhammed Goktepe, Amir hossein Shamseddin, Erencan Uysal, Javier Muinelo Monteagudo, Lukas Drees, Aysim Toker, Senthold Asseng, Malte von Bloh"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=YUtJsxQjv3"
tags: ["query:ocean-obs"]
score: 5.0
evidence: 卫星影像生成用于环境监测，可应用于海洋生态系统
tldr: 该论文为解决卫星影像与气候数据集成难题，构建了包含290万张Sentinel-2影像的数据集，并采用Stable Diffusion 3和ControlNet技术生成气候感知的合成影像。虽未直接用于海洋监测，但其方法可应用于海洋生态遥感场景分析。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-yutjsxqjv3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1765, \"height\": 807, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yutjsxqjv3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 758, \"height\": 854, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yutjsxqjv3/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 831, \"height\": 1303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yutjsxqjv3/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 798, \"height\": 1024, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yutjsxqjv3/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 847, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yutjsxqjv3/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1466, \"height\": 848, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yutjsxqjv3/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1250, \"height\": 942, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yutjsxqjv3/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1240, \"height\": 945, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yutjsxqjv3/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1149, \"height\": 729, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yutjsxqjv3/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1725, \"height\": 1022, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-yutjsxqjv3/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yutjsxqjv3/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 855, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yutjsxqjv3/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 123, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yutjsxqjv3/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 858, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yutjsxqjv3/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 852, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yutjsxqjv3/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1425, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yutjsxqjv3/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1769, \"height\": 896, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yutjsxqjv3/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1766, \"height\": 907, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yutjsxqjv3/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1515, \"height\": 201, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yutjsxqjv3/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 640, \"height\": 245, \"label\": \"Table\"}]"
motivation: 现有卫星影像缺乏与气候数据的集成，限制了其在环境监测中的应用。
method: 利用Stable Diffusion 3进行文本到影像生成，并使用ControlNet实现多条件控制。
result: 生成了逼真的合成卫星影像，覆盖15种土地覆盖类型。
conclusion: 为气候感知的遥感影像生成提供了有效框架，可扩展至海洋监测。
---

## Abstract
Satellite imagery is essential for Earth observation, enabling applications like crop yield prediction, environmental monitoring, and climate
change assessment. However, integrating satellite imagery with climate data remains a challenge, limiting its utility for forecasting and scenario analysis. We introduce a novel dataset of 2.9 million Sentinel-2 images spanning 15 land cover types with corresponding climate records, forming the foundation for two satellite image generation approaches using fine-tuned Stable Diffusion 3 models. The first is a text-to-image generation model that uses textual prompts with climate and land cover details to produce realistic synthetic imagery for specific regions. The second leverages ControlNet for multi-conditional image generation, preserving spatial structures while mapping climate data or generating time-series to simulate landscape evolution. By combining synthetic image generation with climate and land cover data, our work advances generative modeling in remote sensing, offering realistic inputs for environmental forecasting and new possibilities for climate adaptation and geospatial analysis.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：卫星影像与气候数据难以有效集成，限制了其在环境预测、作物产量预估、气候变化评估等任务中的应用。现有遥感数据集多为任务特定或区域受限，且缺乏与未来气候情景关联的生成模型。
- **整体含义**：论文提出一种气候感知的卫星影像生成方法，通过大规模数据集和扩散模型，能够根据地理-气候条件合成逼真的遥感影像，为环境监测、农业、林业等领域提供可预测的未来视图，弥补观测缺失并增强下游模型。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：利用 Stable Diffusion 3 生成模型，将结构化文本提示（包含土地覆盖类型、位置、日期、温度、降水、太阳辐射）作为条件，生成与实际环境一致的高分辨率卫星影像。同时，引入 ControlNet 实现多条件控制，保留空间结构并模拟时序变化。
- **关键技术细节**：
  - **数据集 EcoMapper**：覆盖 104,424 个全球位置、15 种土地覆盖类型，包含 290 万张 Sentinel-2 RGB 影像（训练集：2017-2022 年，每月 1 张；测试集：2017-2024 年，每月 1 张）。附带 NASA POWER 气候数据（月均温度、降水、太阳辐射）。
  - **文本到图像生成**：结构化提示格式（例如“A satellite image of croplands in Northern Cape, South Africa, on October 2019...”）同时输入 CLIP 和 T5 文本编码器，条件化引导 SD3 生成。微调使用了 LoRA（18M 参数）或全参数（1.5B 参数）。
  - **多条件生成（ControlNet）**：将前一期卫星影像作为空间控制信号，结合气候文本提示生成时序影像。ControlNet 权重复制自 SD3-FT 的前 12 层，并全微调（1.1B 参数）。
  - **提示工程**：设计了空间提示（位置、日期、土地覆盖）和气候提示（温度、降水、太阳辐射）。训练时随机丢失部分元数据（如月份、国家）以减少过度依赖，增强泛化。

### 3. 实验设计：数据集、基准、对比方法
- **数据集**：EcoMapper 训练集 98,930 个位置（共约 240 万张图像），测试集 5,500 个独立位置（约 53 万张图像）。气候数据来自 NASA POWER。
- **基准**：对比了未经微调的 Stable Diffusion 3、DiffusionSat，以及微调后的 SD3-FT、DiffusionSat-FT、SD3-FT-HR（高分辨率 1024×1024）。
- **对比方法**：还包括基线 SD3 ControlNet 模型、气候敏感性分析中的极端条件、按土地覆盖类型及年份的鲁棒性测试。评估指标：FID、CLIP Score、SSIM、PSNR、LPIPS。

### 4. 资源与算力
- **算力说明**：文中未明确列出 GPU 型号、数量或具体训练时长。仅提及：SD3-FT-HR 全参数微调（1.5B 参数）耗时约为 SD3-FT（LoRA 18M 参数）的 5-6 倍；ControlNet 微调 1.1B 参数。未提供更详细的资源信息。

### 5. 实验数量与充分性
- **实验数量**：约 6 组主要定量实验（表 1-5），包括文本到图像对比、极端天气敏感性、多条件生成、按土地覆盖类型性能、按年份鲁棒性；另有附录中提示策略消融（表 9）、详细分类性能（表 7、8）以及 SatCLIP 相关性测试（表 10）。定性结果（图 3、4、5）展示了多种场景。
- **充分性**：实验设计较为全面，覆盖了不同方法、不同分辨率、不同气候条件和土地类型。测试集在空间和时间上独立，保证了泛化评估。但缺少与现有最先进遥感生成模型的直接数值对比（仅用两个基线），且未进行大规模用户研究来验证视觉真实性。

### 6. 论文的主要结论与发现
- 扩散模型能有效将气候变量映射到遥感影像外观，在温暖湿润条件下生成更多植被，在寒冷干燥条件下生成雪或裸露地面。
- 卫星专用预训练模型（DiffusionSat）在相同分辨率下优于通用 SD3，但高分辨率 SD3-FT-HR 最终获得最佳 FID（49.48）。
- 多条件生成（ControlNet）在空间保持和气候响应上优于纯文本生成，FID 为 48.20，LPIPS 最低（0.59）。
- 模型对土地覆盖类型敏感：频繁出现的类别（草地、稀树草原）表现好；稀有或视觉复杂类别（湿地、城区）FID 较差（>250）。
- 在时空间上均具有鲁棒性：2017-2024 年各年份性能稳定，2023-2024 年（训练未见）仍保持同等水平。

### 7. 优点
- **数据集规模大**：290 万张全球分布影像，附带气候数据，为气候条件生成提供坚实基础。
- **双模态生成框架**：同时支持文本到图像和多条件控制，应用范围广（填补云覆盖、生成未来情景、保持空间一致性）。
- **结构化提示设计**：融合 CLIP 和 T5 编码器，分离空间与气候信息，并引入随机丢失策略增强泛化。
- **敏感性分析充分**：系统评估了极端气候条件下的响应，揭示模型对分布外情景的局限性。
- **鲁棒性验证**：按土地覆盖和年份分别统计，证明模型在各类场景下的稳定性。

### 8. 不足与局限
- **类别不平衡问题**：稀有类别（如湿地、城区、针叶林）生成质量显著下降，FID 超过 260，部分类别 SSIM 极低（城区 0.06）。未采用重采样或类别加权策略。
- **极端气候条件不真实**：当提示的气候与位置典型气候严重偏离（如热带雨林下雪）时，模型响应微弱或无变化，表明学习了气候-位置相关性，生成可能不符合物理规律。
- **仅 RGB 图像**：未利用多光谱信息（如近红外），限制了植被指数等应用。未来需扩展至多光谱生成。
- **算力与可复现性**：未给出训练所需 GPU 具体配置，高分辨率模型训练时间较长，可能阻碍复现。
- **评估指标局限**：主要依赖 FID、SSIM 等图像质量指标，缺乏下游应用（如作物产量估计）的端到端验证。CLIP Score 偏低（0.32-0.40），提示文本-图像对齐仍有改进空间。

（完）
