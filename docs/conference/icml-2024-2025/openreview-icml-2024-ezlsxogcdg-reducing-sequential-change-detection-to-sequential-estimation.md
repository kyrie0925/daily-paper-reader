---
title: Reducing sequential change detection to sequential estimation
title_zh: 将序贯变化检测归约为序贯估计
authors: "Shubhanshu Shekhar, Aaditya Ramdas"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=EZLsxOgcDg"
tags: ["query:anomaly-id"]
score: 8.0
evidence: 时间序列异常检测的序贯变化检测方法
tldr: 传统变化检测方法对数据分布假设要求较高。本文提出将序贯变化检测归约为序贯估计问题，利用置信序列（CS）构建检测方案，在最小假设下保证低检测延迟和可控虚警率。理论证明了平均运行长度下界为1/α。该方法为时间序列异常检测提供了一种通用且理论保证的框架。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-ezlsxogcdg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 800, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ezlsxogcdg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1664, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ezlsxogcdg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1395, \"height\": 572, \"label\": \"Figure\"}]"
motivation: 现有变化检测方法对数据分布假设要求严格，缺乏通用方案。
method: 将变化检测归约为序贯估计，在每个时间步启动置信序列，当所有活跃序列交集为空时报警。
result: 理论证明平均运行长度至少为1/α，实现了低延迟可控虚警的变化检测。
conclusion: 提供了一个通用且理论保证的序贯变化检测框架。
---

## Abstract
We consider the problem of sequential change detection under minimal assumptions on the distribution generating the stream of observations. Formally, our goal is to design a scheme for detecting any changes in a parameter or functional $\theta$ of the data stream distribution that has small detection delay, but guarantees control on the frequency of false alarms in the absence of changes. We describe a simple reduction from sequential change detection to sequential estimation using confidence sequences (CSs): begin a new level-$(1-\alpha)$ CS at each time step, and proclaim a change as soon as the intersection of all active CSs becomes empty. We prove that the average run length of our scheme is at least $1/\alpha$, resulting in a change detection scheme with minimal structural assumptions (thus allowing for possibly dependent observations, and nonparametric distribution classes), but strong guarantees. We also describe an interesting parallel with Lorden's reduction from change detection to sequential testing and connections to the recent ''e-detector'' framework.

---

## 论文详细总结（自动生成）

### 论文中文总结

#### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：传统的序贯变化检测（Sequential Change Detection, SCD）方法通常对数据分布有较强假设，如独立同分布（i.i.d.）、参数化分布类已知等，限制了其在非参数、依赖数据等场景下的应用。同时，现有方法（如CuSum）需要精确已知的预变化和后变化分布，通用性不足。
- **核心问题**：在尽可能少的分布假设下，设计一种既能控制虚警率（平均运行长度ARL≥1/α），又能保持低检测延迟的变化检测方案。
- **整体含义**：论文提出一种简单的归约思路——将变化检测问题转化为序贯估计问题，利用置信序列（Confidence Sequence, CS）作为基本构建模块，从而将大量现有的CS构造方法（如胡-斯密斯投注CS、Hoeffding CS等）直接应用于变化检测，大大降低了应用门槛，并允许依赖观测和非参数分布类。

#### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：在每个时间步启动一个新的水平为(1-α)的置信序列（CS），随着数据累积，所有活跃CS的交集非空则继续监测，当交集变为空集时宣告发生变化。该方案称为RCS-Detector（Reducing Change Detection to Sequential Estimation）。
- **关键技术细节**：
  - **CS定义**：序列(C_n)满足概率覆盖保证：P(∀n: θ∈C_n) ≥ 1-α，且通常可假设嵌套。
  - **RCS-Detector算法流程**：
    1. 初始化C(0)_n = Θ（非分区问题）或Θ0（分区问题）。
    2. 对每个新数据点Xn：
        - 更新所有已有CS（C(m) for m<n）并初始化新的CS C(n)。
        - 若所有CS的交集∩_{m=0}^n C(m)_n = ∅，则停止并宣告变化；否则继续。
  - **平均运行长度（ARL）定理**：当无变化时，E∞[τ] ≥ 1/α。证明通过构造e-process和e-detector实现。
  - **检测延迟定理**：在满足宽度假设（确定性包络w(n,P,α)→0）下，检测延迟有界为O(u(θ0,θ1,T))，其中u为满足宽度和距离条件的最小样本数。
  - **与Lorden归约的关系**：通过CS与序贯检验的对偶性，证明RCS-Detector是Lorden归约的非参数推广。
