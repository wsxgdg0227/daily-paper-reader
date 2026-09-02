---
title: "PerturbTrace: Evaluating Feedback Use by AI Co-Scientist Agents in Perturbation Discovery"
title_zh: PerturbTrace：评估AI共同科学家Agent在扰动发现中的反馈使用
authors: "Yu, C., Liu, S., Qiao, G., Luo, M., Xiang, Y., Xu, Z."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.18.745260v1.full.pdf"
tags: ["query:gkg"]
score: 7.0
evidence: 通过反馈-状态-动作-结果追踪，评估迭代AI智能体是否真实使用历史反馈
tldr: "大语言模型智能体已能自主开展多轮扰动实验，但能否根据前一轮反馈调整后续决策仍缺乏检验。PerturbTrace提出反馈-状态、状态-动作、动作-结果三阶段评估，逐轮判断反馈是否进入推理、策略是否改变批次、批次是否提升命中。在17个任务上四个智能体均于至少15个胜过最强非智能体基线，但6任务对照显示真实反馈无一致优势；576次转换中仅43次（7.5%）形成完整反馈链。结论强调高最终召回并非有效反馈利用的信号，闭环智能体需同时衡量发现性能与决策是否被反馈改变。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有AI合作用户在闭环设计上表现优秀，但少有工作检验其是否真正使用历史反馈修正实验决策。
method: 提出PerturbTrace，按反馈→状态、状态→动作、动作→结果分解每次环节转换，并通过随机或错误反馈对照辨别因果效应。
result: "四个智能体在17任务至少15个上胜过最强非agent方法；但6任务对照中真实反馈无优势，576次转换仅43次（7.5%）完整利用反馈。"
conclusion: 高最终性能不等于有效反馈利用；需同时评估发现结果与反馈是否改变后续决策，以改进闭环科学智能体。
---

## 摘要
近期AI共同科学家的进展已将LLM代理引入闭环实验设计。然而，这些代理是否利用早期轮次的反馈来修改后续实验决策仍不清楚。我们通过PerturbTrace解决此问题，它通过反馈到状态、状态到行动、行动到结果三个阶段评估每轮之间的转换。这些阶段评估反馈是否反映在代理的理由和扰动选择策略中、所述策略是否指导下一批扰动，以及该批次是否比随机抽样下预期的命中更多。我们在17个筛选衍生的任务上评估了四种LLM代理，并将它们与随机选择、主动学习和LLM引导的贝叶斯优化基线进行比较。每个代理在至少15个任务上优于最强非代理方法，但在六个任务上的受控评估显示，真实反馈相对于随机或无反馈没有一致的优势。在真实或随机反馈下的576个转换中，仅43个（7.5%）完成了完整的反馈-状态-行动-结果序列，其中25个在随机反馈下。这些发现表明高最终召回率并不一定意味着有效的反馈使用。它们还强调，需要通过发现性能和反馈是否改变后续决策来评估闭环科学代理。

## Abstract
Recent advances in AI co-scientists have brought LLM agents into closed-loop experimental design. However, whether these agents use feedback from earlier rounds to revise subsequent experimental decisions remains unclear. We address this question with PerturbTrace, which evaluates each round-to-round transition through Feedback-to-State, State-to-Action, and Action-to-Outcome. These stages assess whether feedback is reflected in the agent's rationale and perturbation-selection strategy, whether the stated strategy guides the next perturbation batch, and whether that batch yields more hits than expected under random sampling. We evaluate four LLM agents on 17 screen-derived tasks and compare them with random selection, active learning, and LLM-guided Bayesian optimization baselines. Each agent outperforms the strongest non-agent method on at least 15 of the 17 tasks, yet controlled evaluations across six tasks show no consistent advantage from true feedback over random or no feedback. Among 576 transitions under true or random feedback, only 43 (7.5%) complete the full Feedback-State-Action-Outcome sequence, including 25 under random feedback. These findings show that high final recall does not necessarily indicate effective feedback use. They also highlight the need to evaluate closed-loop scientific agents by both their discovery performance and whether feedback changes their subsequent decisions.