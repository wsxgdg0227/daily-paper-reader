---
title: "Organizing experiences into cognitive maps makes goal-directed action selection flexible, efficient, and explainable"
title_zh: 将经验组织为认知地图，使目标导向的行为选择灵活、高效且可解释
authors: "Yang, Y., Maass, W."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.1101/2025.10.25.684594v3.full.pdf"
tags: ["query:gkg"]
score: 6.0
evidence: 将经验组织为认知地图的存储与提取机制，用于目标导向行动选择
tldr: 当前目标导向行动选择依赖深度网络或大模型，难以用于低功耗边缘设备。大脑仅需20瓦且权重低精度即可实现。实验数据提示可借鉴经验组织成认知图的方式。该方法采用浅层网络局部在线学习、二值突触权重，并提供基于相关经验的行为解释。在抽象状态空间的确定性或随机动作导航中，显著减少计算步数。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法依赖DNN/LLM，能耗高且缺乏可解释性，不适合边缘设备。
method: 受大脑启发，将经验组织成认知图，通过浅层网络二值权重进行局部在线学习，显式存储经历。
result: 实现灵活高效的行为选择，提供经验解释，且导航计算步数显著少于现有方法。
conclusion: 认知图组织经验是低功耗、可解释且计算高效的行动选择新方向。
---

## 摘要
目前大多数针对目标变化和偶然性变化的目标导向行为选择方法都依赖于深度神经网络或大语言模型，因此不太适合部署在能耗要求极低的边缘设备上。大脑表明，即使突触权重精度很低，仅需20瓦的功耗也能实现类似功能。此外，它还能根据先前的经验为我们的行为选择提供解释，这一能力在那些将先前经验压缩为参数值的学习方法中是缺失的。我们表明，神经科学和认知科学的实验数据提出了一种具体的替代方案，即将经验组织成认知地图。它仅需要浅层网络中具有二值突触权重的局部在线学习，并能根据相关的先前经验对所选行为进行解释。这种受大脑启发的方法在具有确定性或随机性动作的抽象状态空间中导航时，所需的计算步骤也大大减少。

## Abstract
Most current methods for goal-directed action selection in the face of changing goals and contingencies require DNNs or LLMs. Therefore they are less suited for implementation in edge devices, where low energy-consumption is imperative. The brain shows that similar functionality can be produced with just 20W, even with low precision of synaptic weights. In addition, it endows our action selection with explanations in terms of prior experience, a capability that is missing in those learning approaches where prior experiences are compressed into parameter values. We show that experimental data from neuroscience and cognitive science suggest a concrete alternative where experiences are organized into cognitive maps. It only requires local online learning in shallow networks with binary synaptic weights, and provides explanations for selected actions in terms of related prior experiences. This brain-inspired approach also requires substantially fewer computation steps for navigation in abstract state spaces with deterministic or stochastic actions.