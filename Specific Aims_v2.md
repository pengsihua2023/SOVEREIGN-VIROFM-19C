下面给你一版可直接继续打磨的 **Specific Aims page（英文最终草稿版）**。我已经按我们刚才确定的主线来写：

* 主叙事是 **19C: Composable and Modular Foundation Models**
* 技术组织方式是 **multi-agent**
* 核心专用模块是 **from-scratch viral protein foundation model**
* 总体目标是 **scientific reasoning**, 不是单纯做一个病毒分类模型
* 写法尽量贴合 DOE Genesis Mission 对 **Phase I proof-of-concept、AI advantage、clear workflow** 的要求。

---

# Specific Aims

**Project Title:**
**SOVEREIGN-VIROFM: A Multi-Agent, Composable Scientific Foundation Model System for Viral Protein Reasoning**

## Overview

The DOE Genesis Mission Topic 19 calls for a new generation of AI systems capable of **scientific reasoning**, rather than only natural-language generation. The FOA states that such systems should combine **powerful base LLMs** with other foundation models and external scientific tools, enabling hypothesis generation, data analysis, experiment design, and iterative refinement in a closed-loop discovery process. Within this topic, Focus Area **19C – Composable and Modular Foundation Models** specifically seeks **strong base LLMs designed for flexible integration with other specialized foundation models and/or tools to enable complex, cross-domain reasoning**. Phase I projects are expected to demonstrate a **clear, tangible research workflow** and provide **quantitative evidence of AI advantage** or a credible trajectory toward transformative scientific capability.

Viral protein science is an ideal stress test for this vision. Scientifically meaningful reasoning about viral emergence, host adaptation, and immune escape requires integrating heterogeneous evidence across sequence, structure, evolution, statistics, and prior knowledge. Existing AI approaches remain fragmented: general LLMs are not reliable mechanistic scientific reasoners, while specialized biological models are often isolated and difficult to integrate into broader discovery workflows. We therefore propose a **sovereign, multi-agent, composable scientific foundation model architecture** in which a governed base scientific LLM coordinates specialized model agents and scientific tools, including a **from-scratch viral protein foundation model**, to support trustworthy cross-domain reasoning in viral biology. This framing is well aligned with ASCR’s interest in AI, scientific computing, tool use, and computational systems for science.

## Central Hypothesis

**Our central hypothesis is that a sovereign, multi-agent, composable foundation model architecture—built around a strong base scientific LLM, a domain-specialized viral protein foundation model, and modular interfaces to structure, evolutionary, statistical, and literature-analysis tools—will outperform non-composable baselines in viral scientific reasoning while providing stronger provenance, uncertainty awareness, and auditability.** This project is designed not as a narrow virus-only modeling effort, but as a reusable architecture for DOE-relevant scientific AI workflows that require integration across specialized models and tools.

## Significance

This project addresses a core challenge identified in Topic 19: current LLMs still fall short on complex, multi-faceted scientific tasks that require rigorous, verifiable, and multi-modal reasoning. The FOA explicitly points to the need for AI systems that can move beyond summarizing existing knowledge and instead act as true partners in scientific discovery. By using viral protein reasoning as a demanding use case, the project tests this vision in a domain where mechanistic conclusions require coordinated analysis across multiple scientific representations and computational tools. 

The project is also significant because it advances a **governed scientific AI stack** rather than a black-box point solution. The Genesis Mission emphasizes broader integration of resulting AI models and workflows into national scientific AI capabilities, and the FOA notes that successful systems may be integrated into the American Science Cloud. A modular, auditable, agent-based system is therefore not only technically appropriate, but strategically aligned with the larger platform vision of the solicitation. 

## Innovation

The proposed work is innovative in four ways. First, it uses **multi-agent orchestration** as the operational mechanism for realizing 19C-style composability. Second, it introduces a **from-scratch viral protein foundation model** as a specialized scientific module, rather than treating viral biology as only a downstream fine-tuning problem on a generic protein model. Third, it emphasizes a **sovereign model stack** in which data pipelines, weights, evaluation, provenance, and deployment are governed, reproducible, and suitable for trusted execution in U.S.-controlled scientific computing environments. Fourth, it evaluates success not only through prediction metrics, but through **AI advantage** metrics including reasoning quality, uncertainty calibration, evidence traceability, and workflow efficiency, as encouraged by the FOA.

## Specific Aim 1

**Develop a governed base scientific LLM for multi-agent orchestration of viral science workflows.**

