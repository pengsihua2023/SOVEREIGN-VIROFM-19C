下面给你 **Research Strategy / Technical Approach – Page 2** 的英文草稿，紧接上一页，重点展开 architecture components 和五个 agents 的设计。写法继续保持 DOE/ASCR 风格：强调 **base LLM + specialized foundation models + tools + modular interfaces + quantitative evaluation**，并且把 multi-agent 说成一种为 19C 服务的科学计算架构，而不是表面包装。

---

# Research Strategy / Technical Approach

## 2. Architecture Components and Agent Design

The proposed **SOVEREIGN-VIROFM** system is designed as a modular, multi-agent scientific reasoning environment in which a governed base scientific LLM coordinates specialized model agents and external scientific tools through standardized interfaces. This design directly reflects the objectives of Topic 19 and Focus Area 19C: a strong base LLM is not used as a stand-alone model, but as the planning and synthesis core of a composable architecture that integrates domain-specific foundation models and tool-driven analytical workflows. In technical terms, the system is organized as a message-passing, provenance-aware agent graph in which each agent contributes a distinct form of scientific evidence and returns structured outputs that can be reused, inspected, and recombined across workflows.

Across all agents, we will implement four common design principles. First, each agent will expose a **well-defined input/output schema** so that the base LLM can invoke it reliably and aggregate outputs across multiple reasoning steps. Second, each agent will be wrapped by a **tool interface layer** that records model version, parameters, input context, and confidence metadata, enabling provenance and reproducibility. Third, each agent will support **uncertainty-aware outputs**, including confidence scores, abstention flags, or ranked hypotheses where appropriate. Fourth, each agent will be designed for **replaceability**, so that improved models or tools can be inserted later without rewriting the entire system. These principles are essential for operationalizing composability as an architectural property rather than a loose collection of API calls. 

### 2.1 Base Scientific LLM Orchestrator Agent

The **Base Scientific LLM Orchestrator Agent** is the control layer of the system. Its role is to interpret a scientific question, decompose it into subtasks, decide which agents and tools should be invoked, sequence or parallelize those invocations, integrate returned evidence, and produce a final reasoning trace and recommendation.

**Inputs:**
Inputs to the orchestrator include the user’s scientific question, task context, optional prior workflow state, metadata about available agents and tools, and structured outputs returned from previous agent calls. Example inputs may include a viral sequence or mutation list, a target question such as whether a new variant shows immune-escape potential, or a request to assess host-adaptation risk.

**Outputs:**
The orchestrator produces a structured task plan, an execution trace identifying which agents were called and in what order, a synthesized reasoning summary, a ranked set of hypotheses or interpretations, and an uncertainty-aware final response. It also produces machine-readable records of evidence provenance for downstream evaluation.

**Tool interfaces:**
The orchestrator does not perform specialized biological computation itself; instead, it interfaces with all downstream agents through a shared agent protocol. This protocol will include function-style calls, agent capability descriptions, JSON-like structured argument passing, and standardized response fields for confidence, citations, and provenance.

**Training and adaptation strategy:**
In Phase I, we will adapt a base scientific LLM for planning, tool-use reasoning, and evidence synthesis rather than train a frontier-scale general LLM from scratch. Adaptation will focus on scientific task decomposition, multi-step reasoning over structured evidence, tool routing policies, and output formatting for auditable workflows. Training data for this adaptation layer will include curated scientific tasks, agent-invocation exemplars, synthetic workflow demonstrations, and domain-specific reasoning templates. The central requirement is not generic conversational fluency, but reliable orchestration behavior in scientific settings. This directly supports the FOA emphasis on strong base LLMs for scientific reasoning and flexible integration.

### 2.2 Viral Protein Foundation Agent

The **Viral Protein Foundation Agent** is the main specialized foundation model module in the architecture and the principal differentiator of the proposed system. Its purpose is to provide domain-specific representation learning for viral proteins, capturing sequence grammar, evolutionary context, functional constraint, and mutation-dependent biological regularities that may be weakly represented in general protein models.

**Inputs:**
Inputs include viral protein sequences, aligned or unaligned sequence sets, mutation lists, residue windows, clade or subtype context when available, and optionally protein-region annotations such as receptor-binding or antigenic sites.

