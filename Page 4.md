下面给你 **Research Strategy / Technical Approach – Page 4: Milestones, Timeline, and Go/No-Go Criteria** 的英文草稿。这个页面的作用是把 Phase I 变成一个很清楚的 **9-month proof-of-concept execution plan**，并且把 DOE Genesis Mission 很看重的 **quantitative validation**、**trajectory toward AI advantage**、以及为后续 Phase II 做准备的逻辑写出来。

---

# Research Strategy / Technical Approach

## 4. Milestones, Timeline, and Go/No-Go Criteria

The proposed Phase I effort is structured as a **nine-month, milestone-driven proof of concept** designed to satisfy the Genesis Mission requirement that teams demonstrate a **clear, tangible research workflow** and provide **quantitative analysis** of whether the proposed approach is on a trajectory toward transformative scientific capability. Consistent with the FOA, the purpose of Phase I is not to fully scale the final system, but to establish whether the underlying architecture, workflow design, and evaluation framework justify larger follow-on investment. Our milestones are therefore organized around three linked objectives: **(1) demonstrating technical feasibility of the multi-agent architecture, (2) validating measurable AI advantage on representative viral science workflows, and (3) generating a credible Phase II scaling roadmap.** 

### 4.1 Phase I Execution Logic

The execution plan follows the architecture described in earlier sections. The project begins by establishing the base scientific LLM orchestration layer and prototype viral protein foundation model, then incrementally integrates the remaining agents and tool interfaces, and finally evaluates the assembled system on the two Phase I demonstration workflows: **antigenic escape assessment** and **cross-species adaptation analysis**. This staged design reduces technical risk while ensuring that each milestone produces inspectable artifacts that can be reused in later integration and evaluation steps. It also supports the Genesis Mission expectation that Phase I teams provide not only a prototype system, but also quantitative evidence that performance improves with better workflows, additional evidence, or greater compositional sophistication. 

### 4.2 Timeline and Milestones

#### Months 1–2: System Definition, Data Governance, and Initial Agent Scaffolding

During the first phase of the project, we will finalize the agent protocol, define common schemas for task requests and evidence objects, establish provenance and metadata standards, and assemble the curated training and evaluation datasets required for Phase I. In parallel, we will stand up the initial orchestration environment and implement baseline wrappers for agent invocation, structured logging, and workflow tracing.

**Milestones for Months 1–2:**

* Finalized multi-agent protocol for structured request/response exchange
* Defined provenance schema, uncertainty fields, and version-tracking requirements
* Curated prototype viral protein training corpus and initial benchmark task sets
* Initial orchestration environment and agent interface scaffolding operational
* Baseline evaluation plan and comparison systems specified

**Success criterion:** The project has a working agent communication layer, a governed data and artifact pipeline, and the minimum infrastructure needed to begin model adaptation and independent agent testing.

#### Months 3–4: Base Scientific LLM Adaptation and Viral Protein Foundation Model Prototype

In the second phase, we will adapt the base scientific LLM for scientific task decomposition, tool routing, evidence synthesis, and workflow-aware response generation. At the same time, we will train the prototype viral protein foundation model on the curated viral protein corpus and test its ability to produce stable, biologically meaningful representations and mutation-context priors.

**Milestones for Months 3–4:**

* Adapted base scientific LLM capable of structured task planning and agent routing
* Prototype viral protein foundation model trained and producing embeddings and mutation-context outputs
* Independent performance checks completed for orchestrator and viral protein modules
* Initial structured output format validated for downstream integration

**Success criterion:** The orchestrator can reliably invoke stubbed or early-stage agents using the shared protocol, and the viral protein module demonstrates usable domain-specialized outputs for downstream workflows.

#### Months 5–6: Integration of Structure, Evolutionary, Quantitative, and Evidence Agents

During the third phase, we will implement the remaining four agents through tool wrappers, reasoning adapters, and structured evidence translation layers. These agents will be connected to the orchestrator through the common protocol, and we will perform staged integration tests in which the system executes partial and then complete workflow chains.

**Milestones for Months 5–6:**

* Structure Reasoning Agent integrated with selected structure-analysis capabilities
* Evolutionary Dynamics Agent integrated with selected phylogenetic and evolutionary context tools
* Quantitative Inference Agent integrated with ranking, calibration, and uncertainty modules
* Evidence Agent integrated with literature or knowledge retrieval components
* End-to-end provenance logging and confidence propagation operational across all agents
* Partial workflow tests completed for both demonstration tasks

**Success criterion:** The system can execute multi-step, multi-agent workflows with traceable intermediate outputs and without protocol failure across the core agents.

#### Months 7–8: End-to-End Workflow Demonstration and Baseline Comparisons

In the fourth phase, we will run full demonstrations of the two target workflows—antigenic escape assessment and cross-species adaptation analysis—and compare the multi-agent system with predefined baselines. These baselines will include single-model approaches, manually chained non-agentic workflows, and manually assembled tool-use pipelines where feasible. Evaluation will focus not only on task outcomes, but also on reasoning coherence, evidence traceability, uncertainty calibration, and workflow efficiency.

**Milestones for Months 7–8:**

* Full end-to-end execution of both Phase I demonstration workflows
* Baseline comparisons completed across all major evaluation categories
* Quantitative evidence collected for predictive utility, reasoning quality, traceability, calibration, and time-to-hypothesis
* Error analysis and workflow refinement performed on failure cases
* Preliminary Phase II scaling hypotheses identified

