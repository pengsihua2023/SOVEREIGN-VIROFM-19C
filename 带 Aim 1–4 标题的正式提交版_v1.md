下面给你一版 **带 Aim 1–4 标题的正式提交版 5-page DOE narrative 风格文本**。我把刚才的连续版重组为更像正式 submission 的结构：

* 先有 **Overview / Vision / Central Hypothesis**
* 然后是 **Aim 1–4**
* 最后用 **Milestones, Go/No-Go, and Expected Phase I Outcome** 收尾

这样更符合 DOE narrative 的阅读习惯，也更容易让 reviewer 一眼看到你的 Phase I 逻辑链：
**base LLM → specialized viral FM → multi-agent integration → quantitative AI advantage**。
同时，这版仍然严格贴合 Topic 19 / 19C 的原始要求：Topic 19强调 scientific reasoning、base LLM、tool use、agents 和 closed-loop discovery；19C强调 strong base LLMs 与 specialized foundation models/tools 的灵活集成；Phase I要求 clear workflow 和 quantitative evidence of AI advantage trajectory。 

---

# Research Strategy / Technical Approach

## Overview and Project Vision

The DOE Genesis Mission identifies **AI for Scientific Reasoning** as a critical need for next-generation discovery workflows. Topic 19 states that, despite major advances in large language models (LLMs), current systems remain limited on scientific tasks requiring deep analytical reasoning, hypothesis generation from complex datasets, experiment design, and rigorous multimodal inference. The FOA therefore calls for AI systems architected specifically for scientific reasoning, built around **powerful base LLMs**, enhanced by integration with other foundation models and external scientific tools, and capable of functioning as sophisticated agents in a **closed-loop discovery engine**. Within this topic, Focus Area **19C – Composable and Modular Foundation Models** specifically seeks **strong base LLMs designed for flexible integration with other specialized foundation models and/or tools to enable complex, cross-domain reasoning**. Phase I projects are expected to demonstrate a **clear, tangible research workflow** and provide **quantitative analysis** showing whether the proposed approach is on a trajectory toward transformative scientific capability.  

We propose **SOVEREIGN-VIROFM**, a **sovereign, multi-agent, composable scientific foundation model system** for viral protein reasoning. The project is motivated by a central gap in current scientific AI. General LLMs can summarize biology fluently, but they do not reliably perform mechanistic, tool-grounded scientific reasoning. Specialized biological models may perform well on narrow tasks, but they are typically isolated from one another and difficult to integrate into broader workflows for hypothesis formation, evidence reconciliation, and uncertainty-aware decision support. Viral protein science provides an especially strong testbed for addressing this problem because scientifically meaningful reasoning about viral emergence, host adaptation, and immune escape requires coordinated analysis across sequence, structure, evolutionary history, quantitative ranking, and prior mechanistic evidence from literature and curated resources. This project therefore uses viral biology not simply as an application domain, but as a demanding scientific environment in which to test the 19C hypothesis that **composable and modular foundation model systems can create new forms of cross-domain AI advantage for science**.  

A defining feature of the proposed project is its **sovereign scientific model stack**. In this proposal, “sovereign” refers to a governed end-to-end computational pipeline in which training data, model weights, workflow traces, evaluation artifacts, and deployment pathways are auditable, reproducible, and suitable for trusted execution in U.S.-controlled scientific computing environments. This is scientifically important because a reasoning system can only become a reliable participant in discovery if its evidence sources, intermediate outputs, and uncertainty characteristics can be inspected and reproduced. It is also aligned with the broader Genesis Mission philosophy that successful AI models and workflows should be reusable, discoverable, and suitable for integration into larger shared scientific AI ecosystems. 

**Central Hypothesis.** Our central hypothesis is that **a governed base scientific LLM, when coupled through a multi-agent orchestration layer to a domain-specialized viral protein foundation model and other scientific tools, will outperform less integrated baselines in viral scientific reasoning while providing stronger provenance, uncertainty awareness, and auditability**. The project is therefore positioned as a **scientific AI systems effort** rather than a stand-alone bioinformatics model-development effort.

---

## Aim 1. Develop a governed base scientific LLM for multi-agent orchestration of viral science workflows.