**Outputs:**
Outputs include sequence embeddings, residue-level saliency or importance maps, mutation-effect priors, representation-based similarity scores, ranked hypotheses about functional constraint, and structured summaries of mutation context. For downstream workflows, this agent may output scores indicating whether a mutation pattern appears unusual, conserved, potentially adaptive, or plausibly relevant to antigenic change.

**Tool interfaces:**
This agent interfaces with sequence preprocessing tools, alignment utilities if needed, embedding extractors, mutation-scoring modules, and internal model APIs. Outputs are passed back in structured form so that other agents, especially the Structure and Evolutionary agents, can use them as priors rather than final conclusions.

**Training and adaptation strategy:**
Unlike the orchestrator, this module will be trained as a **from-scratch prototype viral protein foundation model** on curated viral protein sequence corpora. The goal is to create a specialized sequence representation space optimized for viral biology rather than rely exclusively on transfer from general protein language models. Pretraining objectives may include masked residue modeling, span corruption, contrastive representation learning across related variants, and region-aware objectives emphasizing mutation context and sequence-function regularity. In Phase I, model scale will be deliberately bounded to fit the proof-of-concept scope, but the design will be chosen to support Phase II scaling. This agent is justified by 19C because it serves as a specialized foundation model that is flexibly integrated into a larger scientific reasoning system rather than operating in isolation. 

### 2.3 Structure Reasoning Agent

The **Structure Reasoning Agent** contributes biomolecular interpretation by mapping sequence-level observations into structural hypotheses. Its role is to assess how mutations or mutation combinations may alter local folding context, receptor-binding geometry, epitope exposure, conformational flexibility, or other structure-linked properties relevant to antigenic escape and host adaptation.

**Inputs:**
Inputs include viral sequences or sequence variants, mutation sets, structural templates where available, residue positions of interest, and priors from the Viral Protein Foundation Agent. The agent may also receive a workflow request such as “evaluate whether these substitutions are consistent with altered receptor interaction” or “assess possible disruption of known antigenic surface features.”

**Outputs:**
Outputs include structural compatibility assessments, residue-neighborhood summaries, mutation-impact interpretations, ranked structural hypotheses, and confidence annotations. Where appropriate, the agent may return predicted local structural changes, affected residue clusters, or explanations linking a mutation to a known functional region.

**Tool interfaces:**
This agent interfaces with structure-prediction or structure-retrieval tools, mutation-effect estimators, structural alignment tools, residue-contact or solvent exposure utilities, and other structure-analysis modules available within the project environment. Importantly, the agent will translate raw structural outputs into machine-readable summaries that other agents can use, rather than returning only unprocessed coordinates or images.

**Training and adaptation strategy:**
The Structure Reasoning Agent will primarily be built through **adapter-based integration** rather than full model pretraining in Phase I. We will wrap existing structure-capable models and tools with standardized interfaces and train lightweight reasoning layers or prompt/adapter policies that convert structural results into consistent scientific evidence statements. This approach is appropriate for Phase I because it emphasizes integration and auditability while preserving the option to deepen structural modeling in Phase II.

### 2.4 Evolutionary Dynamics Agent

The **Evolutionary Dynamics Agent** evaluates whether observed mutations, sequence clusters, or variant patterns are evolutionarily plausible, historically unusual, or consistent with known adaptive trajectories. This agent helps distinguish statistically visible changes from biologically credible evolutionary signals.

**Inputs:**
Inputs include sequence sets, metadata-enriched viral isolates when available, mutation lists, clade or lineage annotations, temporal or geographic labels, and candidate hypotheses produced by the orchestrator or other agents.

**Outputs:**
Outputs include phylogenetic plausibility scores, mutation-context histories, clade association summaries, ranked adaptive hypotheses, and uncertainty-aware interpretations of whether a mutation or mutation combination appears evolutionarily credible, convergent, emerging, or rare.

**Tool interfaces:**
This agent will interface with alignment tools, phylogenetic reconstruction utilities, clade assignment modules, evolutionary conservation estimators, and selective-pattern analysis tools where feasible. It may also consume outputs from the Viral Protein Foundation Agent to compare learned representation-based novelty with tree-based evolutionary context.

**Training and adaptation strategy:**
In Phase I, this agent will rely on **tool-mediated integration plus task-specific adaptation**, not full from-scratch phylogenetic model training. We will create wrappers and reasoning templates for selected evolutionary analysis tools and build translation layers that convert their outputs into structured signals for the orchestrator. The primary innovation is not a new tree-building algorithm, but integration of evolutionary evidence into a broader scientific reasoning system. This is strongly aligned with Topic 19’s emphasis on tool-enabled, cross-domain reasoning workflows. 

