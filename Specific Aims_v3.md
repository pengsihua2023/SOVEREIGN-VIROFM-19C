下面我直接给你两部分：

1. **压缩后的提交风格 Specific Aims page**
2. **Project Summary / Abstract draft**

都按我们已经确定的 19C + multi-agent + sovereign viral protein foundation model 这个主线来写。

---

# Specific Aims

**Project Title:**
**SOVEREIGN-VIROFM: A Multi-Agent, Composable Scientific Foundation Model System for Viral Protein Reasoning**

The DOE Genesis Mission Topic 19 calls for AI systems capable of **scientific reasoning**, not merely language generation. The FOA emphasizes that such systems should combine **powerful base LLMs** with specialized foundation models and external scientific tools to support hypothesis generation, data analysis, and iterative refinement in closed-loop discovery workflows. Focus Area **19C – Composable and Modular Foundation Models** specifically seeks **strong base LLMs designed for flexible integration with other specialized foundation models and/or tools to enable complex, cross-domain reasoning**. Phase I projects are expected to demonstrate a **clear, tangible research workflow** and provide **quantitative evidence of AI advantage** or a credible trajectory toward transformative scientific capability.  

Viral protein science provides a demanding and scientifically important testbed for this vision. Reasoning about viral emergence, host adaptation, and immune escape requires coordinated analysis across sequence, structure, evolution, statistical inference, and literature evidence. Existing AI approaches remain fragmented: general LLMs are weak mechanistic scientific reasoners, while specialized biological models are often isolated from one another and from the tool ecosystems needed for end-to-end scientific workflows.

**Our central hypothesis** is that a **sovereign, multi-agent, composable foundation model architecture**—built around a governed base scientific LLM, a **from-scratch viral protein foundation model**, and modular interfaces to structure, evolutionary, statistical, and evidence-retrieval tools—will outperform non-composable baselines in viral scientific reasoning while providing stronger provenance, uncertainty awareness, and auditability. This project is designed not as a narrow virus-only modeling effort, but as a reusable architecture for DOE-relevant scientific AI workflows that require integration across specialized models and tools.  

**Aim 1. Develop a governed base scientific LLM for multi-agent orchestration of viral science workflows.**
We will develop a base scientific reasoning model that serves as the orchestration layer for task decomposition, agent routing, tool invocation, evidence synthesis, and hypothesis construction. This model will coordinate, rather than replace, specialized agents and tools.   
**Expected outcome:** a prototype base scientific LLM capable of provenance-aware orchestration of multi-step viral analysis workflows.

**Aim 2. Train a prototype from-scratch viral protein foundation model as a specialized reasoning module.**
We will train a viral protein foundation model on curated viral protein sequence corpora to learn domain-specific representations of viral sequence grammar, functional constraint, evolutionary regularity, and mutation-context dependence. This model will operate as a specialized **Viral Protein Foundation Agent** within the larger system.   
**Expected outcome:** a trained prototype model producing domain-specialized embeddings and mutation-effect priors for downstream reasoning tasks such as antigenic escape and cross-species adaptation analysis.  

**Aim 3. Build a modular multi-agent framework connecting specialized agents and scientific tools.**
We will implement a multi-agent framework in which the base scientific LLM coordinates interoperable agents, including Viral Protein, Structure Reasoning, Evolutionary Dynamics, Quantitative Inference, and Evidence agents. Agents will access models and tools through standardized wrappers, shared metadata schemas, provenance logging, and uncertainty propagation mechanisms.  
**Expected outcome:** a working proof-of-concept environment in which heterogeneous scientific models and tools are flexibly composed into an auditable reasoning workflow, directly operationalizing the 19C objective of composable and modular foundation models.  

**Aim 4. Demonstrate and quantify AI advantage on closed-loop viral science workflows.**
We will evaluate the system on two representative workflows: **(i) antigenic escape assessment** and **(ii) cross-species adaptation analysis**. Performance will be compared with non-agentic baselines, single-model baselines, and manually assembled tool-chain workflows using metrics including predictive utility, reasoning coherence, uncertainty calibration, evidence traceability, and time-to-hypothesis.    
**Expected outcome:** quantitative proof-of-concept evidence that a sovereign, composable, multi-agent architecture improves reasoning quality, traceability, and workflow efficiency relative to less integrated alternatives, thereby establishing a strong basis for Phase II scaling.  

**Overall impact:** If successful, this project will deliver a prototype **sovereign multi-agent scientific foundation model system** that advances the 19C vision of strong base LLMs flexibly integrated with specialized models and tools for cross-domain scientific reasoning. Beyond viral biology, the resulting architecture will provide a reusable template for DOE-relevant scientific AI systems requiring auditable, modular, tool-enabled reasoning across heterogeneous computational components.

---

# Project Summary / Abstract

We propose to develop **SOVEREIGN-VIROFM**, a **sovereign, multi-agent, composable scientific foundation model system** for viral protein reasoning. The project addresses DOE Genesis Mission **Topic 19** and **Focus Area 19C – Composable and Modular Foundation Models**, which call for strong base LLMs that can flexibly integrate specialized foundation models and scientific tools to enable complex, cross-domain reasoning. The proposed system is motivated by a central gap in current scientific AI: general LLMs lack reliable mechanistic reasoning in biological science, while specialized biological models are often isolated from one another and from the broader tool ecosystems required for end-to-end discovery workflows.  

Our approach is to build a governed base scientific LLM that serves as the orchestration core of a multi-agent system and coordinates specialized reasoning modules, including a **from-scratch viral protein foundation model**, structure-analysis components, evolutionary-analysis components, quantitative inference tools, and evidence-retrieval modules. Together, these agents will support closed-loop scientific workflows in which heterogeneous evidence is integrated into auditable, uncertainty-aware, and testable biological conclusions. By “sovereign,” we mean that the data pipeline, model weights, training procedures, evaluation workflows, provenance records, and deployment pathway will be governed, reproducible, and suitable for trusted execution in U.S.-controlled scientific computing environments.  

Phase I will deliver a proof-of-concept system demonstrating two representative viral science workflows: **antigenic escape assessment** and **cross-species adaptation analysis**. We will quantitatively evaluate AI advantage relative to non-agentic baselines, single-model baselines, and manually assembled tool workflows using metrics spanning predictive performance, reasoning quality, uncertainty calibration, evidence traceability, and workflow efficiency. Consistent with the Genesis Mission Phase I structure, the project is designed to establish a clear, tangible research workflow and provide quantitative evidence that the proposed approach is on a credible trajectory toward transformative scientific capability.  

The broader outcome is not merely a virus-specific model, but a reusable scientific AI architecture for integrating governed base LLMs, domain-specialized foundation models, and external computational tools into trustworthy multi-agent systems for science. If successful, this project will advance ASCR priorities in AI, scientific computing, and modular scientific reasoning while providing a scalable template for future DOE-relevant discovery workflows beyond viral biology.

---

下一步最合适的是把它继续扩成 **Research Strategy / Technical Approach 的第一页**。