- **公式**：全文无显式公式，但关键定理以文字描述，例如ARL下界E∞[τ] ≥ 1/α，检测延迟上界ET[(τ-T)+] ≤ (3/(1-α))·u。

#### 3. 实验设计：使用了哪些数据集/场景，benchmark，对比了哪些方法
- **数据集/场景**：人为模拟数据，使用Beta分布生成数据（支持[0,1]区间），设定不同均值变化幅度Δ。未使用真实数据集。
- **Benchmark**：与Shekhar & Ramdas (2023)提出的BCS-Detector进行对比。
- **对比方法**：主要对比RCS-Detector与BCS-Detector（两者均基于相同的Hoeffding CS）。另外在附录中简要比较了CuSum（已知分布）和依赖数据场景下RCS-Detector的表现。
- **实验设置**：
  - ARL测试：α ∈ {10^{-1},...,10^{-5}}，无变化情况，50次独立试验，停止时间上限50000。
  - 检测延迟测试：α=0.001，Δ ∈ {0.05,0.075,0.10,0.125,0.15,0.175}，50次独立试验，延迟上限24000。
  - 额外展示依赖数据场景（基于马尔可夫切换机制）下RCS-Detector的性能。

#### 4. 资源与算力
- **未明确说明**：论文未提及使用的GPU型号、数量、训练时长或任何算力资源。实验均为CPU模拟，计算开销与样本量呈二次增长（每个时间步需更新所有CS），但文中未量化具体资源消耗。

#### 5. 实验数量与充分性
- **实验数量**：主要包含两组模拟实验（ARL对比和检测延迟对比），每组实验针对不同α或Δ各进行50次独立重复，并绘制分布密度图。额外在附录中用依赖数据场景展示了一个例子。
- **充分性**：
  - **优点**：覆盖了关键性能指标（ARL和延迟），并提供了分布图展示波动。
  - **不足**：仅限于合成数据，未在真实数据集（如网络流量、金融时序、工业监控）上验证；缺乏与非参数变化检测方法（如e-detector、基于核的方法）的系统对比；仅对比了BCS-Detector一种基线，且两者基于相同CS，本质上反映的是归约方式差异而非CS质量差异；未进行消融实验（如不同CS构造方法、不同窗口大小）。

#### 6. 论文的主要结论与发现
- **理论结论**：
  - RCS-Detector在无任何分布假设时（允许依赖数据、非参数类）能保证ARL≥1/α，且检测延迟与BCS-Detector相当（甚至略优，ARL下界提高约2倍）。
  - 该方案统一了Lorden归约（分区问题）和非分区问题，是更一般化的框架。
  - 通过与e-detector的等价性，建立了与近期非参数变化检测研究的联系。
- **实验结论**：在合成数据上，RCS-Detector与BCS-Detector的ARL和延迟表现相当，但RCS-Detector适用于BCS-Detector无法处理的依赖数据场景。

#### 7. 优点：方法或实验设计上的亮点
- **方法论亮点**：
  - 极简归约，通用性强：只需CS构造方法，即可用于几乎所有变化检测问题（分区/非分区，参数/非参数，独立/依赖）。
  - 理论保证严谨：给出非渐近的ARL下界和延迟上界，且证明简洁。
  - 提升了ARL界：相比BCS-Detector的1/2α−3/2，提升至1/α，且无独立性假设。
- **实验设计亮点**：
  - 通过同一CS构造方法（Hoeffding CS）公平对比RCS与BCS，突出归约方式的影响。
  - 展示了依赖数据场景的可行性，弥补了BCS的不足。

#### 8. 不足与局限
- **实验覆盖不足**：缺乏真实数据集验证，可能无法反映实际复杂时序的模式（如季节、趋势、异常模式）。
- **偏差风险**：仅使用合成Beta分布数据，结果推广性有限；未与其他非参数方法（如基于e-process的检测、基于核的方法）全面比较。
- **计算开销**：在时间n需维护O(n)个CS并更新，计算成本为O(n²)，尽管可通过窗口裁剪缓解，但论文未详细评估计算效率。
- **应用限制**：要求CS是嵌套的且宽度趋于0，这限制了能使用的CS类型；对于非平稳后变化分布或非常小的变化幅度，延迟可能过大。
- **假设前提**：检测延迟定理假设后变化观测独立于前变化观测且平稳，实际中可能违背。

（完）
