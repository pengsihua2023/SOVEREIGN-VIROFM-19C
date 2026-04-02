下面给你一版可直接作为 **one-page concept draft** 的英文稿，已经把你想要的几个核心点都纳入了：

* 19C 的 **composable and modular foundation models**
* Topic 19 的 **scientific reasoning + tool use + closed-loop discovery**
* **multi-agent orchestration**
* **from-scratch viral protein foundation model**
* **sovereign / governed / auditable model stack**
* 面向 **Phase I 9-month proof-of-concept** 的写法

我先给你英文正文，后面再补一句中文说明你这版的写法逻辑。

---

# One-Page Concept

**Project Title**
**SOVEREIGN-VIROFM: A Multi-Agent, Composable Scientific Foundation Model System for Viral Protein Reasoning**

**Focus Area**
**Topic 19C – Composable and Modular Foundation Models (ASCR)**

## Project Concept

We propose to develop a **sovereign, composable, multi-agent scientific foundation model system** for viral protein science, centered on a **strong base scientific LLM** that coordinates specialized foundation models and external scientific tools to enable rigorous, cross-domain reasoning. The project addresses DOE Topic 19, which calls for a new class of AI systems capable of scientific reasoning beyond text generation, including hypothesis generation, tool use, experiment design, data analysis, and iterative refinement in a closed-loop discovery process. It directly aligns with Focus Area 19C, which emphasizes **strong base LLMs designed for flexible integration with specialized foundation models and tools to enable complex, cross-domain reasoning**. 

The scientific target domain is **viral protein evolution, host adaptation, and immune escape**, with initial emphasis on high-consequence RNA viruses such as influenza A/H5N1. Current AI approaches in this area are fragmented: general LLMs lack mechanistic scientific reasoning, while specialized biological models are often isolated, narrowly scoped, and difficult to integrate into larger workflows. We hypothesize that scientific performance can be substantially improved by combining a governed base reasoning model with a **from-scratch viral protein foundation model** and a modular ecosystem of structure, evolutionary, statistical, and literature-analysis tools under a multi-agent architecture. This design treats AI not as a passive summarizer, but as an active scientific partner capable of coordinating heterogeneous evidence streams into testable biological hypotheses. 

Our central innovation is a **multi-agent orchestration layer** that operationalizes composability. Rather than building a monolithic model, we will create an agent-native architecture in which the base scientific LLM routes tasks across specialized agents, including: (1) a **Viral Protein Foundation Agent** trained from scratch on curated viral protein sequence corpora; (2) a **Structure Reasoning Agent** that interfaces with structure prediction and mutation-effect tools; (3) an **Evolutionary Dynamics Agent** that evaluates phylogenetic plausibility and adaptive trajectories; (4) a **Quantitative Inference Agent** that performs statistical analysis, uncertainty estimation, and ranking; and (5) an **Evidence Agent** that retrieves and reconciles findings from scientific literature and domain knowledge resources. This directly supports the FOA vision of AI systems that integrate base LLMs, specialized foundation models, and external tools into a closed-loop scientific workflow. 

A defining feature of the proposed system is its **sovereign scientific model stack**. By “sovereign,” we mean that the data pipeline, model weights, training procedures, intermediate outputs, and deployment pathway will be governed, auditable, reproducible, and suitable for trusted execution in U.S.-controlled scientific computing environments. This is not only a governance and infrastructure advantage; it is a scientific one. Scientific AI systems must support provenance tracking, uncertainty-aware reasoning, and reproducible evaluation if they are to become reliable contributors to discovery. DOE’s emphasis on large-scale computing, scientific data ecosystems, and cross-domain scientific AI makes this an especially strong fit for ASCR-led work.

The proposed Phase I effort will deliver a **clear, tangible research workflow** with quantitative evaluation of **AI advantage**, consistent with the Genesis Mission phased-program structure. Specifically, we will build a proof-of-concept system that demonstrates how a base scientific LLM can coordinate a viral protein foundation model and scientific tools to perform multi-step reasoning on two representative viral science workflows: **antigenic escape assessment** and **cross-species adaptation analysis**. Evaluation will compare the multi-agent system against single-model and manually assembled baselines using metrics spanning predictive performance, reasoning quality, uncertainty calibration, evidence traceability, and workflow efficiency. We will also examine scaling behavior with additional data, compute, and tool integration, thereby addressing the FOA’s requirement for quantitative evidence that the approach is on a credible trajectory toward transformative scientific capability.

This project advances ASCR priorities by developing AI architectures for scientific reasoning, modular integration, tool use, and HPC-enabled model training, while using viral science as a demanding testbed for cross-domain discovery. The broader outcome is not merely a virus-specific model, but a **reusable scientific AI framework** for composing governed base models, domain foundation models, and external computational tools into auditable multi-agent systems for science. If successful, the project will establish a prototype for a new class of trustworthy, extensible scientific foundation model platforms that can later be adapted to other DOE-relevant domains requiring deep, multi-modal, cross-domain reasoning.

## Phase I Objectives

1. Develop a governed base scientific LLM capable of agentic task planning, tool routing, and evidence synthesis for biological reasoning workflows.
2. Train a prototype **from-scratch viral protein foundation model** as a specialized module for viral sequence-function-evolution representation.
3. Build a modular **multi-agent integration framework** connecting the base LLM with scientific agents and external tools through standardized interfaces, provenance logging, and uncertainty propagation.
4. Demonstrate the system on closed-loop viral science workflows and quantify AI advantage relative to non-agentic and non-composable baselines.

## Expected Deliverables

Phase I deliverables will include: a prototype sovereign multi-agent scientific AI system; a trained viral protein foundation model prototype; modular adapters for selected structure, evolutionary, and statistical tools; benchmark tasks and evaluation reports for antigenic escape and host-adaptation reasoning; and a Phase II scaling roadmap for larger model training, broader domain coverage, and deeper integration with DOE-relevant scientific computing infrastructure.

---

这版的特点是：

1. **主叙事不是“训练病毒模型”**，而是
   **multi-agent + composable foundation model system**。

2. 你的病毒蛋白模型被写成
   **specialized foundation model / agent**，这更符合 19C。

3. 明确呼应了 FOA 的几个关键词：

   * base LLM
   * specialized foundation models
   * external tools
   * closed-loop discovery
   * scientific reasoning
   * Phase I quantitative AI advantage

4. “主权”没有写成空口号，而是写成
   **governed, auditable, reproducible, trusted scientific model stack**。

如果你愿意，我下一步可以继续把这版直接扩展成 **Specific Aims page**。