The first aim is to develop the **Base Scientific LLM Orchestrator Agent**, which will serve as the control layer of the system. Its role is to interpret a scientific question, decompose it into structured subtasks, decide which specialized agents and tools should be invoked, sequence or parallelize those invocations, integrate intermediate outputs, and produce a final reasoning trace and recommendation. In the proposed architecture, the base LLM is not a stand-alone chatbot; it is the reasoning and coordination engine that makes the broader system composable.

This aim is directly responsive to Focus Area 19C, which emphasizes **strong base LLMs designed for flexible integration** across specialized foundation models and tools. It is also responsive to Topic 19’s broader emphasis on AI systems that use tools, support scientific reasoning, and operate in an iterative workflow rather than merely generating narrative text. The orchestrator will therefore be optimized for scientific planning, tool-aware reasoning, and evidence synthesis rather than generic conversation. Inputs to the orchestrator will include the user’s scientific question, workflow context, metadata describing available agents and tools, and structured outputs returned from prior agent calls. Outputs will include a task plan, an execution trace, a synthesized reasoning summary, a ranked set of interpretations or hypotheses, and an uncertainty-aware final response, all accompanied by provenance-linked workflow records.  

In Phase I, we will use a **governed adaptation strategy** rather than attempting frontier-scale pretraining of a general LLM. Training data for adaptation will include scientific task decomposition examples, structured tool-use traces, multi-step reasoning demonstrations over heterogeneous evidence, and workflow exemplars relevant to viral biology. The purpose is to produce dependable orchestration behavior in scientific settings: correct routing to specialized agents, consistent interpretation of returned evidence, preservation of provenance, and structured synthesis into testable scientific conclusions. This adaptation strategy is well matched to Phase I because the FOA asks for a clear proof-of-concept workflow and quantitative evidence of potential AI advantage, not a maximally scaled frontier model. 

**Expected Phase I outcome for Aim 1:** a prototype governed base scientific LLM capable of provenance-aware orchestration of multi-step viral analysis workflows, with structured invocation of downstream agents and auditable reasoning traces.

---

## Aim 2. Train a prototype from-scratch viral protein foundation model as a specialized reasoning module.

The second aim is to develop the system’s principal specialized foundation model: the **Viral Protein Foundation Agent**. This module is intended to capture viral sequence grammar, mutation context, functional constraint, and evolutionary regularity in a way that more general protein language models may not fully represent. It is the core domain-specialized component that differentiates the proposed architecture from generic scientific LLM approaches.

This aim is justified by 19C because the FOA does not call only for powerful base LLMs; it explicitly calls for base LLMs that can be **flexibly integrated with specialized foundation models and/or tools**. Viral proteins occupy a biologically distinctive regime shaped by rapid evolution, immune selection, host adaptation, and uneven experimental characterization. A specialized viral protein foundation model is therefore scientifically justified as a reusable module that provides priors and representations tailored to a high-value scientific domain. The critical point is that this model is not proposed as an isolated end product. It is designed from the outset to operate inside a broader composable reasoning architecture coordinated by the base scientific LLM. 

Inputs to this agent will include viral protein sequences, mutation lists, aligned or unaligned sequence sets, and optional contextual information such as subtype, clade, or region annotations. Outputs will include sequence embeddings, residue-level saliency or importance signals, mutation-effect priors, representation-based similarity measures, and structured summaries of sequence-context evidence relevant to downstream reasoning. These outputs will be consumed by the other agents and by the orchestrator as evidence, not treated as final stand-alone conclusions.

In Phase I, this module will be developed as a **from-scratch prototype viral protein foundation model** trained on curated viral protein sequence corpora. The model and corpus scale will be deliberately bounded to fit the nine-month proof-of-concept scope. Pretraining objectives will focus on learning reusable sequence representations and mutation-context signals rather than optimizing one narrow downstream task. This design is aligned with Phase I expectations because it prioritizes architectural feasibility and representation utility while leaving larger-scale expansion for a possible Phase II effort. 

