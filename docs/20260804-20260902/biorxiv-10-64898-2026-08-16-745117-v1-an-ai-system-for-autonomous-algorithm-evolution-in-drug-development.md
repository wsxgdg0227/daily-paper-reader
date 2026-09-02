---
title: An AI System for Autonomous Algorithm Evolution in Drug Development
title_zh: 用于药物研发中算法自主演化的人工智能系统
authors: "Zhou, Z., Nan, Y., Mou, M., Qian, Y., Liu, Y., Zuo, Z., Yang, H., Xu, W., Li, B., Jiang, W., Ren, Y., Liao, Y., Wang, Y., Li, Y., Yang, Q., Xi, Z., Mi, T., Sun, H., Liu, P., Zhu, F."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.16.745117v1.full.pdf"
tags: ["query:gkg"]
score: 9.0
evidence: 多角色大语言模型系统实现无需人工干预的闭环自主算法进化
tldr: 药物开发算法高度依赖专家设计和任务特定优化，难以实现跨阶段协同累积。DrugEvolve构建多角色大语言模型系统，整合研究者、工程师和分析师角色，闭环迭代算法设计、实现、评估与改进。在覆盖靶点发现到临床试验的11项任务、120个基准测试集上性能显著增强，并稳健泛化至多种数据模态与预测/生成任务。该系统可作为药物开发算法基础设施，并为更广科学领域提供可迁移范式。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有药物开发算法需专家按任务反复优化，缺乏跨阶段自主进化机制，难以实现全流程协同提升。
method: 构建含研究员、工程师与分析师的DrugEvolve系统，通过闭环“设计-实现-评估-改进”循环驱动算法自主演化。
result: 在11项代表性任务及120个基准测试集上性能大幅提升，对序列、图、拓扑、文本等异构模态及预测/生成任务均表现稳健。
conclusion: DrugEvolve可充当药物开发算法基础设施，其多角色闭环进化范式亦适用于更广泛的科学领域。
---

## 摘要
人工智能（AI）正日益渗透到药物研发流程中。为了加速这一多阶段、多任务的过程，人们构建了大量算法，这些算法高度依赖于专家设计和劳动密集型的特定任务优化。鉴于AI驱动的药物研发加速被认为是跨多个阶段的累积性、通常是协同性的效应，因此需要对整个流程中的现有算法进行自主演化，以实现整体推进。在此，我们提出了DrugEvolve，一个用于药物研发中系统性和自主算法演化的多角色大语言模型系统。DrugEvolve通过整合研究员、工程师和分析师领域，实现了闭环演化过程，并利用科学知识和积累的演化经验，实现了算法的迭代设计、实现、评估和改进。在跨越靶点识别、药物发现、临床前研究和临床试验的十一个代表性任务中，DrugEvolve自主演化出相应的任务特定算法，并在120个基准测试集上实现了显著的性能提升。此外，它在异构数据模态（从生物序列和图到分子拓扑和文本语言）中显示出强大的泛化能力，并在预测和生成任务中都取得了收益。总的来说，这个AI系统不仅可以作为药物研发的算法基础设施，还可以作为更广泛科学领域的可迁移范式。

## Abstract
Artificial intelligence (AI) is increasingly permeating the drug development pipeline. Numerous algorithms for accelerating this multi-stage and multi-task process have been constructed, which depends heavily on expert design and labor-intensive task-specific optimization. Given that AI-driven acceleration of drug development is recognized as a cumulative, often synergistic, effect across multiple stages, the autonomous evolution of existing algorithms across the entire pipeline is demanded to achieve a holistic advancement. Here, we present DrugEvolve, a multi-role large language model system for systematic and autonomous algorithm evolution in drug development. DrugEvolve realizes a closed-loop evolution process by incorporating Researcher, Engineer, and Analyst domains, and enables an iterative design, implementation, evaluation, and refinement of algorithm by leveraging scientific knowledge and accumulated evolutionary experience. Across eleven representative tasks spanning target identification, drug discovery, preclinical study, and clinical trial, DrugEvolve autonomously evolved the corresponding task-specific algorithms and achieved substantial performance enhancement on 120 benchmark test sets. Moreover, it showed robust generalizabilities across heterogeneous data modalities (ranging from biological sequence and graph to molecular topology and textual language), and realized gains in both predictive and generative tasks. Collectively, this AI system can serve not only as an algorithmic infrastructure for drug development, but also as a transferable paradigm for broader scientific domains.