We will develop a base scientific reasoning model that serves as the orchestration layer for task decomposition, agent routing, tool invocation, evidence synthesis, and final hypothesis construction. This model will function not as a stand-alone chatbot, but as the coordinating engine of a scientific workflow that can break a complex viral biology question into structured subtasks and integrate their outputs into a coherent, auditable reasoning trace.

**Rationale:** Topic 19 explicitly emphasizes powerful base LLMs as core components of AI systems for scientific reasoning, enhanced through integration with other models and external scientific tools. Focus Area 19C further requires that these base LLMs be designed for flexible integration across specialized models and domains.

**Expected outcome:** A prototype base scientific LLM capable of planning and coordinating multi-step viral analysis workflows, while preserving provenance-aware intermediate reasoning and interoperable interfaces for specialized agents and tools. This aim provides the backbone of the full composable system. 

## Specific Aim 2

**Train a prototype from-scratch viral protein foundation model as a specialized reasoning module.**

We will train a prototype viral protein foundation model on curated viral protein sequence corpora to learn domain-specific representations of viral sequence grammar, functional constraint, evolutionary regularity, and mutation-context dependence. This model will operate as a specialized **Viral Protein Foundation Agent** within the larger multi-agent architecture.

**Rationale:** Focus Area 19C is centered on integration of strong base LLMs with specialized foundation models. A viral protein foundation model is justified because viral proteins occupy a biologically distinctive regime shaped by rapid evolution, host adaptation, immune selection, and sparse experimental characterization; these features may not be optimally represented by general-purpose protein models alone.

**Expected outcome:** A trained prototype viral protein model that generates domain-specialized embeddings and mutation-effect priors for downstream reasoning tasks such as antigenic escape assessment and cross-species adaptation analysis. This aim establishes the main specialized module that differentiates the proposed system from generic scientific LLM approaches.

## Specific Aim 3

**Build a modular multi-agent framework connecting specialized agents and scientific tools.**

We will implement a multi-agent framework in which the base scientific LLM coordinates interoperable agents, including a Viral Protein Foundation Agent, a Structure Reasoning Agent, an Evolutionary Dynamics Agent, a Quantitative Inference Agent, and an Evidence Agent. Each agent will access models or external scientific tools through standardized wrappers, shared metadata schemas, provenance logging, and uncertainty propagation mechanisms.

**Rationale:** The FOA highlights the importance of tool use, multimodal evidence integration, and cross-domain reasoning in next-generation scientific AI. A modular framework is essential because structure tools, phylogenetic workflows, statistical packages, and retrieval systems evolve independently and must remain replaceable without redesigning the full system.

**Expected outcome:** A working proof-of-concept multi-agent environment in which heterogeneous scientific models and tools can be flexibly composed into an auditable reasoning workflow. This aim directly operationalizes the “composable and modular foundation models” objective of Focus Area 19C. 

## Specific Aim 4

**Demonstrate and quantify AI advantage on closed-loop viral science workflows.**

We will evaluate the system on two representative workflows: **(i) antigenic escape assessment** and **(ii) cross-species adaptation analysis**. Performance will be compared with non-agentic baselines, single-model baselines, and manually assembled tool-chain workflows. Evaluation metrics will include predictive utility, reasoning coherence, uncertainty calibration, evidence traceability, and time-to-hypothesis.

**Rationale:** The Genesis Mission Phase I structure requires a clear workflow and quantitative analysis showing whether the proposed approach is on a credible path toward transformative scientific capability. The FOA explicitly states that Phase I should provide quantitative evidence of increased predictive power, scientific insight, improved workflows, scaling behavior, or other proposed measures demonstrating AI advantage.

**Expected outcome:** Quantitative proof-of-concept evidence that a sovereign, composable, multi-agent architecture provides measurable gains in reasoning quality, traceability, and workflow efficiency relative to less integrated alternatives. These results will define the technical basis and scaling roadmap for a future Phase II effort. 

## Overall Impact

If successful, this project will deliver a prototype **sovereign multi-agent scientific foundation model system** that advances the 19C vision of strong base LLMs flexibly integrated with specialized models and tools for cross-domain scientific reasoning. Beyond viral biology, the resulting architecture will provide a reusable template for DOE-relevant scientific AI systems that require auditable, modular, tool-enabled reasoning across heterogeneous computational components. By combining agentic orchestration, domain-specialized biological modeling, scientific tool use, and quantitative Phase I validation, the project aims to move AI from passive language support toward active, testable, and extensible scientific reasoning.

---

这版已经可以作为主稿继续改。
下一步最有价值的是把它再压成 **更像正式提交版的一页排版长度**，并顺手给你配一个 **Project Summary/Abstract**。