**Success criterion:** The system produces measurable and interpretable gains in at least a subset of the targeted AI advantage metrics relative to less integrated baselines, or else reveals a clear scaling path supported by partial gains and workflow analysis.

#### Month 9: Final Validation, Reporting, and Phase II Readiness Assessment

The final month will be used to consolidate results, finalize the quantitative evaluation package, document the architecture and workflow artifacts, and produce a Phase II readiness assessment. This will include explicit go/no-go decisions for larger-scale model development, broader tool integration, and expanded scientific scope.

**Milestones for Month 9:**

* Final quantitative evaluation report completed
* Workflow artifacts, provenance records, and model documentation organized for reuse
* Phase II scaling roadmap drafted, including proposed expansion in model scale, agent coverage, and scientific breadth
* Final go/no-go assessment completed and documented

**Success criterion:** The project delivers a complete proof-of-concept package demonstrating technical feasibility, quantitative evaluation, and a justified recommendation regarding Phase II expansion.

### 4.3 Go/No-Go Criteria

The Phase I project will use explicit **go/no-go criteria** to determine whether the architecture has demonstrated sufficient promise for Phase II scaling. These criteria are designed to match the Genesis Mission expectation that Phase I provide evidence that the approach is on a trajectory toward a larger transformative capability, rather than simply producing a partially functioning prototype. 

#### Go Criterion 1: Orchestration Feasibility

The adapted base scientific LLM must reliably execute structured task decomposition and agent routing across the two demonstration workflows without repeated protocol breakdown or excessive manual intervention.

**Go threshold:** The orchestrator consistently produces valid multi-step workflow plans and successfully invokes the required agents using the shared communication schema.

**No-go condition:** Workflow execution remains brittle, non-reproducible, or dependent on ad hoc manual correction after iterative refinement.

#### Go Criterion 2: Specialized Module Utility

The prototype viral protein foundation model must provide domain-specific outputs that are meaningfully usable within the integrated workflow, rather than behaving as a redundant replacement for generic sequence features.

**Go threshold:** The viral protein module contributes informative representation or mutation-context signals that improve at least one downstream reasoning or ranking task relative to a simpler sequence-only baseline.

**No-go condition:** The module does not provide evidence of distinct utility within the multi-agent workflow, or its outputs are unstable or not reusable by downstream agents.

#### Go Criterion 3: Multi-Agent Integration Integrity

All five agents must operate within a shared, provenance-aware framework that preserves structured outputs, confidence metadata, and reproducibility of intermediate reasoning artifacts.

**Go threshold:** End-to-end workflow traces are complete, auditable, and reproducible for the target demonstration tasks.

**No-go condition:** Agent integration fails to preserve provenance, confidence, or interoperability in a way that undermines the core 19C composability objective.

#### Go Criterion 4: Quantitative Evidence of AI Advantage

The assembled system must demonstrate measurable value relative to less integrated alternatives using the Phase I evaluation framework.

**Go threshold:** The prototype shows clear gains in one or more pre-specified metrics—such as reasoning coherence, evidence traceability, uncertainty calibration, workflow efficiency, or predictive utility—or else demonstrates a compelling scaling trend when additional agents or evidence sources are included.

**No-go condition:** The system fails to show measurable benefit over baselines and provides no defensible indication that added composability improves workflow capability.

#### Go Criterion 5: Credible Scaling Path to Phase II

The project must produce a technically and scientifically coherent rationale for Phase II expansion.

**Go threshold:** Results support a practical roadmap for scaling model capacity, broadening the agent ecosystem, expanding viral domains or scientific tasks, and strengthening integration with larger scientific computing infrastructure.

**No-go condition:** Even if components function individually, the project does not produce a convincing case that further investment would substantially improve scientific reasoning capability.

### 4.4 Quantitative Decision Framework

To support transparent go/no-go decisions, we will summarize Phase I performance in a structured decision matrix spanning five categories:

1. **Architecture readiness** – stability of orchestration, protocol integrity, and successful workflow execution
2. **Specialized model contribution** – measurable value of the viral protein foundation model within integrated workflows
3. **Workflow performance** – end-to-end results on antigenic escape and cross-species adaptation tasks
4. **Trustworthiness metrics** – provenance completeness, uncertainty calibration, and evidence traceability
5. **Scaling evidence** – signs that adding agent capability, evidence sources, or model capacity improves system behavior

A favorable Phase II recommendation will require strong performance in architecture readiness and integration integrity, plus positive evidence in at least some of the remaining categories. This reflects the FOA’s broad view of Phase I success, which may include gains in scientific insight, tighter coupling of data and hypotheses, improved workflows, and evidence of performance growth with additional resources. 

### 4.5 Expected Outcome of Phase I

At the conclusion of the nine-month effort, the expected outcome is a **well-documented prototype of a sovereign, multi-agent, composable scientific foundation model system** that has been tested on two scientifically meaningful viral reasoning workflows and evaluated quantitatively against less integrated baselines. Even if Phase I does not fully optimize every component, success will be defined by whether the project establishes a clear and defensible case that the architecture can evolve into a broader scientific reasoning capability under Phase II support. In this sense, the milestones and go/no-go criteria are not merely project-management devices; they are the operational mechanism by which the project will test the central 19C hypothesis that strong base LLMs, when flexibly integrated with specialized foundation models and scientific tools, can create new forms of cross-domain AI advantage for science. 

---

如果你愿意，下一步我可以把前面四页内容再整理成一个 **更完整、更像正式 DOE narrative 的连续版本**。