---

## 论文详细总结（自动生成）

# 论文详细总结：DrugEvolve——用于药物研发中算法自主演化的人工智能系统

## 一、论文的核心问题与整体含义（研究动机与背景）

- **研究背景**：人工智能在药物研发中的渗透日益深入，但现有用于加速这一多阶段、多任务流程的算法高度依赖专家手工设计，以及劳动密集、针对特定任务的反复优化。
- **核心痛点**：药物研发的AI驱动加速已被认可为一种跨阶段积累、通常具有协同效应的整体过程，而当前缺乏让算法在整个流程中实现**自主演化**的机制，导致难以形成跨阶段的累积性提升和全局层面的协同进步。
- **研究目标**：构建一个能够对药物研发全流程中的已有算法进行系统性、自主演化的AI系统——DrugEvolve，从而推动算法基础设施的整体进步，并将该范式拓展到更广泛的科学领域。

## 二、方法论：核心思想、关键技术与算法流程

- **总体方案**：DrugEvolve 是一个**多角色大语言模型系统**，通过角色分工模拟真实的算法研发团队协作模式，实现算法的闭环自主演化。
- **三个核心角色**：
  - **Researcher（研究者）**：依据科学知识提出算法设计思想与改进方向。
  - **Engineer（工程师）**：将设计转化为可执行代码，负责算法实现与迭代。
  - **Analyst（分析师）**：对算法效果进行系统评估，识别问题并提供反馈。
- **闭环演化流程**：系统整合上述三方角色，利用科学知识和累积的演化经验，对算法执行**"设计 → 实现 → 评估 → 改进"**的迭代循环，无需人工干预即可持续生成性能更优的任务特定算法。
- **方法特点**：
  - 不针对单个任务做一次性优化，而是强调迭代式的持续演化。
  - 依赖"演化经验"的积累，使后续迭代能从前一轮失败/成功中学习，实现了跨轮次的知识复用。

## 三、实验设计

- **任务覆盖范围**：涵盖药物研发全流程的 4 个核心阶段、共 **11 个代表性任务**：
  - 靶点识别
  - 药物发现
  - 临床前研究
  - 临床试验
- **基准测试规模**：在 **120 个基准测试集** 上评估真实效果。
- **数据模态多样性**：覆盖 **异构数据模态**：
  - 生物序列
  - 图结构
  - 分子拓扑
  - 文本语言
- **任务类型多样性**：（说明涵盖两类基本机器学习任务）
  - **预测任务**
  - **生成任务**
- **对比方法说明**：由于当前仅为摘要级信息，**没有列出具体对比算法的名称**，也未说明对比基线（如人工设计最优算法、传统机器学习模型、其他LLM系统等）的具体设置；仅能确认为不同模态、不同任务下相对既有任务特定算法的性能增益。

## 四、资源与算力

- 原论文摘要与元数据中**未明确说明**所用的算力资源（如 GPU 型号与数量、训练/推理时长、系统调用成本等）。
- 也没有披露该闭环演化的总运行时间、每次迭代的平均开销或大语言模型的规模与版本信息。
- **建议**：如需了解计算资源约束与效率，需查阅论文正文的实验环境与实现细节部分。

## 五、实验数量与充分性