### 2.5 Quantitative Inference Agent

The **Quantitative Inference Agent** provides statistical analysis, ranking, uncertainty estimation, and consistency checks across evidence streams. Its purpose is to prevent the system from acting like a purely narrative generator by grounding conclusions in explicit quantitative signals wherever possible.

**Inputs:**
Inputs include candidate mutation hypotheses, scores from other agents, benchmark labels when available, comparative outputs from baseline models, and structured workflow outputs requiring confidence analysis or ranking.

**Outputs:**
Outputs include calibrated scores, uncertainty intervals or confidence summaries, ranked candidate interpretations, significance-style assessments where appropriate, and flags indicating insufficient evidence or high ambiguity. This agent also contributes to final workflow scoring for evaluation metrics such as calibration and traceable decision quality.

**Tool interfaces:**
This agent interfaces with statistical computing libraries, calibration tools, ranking utilities, evaluation pipelines, and uncertainty-estimation procedures. In evaluation mode, it will also connect to benchmarking and reporting tools used to quantify AI advantage across workflows.

**Training and adaptation strategy:**
This agent will be implemented primarily through **tool-centric composition** plus light reasoning adaptation. Rather than training a separate large model, we will connect robust quantitative packages to the agent framework and ensure that results are returned in structured, audit-friendly form. This is especially important for Phase I because the FOA expects quantitative evaluation of workflow performance and AI advantage, not only qualitative demonstrations. 

### 2.6 Evidence Agent

The **Evidence Agent** provides external knowledge grounding through retrieval and reconciliation of relevant literature, curated databases, and domain resources. Its function is to connect model-generated hypotheses to prior scientific evidence and to identify agreement, conflict, or missing support.

**Inputs:**
Inputs include scientific questions, mutation lists, protein regions, candidate mechanisms proposed by other agents, and terms or concepts requiring contextualization from external resources.

**Outputs:**
Outputs include retrieved evidence summaries, literature-grounded support or contradiction statements, evidence strength rankings, provenance-linked citations, and flags for sparse or conflicting evidence. These outputs help the orchestrator differentiate well-supported hypotheses from speculative ones.

**Tool interfaces:**
This agent interfaces with retrieval systems, literature search and ranking modules, domain databases, and structured knowledge resources. It will normalize outputs into concise evidence objects that can be cited in final reasoning traces and reused during evaluation.

**Training and adaptation strategy:**
The Evidence Agent will be implemented through **retrieval-augmented adaptation** rather than independent model pretraining. We will focus on query formulation, evidence filtering, contradiction handling, and structured summarization. Because Topic 19 emphasizes AI systems that work with scientific evidence in rigorous workflows, this agent is critical for scientific grounding and for the provenance requirements of the broader sovereign architecture.

### 2.7 Inter-Agent Communication and Workflow Composition

The value of the architecture lies not only in the individual agents, but in how they communicate. All agents will use a shared schema for request and response exchange, including: task identifier, input object, model/tool version, confidence metadata, provenance record, output object, and optional abstention or escalation flags. The orchestrator will use these structured outputs to decide whether to accept a result, request clarification from another agent, invoke an additional tool, or produce a final integrated hypothesis.

For example, in an **antigenic escape assessment** workflow, the orchestrator may first call the Viral Protein Foundation Agent to obtain mutation-context priors, then invoke the Structure Reasoning Agent to assess epitope and receptor-region implications, then call the Evolutionary Dynamics Agent to evaluate plausibility in historical and clade context, and finally use the Quantitative Inference Agent and Evidence Agent to calibrate and contextualize the conclusion. A similar but distinct chain can be used for **cross-species adaptation analysis**, with greater emphasis on mutation plausibility, host-associated patterns, and evidence reconciliation. This architecture enables workflow specialization without sacrificing system-wide modularity.

Taken together, these five agents instantiate the core technical thesis of the proposal: that composable scientific reasoning requires a governed base LLM, domain-specialized foundation models, tool-mediated analytical components, and structured multi-agent coordination. In the next section, we describe how these components will be trained, integrated, and evaluated during Phase I to determine whether the resulting architecture provides measurable AI advantage and a credible path toward Phase II scaling.

---

下一步最自然的是继续写 **Page 3: Training, Integration, and Evaluation Plan**。