**Expected Phase I outcome for Aim 2:** a trained prototype viral protein foundation model that produces domain-specialized embeddings and mutation-context priors useful within integrated workflows such as antigenic escape assessment and cross-species adaptation analysis.

---

## Aim 3. Build a modular multi-agent framework connecting specialized agents and scientific tools.

The third aim is to build the **multi-agent integration framework** that operationalizes composability. This framework will connect the base scientific LLM to five core agent types: the Viral Protein Foundation Agent, the Structure Reasoning Agent, the Evolutionary Dynamics Agent, the Quantitative Inference Agent, and the Evidence Agent. The technical goal is to ensure that heterogeneous computational components can be coordinated in a common reasoning environment rather than remaining isolated point solutions.

The **Structure Reasoning Agent** will translate sequence-level variation into structure-linked hypotheses by interfacing with structure-capable models and mutation-effect tools. It will assess possible impacts on local structural context, receptor-binding geometry, epitope exposure, or related features relevant to antigenic escape and host adaptation. The **Evolutionary Dynamics Agent** will provide phylogenetic plausibility and historical context, determining whether candidate mutations or variant profiles are consistent with known evolutionary patterns, clade structure, conservation, or plausible adaptive trajectories. The **Quantitative Inference Agent** will provide calibration, ranking, uncertainty estimation, and consistency checks so that the overall system remains grounded in explicit quantitative evidence rather than narrative alone. The **Evidence Agent** will retrieve and reconcile relevant prior knowledge from literature, curated databases, and domain resources so that system-generated hypotheses can be supported, challenged, or identified as speculative. This multi-agent design directly matches Topic 19’s emphasis on AI systems that use external tools and integrate diverse evidence streams in a closed-loop discovery workflow. 

Across all agents, four architectural principles will be enforced. First, each agent will expose a **well-defined input/output schema** so that the orchestrator can invoke it reliably and integrate its outputs across multiple reasoning steps. Second, each agent will operate through a **tool interface layer** that records model or tool version, parameters, input context, confidence metadata, and provenance. Third, each agent will support **uncertainty-aware outputs**, including ranked alternatives, confidence scores, or abstention flags where appropriate. Fourth, each agent will be designed for **replaceability**, allowing improved models or tools to be swapped into the architecture later without requiring redesign of the whole system. These principles are essential because 19C is fundamentally about **composable and modular foundation models**, not simply about using many tools at once. 

In Phase I, the Structure, Evolutionary, Quantitative, and Evidence agents will be implemented primarily through **adapter-based integration and tool wrapping** rather than full custom pretraining. Their value in Phase I lies in integration quality, provenance preservation, and structured output behavior. Wrappers and translation layers will convert raw tool outputs into machine-readable evidence objects that can be synthesized by the orchestrator. This is both technically efficient and programmatically appropriate for a Phase I proof of concept. 

**Expected Phase I outcome for Aim 3:** a working multi-agent environment in which the base scientific LLM coordinates interoperable specialized agents and scientific tools through shared schemas, provenance logging, and uncertainty propagation.

---

## Aim 4. Demonstrate and quantify AI advantage on closed-loop viral science workflows.

The fourth aim is to demonstrate and quantitatively evaluate the assembled system on two representative workflows: **antigenic escape assessment** and **cross-species adaptation analysis**. This aim is essential because the Genesis Mission Phase I structure explicitly requires a **clear, tangible research workflow** and **quantitative analysis** showing whether the proposed approach is on a trajectory toward transformative scientific capability. 

In the **antigenic escape assessment** workflow, the system will begin from a sequence variant or mutation set and determine whether the available evidence supports concern for altered antigenic properties. The orchestrator will obtain mutation-context priors from the Viral Protein Foundation Agent, structural interpretation from the Structure Reasoning Agent, evolutionary plausibility from the Evolutionary Dynamics Agent, supporting or contradictory prior knowledge from the Evidence Agent, and calibrated prioritization from the Quantitative Inference Agent. The final output will be an auditable, uncertainty-aware assessment that explains both the conclusion and the evidence chain that led to it.