- **实验规模较大**：11 项任务 × 120 个基准测试集，覆盖多阶段、多模态、多任务类型，相比一般单任务或单模态的方法论文，覆盖面更广。
- **泛化性验证充分**：同时考察了异构数据模态（序列、图、拓扑结构、自然语言）和两种基本任务范式（预测与生成），能较好地展示系统的通用性。
- **尚可补充的分析方向**（基于现有摘要无法判断充分性）：
  - 缺少**消融实验**的描述（例如：仅用单个角色或多个角色组合时的性能差异、闭环迭代轮数的敏感性分析等）。
  - 缺少对**人工设计算法与自主演化算法在同等算力/时间条件下的成本-收益分析**。
  - 未明确说明各基准集是否分别使用相同的演化预算，以及是否存在数据泄漏或评估偏向的风险。

## 六、论文的主要结论与发现

1. **自主演化有效性**：DrugEvolve 能够在完全自主的闭环过程中，针对每项特定任务演化出相应的算法，并在 120 个基准测试集上获得**显著的性能提升**。
2. **跨任务与跨阶段能力**：系统并非适用于单一环节，而是贯通靶点识别、药物发现、临床前研究和临床试验的全链条。
3. **多模态与多任务泛化**：在生物序列、图、分子拓扑、文本语言等多种模态下，以及预测和生成两类任务中均取得了增益，证明方法具备**稳健的通用性**。
4. **定位与意义**：DrugEvolve 不仅可作为药物研发的**算法基础设施**，其"多角色大语言模型 + 闭环自主演化"的设计范式也为**更广泛的科学领域**提供了可迁移的AI驱动研发模板。

## 七、优点

- **范式创新**：将大语言模型从"单次任务求解器"升级为"持续自主演化的科研协作系统"，本质上是把算法研发过程本身作为自动化对象，与传统的 AutoML/神经网络搜索相比，具备更强的科学知识理解和代码生成能力。
- **闭环迭代机制**：引入积累的演化经验作为后续迭代的知识基础，使设计-实现-评估-改进形成正向循环，实现开放式的持续优化。
- **多角色架构的设计合理**：借鉴真实团队分工（研究者—工程师—分析者），在方法上更接近"AI 科学家"式科研自动化的理念，比单一智能体更有利于职责解耦与结果质量控制。
- **评价指标体系较完整**：以多阶段、多任务、多模态、多种任务类型的大规模基准来检验效果，结论的外推可信度相对较高。
- **潜在应用价值大**：如果真实有效，可以在无人值守的条件下持续改进药物研发算法，大幅降低专家人力成本与开发周期。

## 八、不足与局限（结合现有信息的客观评估）

- **信息透明性局限**：以当前可获得的摘要和元数据看，实验部分缺少对**基准数据集的来源及标准化程度**、**任务评价指标的具体定义**、以及对照基线（如"专家设计的最优算法"）如何选择的细节说明。
- **计算成本与可行性**：未报告实际耗费的资源（GPU 数量、时间、Token 消耗量），而大语言模型驱动的多轮"设计-实现-评估"闭环通常意味着较高的计算成本和API调用开销，真实场景中的性价比有待验证。
- **自动评估的可靠性风险**：闭环中的"分析师"角色本质上仍由大语言模型承担，其算法评估的**严谨性、可复现性和统计合理性**可能缺乏第三方独立验证；在缺少真实人工复核基准的情况下，存在对性能增益过度乐观的风险。
- **复杂任务适应性**：实验涉及的11个任务虽多，但缺乏对每项任务难度的细节描述（如模型复杂度增益 vs. 已有基线的胜率）；在真实极端复杂的药物研发场景（例如活体实验设计、临床终点预测中的混杂控制）下的表现仍需在后续工作中给出更深入的证据。
- **存在的偏差风险**：120个基准数据集若皆为公共已知数据，大语言模型的预训练知识可能泄漏到实验环节，造成性能高估；论文摘要未提及如何隔离和评估此类泄漏影响。
- **可解释性与安全性**：自主演化生成的算法可能存在"黑箱"问题，且药物研发是高监管、高失败成本场景，对于算法可解释性、安全性（如毒副作用预测错误）以及责任归因等问题，摘要中完全没有涉及。

---

（完）