In the **cross-species adaptation analysis** workflow, the system will begin from a sequence, mutation profile, or candidate variant and assess whether the evidence is consistent with host-adaptive change. This workflow will place greater emphasis on mutation plausibility, host-associated evolutionary patterns, evidence reconciliation, and uncertainty-aware ranking of interpretations. These two workflows were chosen because they are scientifically meaningful, computationally heterogeneous, and directly test the value of composable cross-domain reasoning. 

The evaluation framework will operate at three levels: **component performance**, **workflow performance**, and **AI advantage trajectory**. At the component level, we will assess whether the orchestrator reliably performs task decomposition and agent routing, whether the viral protein foundation model contributes distinct domain-specific signals, and whether the other agents return stable, structured, provenance-aware outputs. At the workflow level, we will compare the full system against three baseline categories:
(1) a **single-model baseline** in which one general model attempts the reasoning task without modular agent support;
(2) a **non-agentic compositional baseline** in which tools are manually chained but not coordinated by an orchestrating reasoning model; and
(3) a **manual or expert-assembled workflow** using the same tools outside the agent framework. Metrics will include predictive utility, reasoning coherence, evidence traceability, uncertainty calibration, and time-to-hypothesis. At the AI advantage trajectory level, we will examine whether performance improves as additional evidence sources or agent capabilities are added, thereby testing whether the architecture shows a credible path toward broader scientific capability rather than only isolated prototype performance. This approach is directly aligned with the FOA’s framing of Phase I success. 

**Expected Phase I outcome for Aim 4:** quantitative proof-of-concept evidence that a sovereign, composable, multi-agent architecture improves at least a subset of targeted workflow metrics relative to less integrated baselines, while also generating a defensible roadmap for Phase II scaling.

---

## Milestones, Go/No-Go Criteria, and Phase I Outcome

The Phase I effort will be organized as a **nine-month, milestone-driven proof of concept**. In Months 1–2, we will finalize the agent protocol, define shared schemas for evidence and provenance, establish artifact-governance standards, assemble the curated viral protein corpus, and stand up the baseline orchestration environment. In Months 3–4, we will adapt the base scientific LLM and train the prototype viral protein foundation model. In Months 5–6, we will integrate the Structure, Evolutionary, Quantitative, and Evidence agents. In Months 7–8, we will execute the two full demonstration workflows and perform baseline comparisons. In Month 9, we will finalize the evaluation package, organize reusable workflow artifacts, and complete a Phase II readiness assessment. 

Go/no-go decisions will be based on five criteria. First, the base scientific LLM must reliably execute structured task decomposition and agent routing without brittle protocol failure. Second, the viral protein foundation model must contribute domain-specific utility within integrated workflows rather than duplicating generic sequence features. Third, the five-agent system must operate inside a shared provenance-aware framework that preserves structured outputs, confidence metadata, and reproducibility. Fourth, the assembled system must demonstrate measurable value relative to less integrated baselines in at least some targeted AI advantage metrics, such as reasoning coherence, evidence traceability, uncertainty calibration, workflow efficiency, or predictive utility. Fifth, the project must produce a technically coherent rationale for Phase II scaling in model capacity, tool breadth, scientific scope, and computing integration. These criteria directly reflect the FOA’s expectation that Phase I serve as a quantitative decision point on whether a larger transformative capability is plausible. 

At the conclusion of Phase I, we expect to deliver:
(1) a prototype governed base scientific LLM adapted for agentic orchestration;
(2) a prototype from-scratch viral protein foundation model;
(3) a modular multi-agent integration framework with standardized interfaces, provenance logging, and uncertainty propagation;
(4) two working demonstration workflows for antigenic escape assessment and cross-species adaptation analysis;
(5) a quantitative evaluation report comparing the system with single-model, non-agentic, and manual baselines; and
(6) a Phase II scaling roadmap.

If successful, **SOVEREIGN-VIROFM** will demonstrate a reusable template for DOE-relevant scientific AI systems in which a strong base scientific LLM is flexibly integrated with specialized foundation models and external tools in a governed multi-agent environment. In this sense, the project is a direct test of the 19C thesis that **composable and modular foundation model systems can produce new forms of cross-domain AI advantage for science**.  

---

下一步最合适的是我把这版再继续压成 **更接近 5 页长度的精简最终稿**。
