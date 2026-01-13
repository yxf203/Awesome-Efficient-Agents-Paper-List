<h1 align="center">Toward Efficient Agents: A Survey of Memory, Tool Learning, and Planning</h1>

## ⚡introduction

Recent years have seen growing interest in extending large language models into agentic systems. While agent capabilities have advanced rapidly, efficiency has received comparatively less attention despite being crucial for real-world deployment. This repository studies efficiency-guided agent design from three core components: memory, tool learning, and planning.

We provide a curated paper list to help readers quickly locate representative work, along with lightweight notes on how each topic connects to efficiency.

- **Efficient Memory.** We organize memory-related papers into three processes: construction, management, and access.
- **Efficient Tool Learning.** We group papers into tool selection, tool calling, and tool-integrated reasoning.
- **Efficient Planning.** We collect work on planning that improves overall agent efficiency by reducing unnecessary actions and shortening trajectories.

![introduction-picture](assets/introduction-picture.png)

## 🧾Paper List

- [🧠Memory](#memory)
   * [Working Memory](#working-memory)
      + [Textual Memory](#textual-memory)
      + [Latent Memory](#latent-memory)
   * [External Memory](#external-memory)
      + [Item-based Memory](#item-based-memory)
      + [Graph-based Memory](#graph-based-memory)
      + [Hierarchical Memory](#hierarchical-memory)
   * [Multi-Agent Memory](#multi-agent-memory)
      + [Shared Memory](#shared-memory)
      + [Local Memory](#local-memory)
      + [Mixed Memory](#mixed-memory)
- [🛠️Tool Learning](#tool-learning)
   * [Tool Selection](#tool-selection)
      + [External Retriever](#external-retriever)
      + [Multi-Label Classification (MLC)](#multi-label-classification-mlc)
      + [Vocabulary-based Retrieval](#vocabulary-based-retrieval)
   * [Tool Calling](#tool-calling)
      + [In-Place Parameter Filling](#in-place-parameter-filling)
      + [Parallel Tool Calling](#parallel-tool-calling)
      + [Cost-Aware Tool Calling](#cost-aware-tool-calling)
      + [Efficient Test-Time Scaling](#efficient-test-time-scaling)
      + [Efficient Tool Calling with Post-training](#efficient-tool-calling-with-post-training)
   * [Tool-Integrated Reasoning (TIR)](#tool-integrated-reasoning-tir)
      + [Selective Invocation](#selective-invocation)
      + [Cost-Aware Policy Optimization](#cost-aware-policy-optimization)
- [🧩Planning](#planning)
   * [Single-Agent Planning Efficiency](#single-agent-planning-efficiency)
      + [Adaptive Budgeting and Control](#adaptive-budgeting-and-control)
      + [Structured Search](#structured-search-strategies)
      + [Task Decomposition](#task-decomposition-and-routing)
      + [Policy Optimization](#policy-optimization)
      + [Memory and Skill Acquisition](#architectural-synergy-with-memory-and-tools)
   * [Multi-Agent Collaborative Efficiency](#multi-agent-collaborative-efficiency)
      + [Topological Efficiency and Sparsification](#topological-efficiency)
      + [Protocol and Context Optimization](#protocol-and-context-optimization)
      + [Distilling Coordination into Planning](#distilling-coordination-into-planning)

<a name="memory"></a>

### 🧠Memory

![paper-memory-picture](assets/paper-memory-picture.png)

In the paper, we organize memory into construction, management, and access. Since many papers overlap across these stages, this README is primarily organized around memory construction to avoid redundancy.

<a name="working-memory"></a>
#### Working Memory

<a name="textual-memory"></a>
#####  Textual Memory

* Compress to Impress: Unleashing the Potential of Compressive Memory in Real-World Long-Term Conversations [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2025.coling-main.51/) [![arXiv](https://img.shields.io/badge/arXiv-2402.11975-b31b1b.svg)](https://arxiv.org/abs/2402.11975)
* Dynamic Cheatsheet: Test-Time Learning with Adaptive Memory [![arXiv](https://img.shields.io/badge/arXiv-2504.07952-b31b1b.svg)](https://arxiv.org/abs/2504.07952)
* MEM1: Learning to Synergize Memory and Reasoning for Efficient Long-Horizon Agents [![arXiv](https://img.shields.io/badge/arXiv-2506.15841-b31b1b.svg)](https://arxiv.org/abs/2506.15841)
* MemAgent: Reshaping Long-Context LLM with Multi-Conv RL-based Memory Agent [![arXiv](https://img.shields.io/badge/arXiv-2507.02259-b31b1b.svg)](https://arxiv.org/abs/2507.02259)
* AgentFold: Long-Horizon Web Agents with Proactive Context Management [![arXiv](https://img.shields.io/badge/arXiv-2510.24699-b31b1b.svg)](https://arxiv.org/abs/2510.24699)


<a name="latent-memory"></a>
#####  Latent Memory

* Long Context Compression with Activation Beacon [![arXiv](https://img.shields.io/badge/arXiv-2401.03462-b31b1b.svg)](https://arxiv.org/abs/2401.03462)
* MEMORYLLM: Towards Self-Updatable Large Language Models [![ICML](https://img.shields.io/badge/ICML-blue)](https://proceedings.mlr.press/v235/wang24s.html) [![arXiv](https://img.shields.io/badge/arXiv-2402.04624-b31b1b.svg)](https://arxiv.org/abs/2402.04624)
* $\text{Memory}^3$: Language Modeling with Explicit Memory  [![arXiv](https://img.shields.io/badge/arXiv-2407.01178-b31b1b.svg)](https://arxiv.org/abs/2407.01178) 
* MemoRAG: Boosting Long Context Processing with Global Memory-Enhanced Retrieval Augmentation [![ACM DL](https://img.shields.io/badge/ACM-DL-blue)](https://dl.acm.org/doi/abs/10.1145/3696410.3714805) [![arXiv](https://img.shields.io/badge/arXiv-2409.05591-b31b1b.svg)](https://arxiv.org/abs/2409.05591)
* Titans: Learning to Memorize at Test Time [![arXiv](https://img.shields.io/badge/arXiv-2501.00663-b31b1b.svg)](https://arxiv.org/abs/2501.00663)
* M+: Extending MemoryLLM with Scalable Long-Term Memory [![arXiv](https://img.shields.io/badge/arXiv-2502.00592-b31b1b.svg)](https://arxiv.org/abs/2502.00592)
* MemGen: Weaving Generative Latent Memory for Self-Evolving Agents [![arXiv](https://img.shields.io/badge/arXiv-2509.24704-b31b1b.svg)](https://arxiv.org/abs/2509.24704)

<a name="external-memory"></a>
#### External Memory

<a name="item-based-memory"></a>
#####  Item-based Memory

* MemoryBank: Enhancing Large Language Models with Long-Term Memory ![AAAI](https://img.shields.io/badge/AAAI-blue) [![arXiv](https://img.shields.io/badge/arXiv-2305.10250-b31b1b.svg)](https://arxiv.org/abs/2305.10250)
* MemoChat: Tuning LLMs to Use Memos for Consistent Long-Range Open-Domain Conversation [![arXiv](https://img.shields.io/badge/arXiv-2308.08239-b31b1b.svg)](https://arxiv.org/abs/2308.08239)
* ExpeL: LLM Agents Are Experiential Learners ![AAAI](https://img.shields.io/badge/AAAI-blue) [![arXiv](https://img.shields.io/badge/arXiv-2308.10144-b31b1b.svg)](https://arxiv.org/abs/2308.10144)
* RECOMP: Improving Retrieval-Augmented LMs with Compression and Selective Augmentation [![arXiv](https://img.shields.io/badge/arXiv-2310.04408-b31b1b.svg)](https://arxiv.org/abs/2310.04408)
* "My agent understands me better": Integrating Dynamic Human-like Memory Recall and Consolidation in LLM-Based Agents ![CHI](https://img.shields.io/badge/CHI-blue) [![arXiv](https://img.shields.io/badge/arXiv-2404.00573-b31b1b.svg)](https://arxiv.org/abs/2404.00573)
* Hello Again! LLM-powered Personalized Agent for Long-term Dialogue [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2025.naacl-long.272/) [![arXiv](https://img.shields.io/badge/arXiv-2406.05925-b31b1b.svg)](https://arxiv.org/abs/2406.05925) 
* On Memory Construction and Retrieval for Personalized Conversational Agents ![ICLR](https://img.shields.io/badge/ICLR-blue) [![arXiv](https://img.shields.io/badge/arXiv-2502.05589-b31b1b.svg)](https://arxiv.org/abs/2502.05589)
* A-MEM: Agentic Memory for LLM Agents ![NeurIPS](https://img.shields.io/badge/NeurIPS-blue) [![arXiv](https://img.shields.io/badge/arXiv-2502.12110-b31b1b.svg)](https://arxiv.org/abs/2502.12110)
* In Prospect and Retrospect: Reflective Memory Management for Long-term Personalized Dialogue Agents [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2025.acl-long.413/) [![arXiv](https://img.shields.io/badge/arXiv-2503.08026-b31b1b.svg)](https://arxiv.org/abs/2503.08026)
* MemInsight: Autonomous Memory Augmentation for LLM Agents [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2025.emnlp-main.1683/) [![arXiv](https://img.shields.io/badge/arXiv-2503.21760-b31b1b.svg)](https://arxiv.org/abs/2503.21760)
* Mem0: Building Production-Ready AI Agents with Scalable Long-Term Memory [![arXiv](https://img.shields.io/badge/arXiv-2504.19413-b31b1b.svg)](https://arxiv.org/abs/2504.19413)
* Cost-Efficient Serving of LLM Agents via Test-Time Plan Caching(Agentic Plan Caching: Test-Time Memory for Fast and Cost-Efficient LLM Agents ) ![NeurIPS](https://img.shields.io/badge/NeurIPS-blue) [![arXiv](https://img.shields.io/badge/arXiv-2506.14852-b31b1b.svg)](https://arxiv.org/abs/2506.14852)
* Agent KB: Leveraging Cross-Domain Experience for Agentic Problem Solving [![arXiv](https://img.shields.io/badge/arXiv-2507.06229-b31b1b.svg)](https://arxiv.org/abs/2507.06229)
* Memento: Fine-tuning LLM Agents without Fine-tuning LLMs [![arXiv](https://img.shields.io/badge/arXiv-2508.16153-b31b1b.svg)](https://arxiv.org/abs/2508.16153)
* Memory-R1: Enhancing Large Language Model Agents to Manage and Utilize Memories via Reinforcement Learning [![arXiv](https://img.shields.io/badge/arXiv-2508.19828-b31b1b.svg)](https://arxiv.org/abs/2508.19828)
* ReasoningBank: Scaling Agent Self-Evolving with Reasoning Memory [![arXiv](https://img.shields.io/badge/arXiv-2509.25140-b31b1b.svg)](https://arxiv.org/abs/2509.25140)
* Agentic Context Engineering: Evolving Contexts for Self-Improving Language Models [![arXiv](https://img.shields.io/badge/arXiv-2510.04618-b31b1b.svg)](https://arxiv.org/abs/2510.04618)


<a name="graph-based-memory"></a>
#####  Graph-based Memory

* KG-Agent: An Efficient Autonomous Agent Framework for Complex Reasoning over Knowledge Graph [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2025.acl-long.468/) [![arXiv](https://img.shields.io/badge/arXiv-2402.11163-b31b1b.svg)](https://arxiv.org/abs/2402.11163)
* GraphReader: Building Graph-based Agent to Enhance Long-Context Abilities of Large Language Models [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2024.findings-emnlp.746/) [![arXiv](https://img.shields.io/badge/arXiv-2406.14550-b31b1b.svg)](https://arxiv.org/abs/2406.14550)
* AriGraph: Learning Knowledge Graph World Models with Episodic Memory for LLM Agents [![arXiv](https://img.shields.io/badge/arXiv-2407.04363-b31b1b.svg)](https://arxiv.org/abs/2407.04363)
* Zep: A Temporal Knowledge Graph Architecture for Agent Memory  [![arXiv](https://img.shields.io/badge/arXiv-2501.13956-b31b1b.svg)](https://arxiv.org/abs/2501.13956)
* Mem0: Building Production-Ready AI Agents with Scalable Long-Term Memory [![arXiv](https://img.shields.io/badge/arXiv-2504.19413-b31b1b.svg)](https://arxiv.org/abs/2504.19413)
* D-SMART: Enhancing LLM Dialogue Consistency via Dynamic Structured Memory And Reasoning Tree [![arXiv](https://img.shields.io/badge/arXiv-2510.13363-b31b1b.svg)](https://arxiv.org/abs/2510.13363)

<a name="hierarchical-memory"></a>
#####  Hierarchical Memory

* MemGPT: Towards LLMs as Operating Systems [![arXiv](https://img.shields.io/badge/arXiv-2310.08560-b31b1b.svg)](https://arxiv.org/abs/2310.08560)
* A Human-Inspired Reading Agent with Gist Memory of Very Long Contexts [![ICML](https://img.shields.io/badge/ICML-blue)](https://proceedings.mlr.press/v235/lee24c.html) [![arXiv](https://img.shields.io/badge/arXiv-2402.09727-b31b1b.svg)](https://arxiv.org/abs/2402.09727)
* HiAgent: Hierarchical Working Memory Management for Solving Long-Horizon Agent Tasks with Large Language Model [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2025.acl-long.1575/) [![arXiv](https://img.shields.io/badge/arXiv-2408.09559-b31b1b.svg)](https://arxiv.org/abs/2408.09559)
* Memory OS of AI Agent [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2025.emnlp-main.1318/) [![arXiv](https://img.shields.io/badge/arXiv-2506.06326-b31b1b.svg)](https://arxiv.org/abs/2506.06326)
* MemOS: A Memory OS for AI System [![arXiv](https://img.shields.io/badge/arXiv-2507.03724-b31b1b.svg)](https://arxiv.org/abs/2507.03724)
* Hierarchical Memory for High-Efficiency Long-Term Reasoning in LLM Agents [![arXiv](https://img.shields.io/badge/arXiv-2507.22925-b31b1b.svg)](https://arxiv.org/abs/2507.22925)
* LightMem: Lightweight and Efficient Memory-Augmented Generation [![arXiv](https://img.shields.io/badge/arXiv-2510.18866-b31b1b.svg)](https://www.arxiv.org/abs/2510.18866)

<a name="multi-agent-memory"></a>
#### Multi-Agent Memory

<a name="shared-memory"></a>
#####  Shared Memory

* Memory Sharing for Large Language Model based Agents [![arXiv](https://img.shields.io/badge/arXiv-2404.09982-b31b1b.svg)](https://arxiv.org/abs/2404.09982)
* G-Memory: Tracing Hierarchical Memory for Multi-Agent Systems ![NeurIPS](https://img.shields.io/badge/NeurIPS-blue) [![arXiv](https://img.shields.io/badge/arXiv-2506.07398-b31b1b.svg)](https://arxiv.org/abs/2506.07398)
* MIRIX: Multi-Agent Memory System for LLM-Based Agents [![arXiv](https://img.shields.io/badge/arXiv-2507.07957-b31b1b.svg)](https://arxiv.org/abs/2507.07957)
* RCR-Router: Efficient Role-Aware Context Routing for Multi-Agent LLM Systems with Structured Memory [![arXiv](https://img.shields.io/badge/arXiv-2508.04903-b31b1b.svg)](https://arxiv.org/abs/2508.04903)
* MemIndex: Agentic Event-based Distributed Memory Management for Multi-agent Systems [![ACM DL](https://img.shields.io/badge/ACM-DL-blue)](https://dl.acm.org/doi/10.1145/3774946)

<a name="local-memory"></a>
#####  Local Memory

* LLM-Powered Decentralized Generative Agents with Adaptive Hierarchical Knowledge Graph for Cooperative Planning [![arXiv](https://img.shields.io/badge/arXiv-2502.05453-b31b1b.svg)](https://arxiv.org/abs/2502.05453)
* AgentNet: Decentralized Evolutionary Coordination for LLM-based Multi-Agent Systems ![NeurIPS](https://img.shields.io/badge/NeurIPS-blue) [![arXiv](https://img.shields.io/badge/arXiv-2504.00587-b31b1b.svg)](https://arxiv.org/abs/2504.00587)
* Intrinsic Memory Agents: Heterogeneous Multi-Agent LLM Systems through Structured Contextual Memory [![arXiv](https://img.shields.io/badge/arXiv-2508.08997-b31b1b.svg)](https://arxiv.org/abs/2508.08997)


<a name="mixed-memory"></a>
#####  Mixed Memory

* SRMT: Shared Memory for Multi-agent Lifelong Pathfinding [![arXiv](https://img.shields.io/badge/arXiv-2501.13200-b31b1b.svg)](https://arxiv.org/abs/2501.13200)
* Collaborative Memory: Multi-User Memory Sharing in LLM Agents with Dynamic Access Control [![arXiv](https://img.shields.io/badge/arXiv-2505.18279-b31b1b.svg)](https://arxiv.org/abs/2505.18279)
* LEGOMem: Modular Procedural Memory for Multi-agent LLM Systems for Workflow Automation [![arXiv](https://img.shields.io/badge/arXiv-2510.04851-b31b1b.svg)](https://arxiv.org/abs/2510.04851)

<a name="tool-learning"></a>
### 🛠️Tool Learning

![tool-learning](assets/tool-learning.png)

<a name="tool-selection"></a>
#### Tool Selection

<a name="external-retriever"></a>
#####  External Retriever

* ProTIP: Progressive Tool Retrieval Improves Planning [![arXiv](https://img.shields.io/badge/arXiv-2312.10332-b31b1b.svg)](https://arxiv.org/abs/2312.10332)

<a name="multi-label-classification-mlc"></a>
#####  Multi-Label Classification (MLC)

* TinyAgent: Function Calling at the Edge [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2024.emnlp-demo.9/) [![arXiv](https://img.shields.io/badge/arXiv-2409.00608-b31b1b.svg)](https://arxiv.org/abs/2409.00608)
* Efficient and Scalable Estimation of Tool Representations in Vector Space [![arXiv](https://img.shields.io/badge/arXiv-2409.02141-b31b1b.svg)](https://arxiv.org/abs/2409.02141)

<a name="vocabulary-based-retrieval"></a>
#####  Vocabulary-based Retrieval

* ToolkenGPT: Augmenting Frozen Language Models with Massive Tools via Tool Embeddings [![arXiv](https://img.shields.io/badge/arXiv-2305.11554-b31b1b.svg)](https://arxiv.org/abs/2305.11554)
* Concise and Precise Context Compression for Tool-Using Language Models [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2024.findings-acl.974/) [![arXiv](https://img.shields.io/badge/arXiv-2407.02043-b31b1b.svg)](https://arxiv.org/abs/2407.02043)
* ToolGen: Unified Tool Retrieval and Calling via Generation [![arXiv](https://img.shields.io/badge/arXiv-2410.03439-b31b1b.svg)](https://arxiv.org/abs/2410.03439)
* Toolken+: Improving LLM Tool Usage with Reranking and a Reject Option [![arXiv](https://img.shields.io/badge/arXiv-2410.12004-b31b1b.svg)](https://arxiv.org/abs/2410.12004)
* Chain-of-Tools: Utilizing Massive Unseen Tools in the CoT Reasoning of Frozen Language Models [![arXiv](https://img.shields.io/badge/arXiv-2503.16779-b31b1b.svg)](https://arxiv.org/abs/2503.16779)


<a name="tool-calling"></a>
#### Tool Calling

<a name="in-place-parameter-filling"></a>
#####  In-Place Parameter Filling

* Toolformer: Language Models Can Teach Themselves to Use Tools [![arXiv](https://img.shields.io/badge/arXiv-2302.04761-b31b1b.svg)](https://arxiv.org/abs/2302.04761)
* Efficient Tool Use with Chain-of-Abstraction Reasoning [![arXiv](https://img.shields.io/badge/arXiv-2401.17464-b31b1b.svg)](https://arxiv.org/abs/2401.17464)

<a name="parallel-tool-calling"></a>
#####  Parallel Tool Calling

* An LLM Compiler for Parallel Function Calling [![arXiv](https://img.shields.io/badge/arXiv-2312.04511-b31b1b.svg)](https://arxiv.org/abs/2312.04511)
* An LLM-Tool Compiler for Fused Parallel Function Calling [![arXiv](https://img.shields.io/badge/arXiv-2405.17438-b31b1b.svg)](https://arxiv.org/abs/2405.17438)
* CATP-LLM: Empowering Large Language Models for Cost-Aware Tool Planning [![arXiv](https://img.shields.io/badge/arXiv-2411.16313-b31b1b.svg)](https://arxiv.org/abs/2411.16313)

<a name="cost-aware-tool-calling"></a>
#####  Cost-Aware Tool Calling

* TroVE: Inducing Verifiable and Efficient Toolboxes for Solving Programmatic Tasks [![arXiv](https://img.shields.io/badge/arXiv-2401.12869-b31b1b.svg)](https://arxiv.org/abs/2401.12869)
* Budget-Constrained Tool Learning with Planning [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2024.findings-acl.536/) [![arXiv](https://img.shields.io/badge/arXiv-2402.15960-b31b1b.svg)](https://arxiv.org/abs/2402.15960)
* ToolCoder: A Systematic Code-Empowered Tool Learning Framework for Large Language Models [![arXiv](https://img.shields.io/badge/arXiv-2502.11404-b31b1b.svg)](https://arxiv.org/abs/2502.11404)
* Alignment for Efficient Tool Calling of Large Language Models [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2025.emnlp-main.898/) [![arXiv](https://img.shields.io/badge/arXiv-2503.06708-b31b1b.svg)](https://arxiv.org/abs/2503.06708)
* Distilling LLM Agent into Small Models with Retrieval and Code Tools [![arXiv](https://img.shields.io/badge/arXiv-2505.17612-b31b1b.svg)](https://arxiv.org/abs/2505.17612)
* A Joint Optimization Framework for Enhancing Efficiency of Tool Utilization in LLM Agents [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2025.findings-acl.1149/)




<a name="efficient-test-time-scaling"></a>
#####  Efficient Test-Time Scaling

* ToolChain\*: Efficient Action Space Navigation in Large Language Models with A\* Search [![arXiv](https://img.shields.io/badge/arXiv-2310.13227-b31b1b.svg)](https://arxiv.org/abs/2310.13227)
* ToolPlanner: A Tool Augmented LLM for Multi Granularity Instructions with Path Planning and Feedback [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2024.emnlp-main.1018/) [![arXiv](https://img.shields.io/badge/arXiv-2409.14826-b31b1b.svg)](https://arxiv.org/abs/2409.14826)


<a name="efficient-tool-calling-with-post-training"></a>
#####  Efficient Tool Calling with Post-training

* Acting Less is Reasoning More! Teaching Model to Act Efficiently [![arXiv](https://img.shields.io/badge/arXiv-2504.14870-b31b1b.svg)](https://arxiv.org/abs/2504.14870)
* ToolRM: Outcome Reward Models for Tool-Calling Large Language Models [![arXiv](https://img.shields.io/badge/arXiv-2509.11963-b31b1b.svg)](https://arxiv.org/abs/2509.11963)
* ToolOrchestra: Elevating Intelligence via Efficient Model and Tool Orchestration [![arXiv](https://img.shields.io/badge/arXiv-2511.21689-b31b1b.svg)](https://arxiv.org/abs/2511.21689)

<a name="tool-integrated-reasoning-tir"></a>
#### Tool-Integrated Reasoning (TIR)

<a name="selective-invocation"></a>
#####  Selective Invocation

* Agent-FLAN: Designing Data and Methods of Effective Agent Tuning for Large Language Models [![arXiv](https://img.shields.io/badge/arXiv-2403.12881-b31b1b.svg)](https://arxiv.org/abs/2403.12881)
* Sibyl: Simple yet Effective Agent Framework for Complex Real-world Reasoning [![arXiv](https://img.shields.io/badge/arXiv-2407.10718-b31b1b.svg)](https://arxiv.org/abs/2407.10718)
* SMART: Self-Aware Agent for Tool Overuse Mitigation [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2025.findings-acl.239/) [![arXiv](https://img.shields.io/badge/arXiv-2502.11435-b31b1b.svg)](https://arxiv.org/abs/2502.11435)
* TableMind: An Autonomous Programmatic Agent for Tool-Augmented Table Reasoning [![arXiv](https://img.shields.io/badge/arXiv-2509.06278-b31b1b.svg)](https://arxiv.org/abs/2509.06278)

<a name="cost-aware-policy-optimization"></a>
#####  Cost-Aware Policy Optimization

* Synthetic Data Generation & Multi-Step RL for Reasoning & Tool Use [![arXiv](https://img.shields.io/badge/arXiv-2504.04736-b31b1b.svg)](https://arxiv.org/abs/2504.04736)
* ReTool: Reinforcement Learning for Strategic Tool Use in LLMs [![arXiv](https://img.shields.io/badge/arXiv-2504.11536-b31b1b.svg)](https://arxiv.org/abs/2504.11536)
* ToolRL: Reward is All Tool Learning Needs [![arXiv](https://img.shields.io/badge/arXiv-2504.13958-b31b1b.svg)](https://arxiv.org/abs/2504.13958)
* Agentic Reasoning and Tool Integration for LLMs via Reinforcement Learning [![arXiv](https://img.shields.io/badge/arXiv-2505.01441-b31b1b.svg)](https://arxiv.org/abs/2505.01441)
* Reinforced Internal-External Knowledge Synergistic Reasoning for Efficient Adaptive Search Agent [![arXiv](https://img.shields.io/badge/arXiv-2505.07596-b31b1b.svg)](https://arxiv.org/abs/2505.07596)
* AutoTIR: Autonomous Tools Integrated Reasoning via Reinforcement Learning [![arXiv](https://img.shields.io/badge/arXiv-2507.21836-b31b1b.svg)](https://arxiv.org/abs/2507.21836)
* TableMind: An Autonomous Programmatic Agent for Tool-Augmented Table Reasoning [![arXiv](https://img.shields.io/badge/arXiv-2509.06278-b31b1b.svg)](https://arxiv.org/abs/2509.06278)
* A$^2$FM: An Adaptive Agent Foundation Model for Tool-Aware Hybrid Reasoning [![arXiv](https://img.shields.io/badge/arXiv-2510.12838-b31b1b.svg)](https://arxiv.org/abs/2510.12838)
* PORTool: Tool-Use LLM Training with Rewarded Tree [![arXiv](https://img.shields.io/badge/arXiv-2510.26020-b31b1b.svg)](https://arxiv.org/abs/2510.26020)

<a name="planning"></a>
### 🧩Planning

![planning](assets/planning.png)

<a name="single-agent-planning-efficiency"></a>
#### Single-Agent Planning Efficiency

<a name="adaptive-budgeting-and-control"></a>
#####  Adaptive Budgeting and Control

* Reflexion: Language Agents with Verbal Reinforcement Learning [![arXiv](https://img.shields.io/badge/arXiv-2303.11366-b31b1b.svg)](https://arxiv.org/abs/2303.11366)
* SwiftSage: A Generative Agent with Fast and Slow Thinking for Complex Interactive Tasks [![arXiv](https://img.shields.io/badge/arXiv-2305.17390-b31b1b.svg)](https://arxiv.org/abs/2305.17390)
* ReST meets ReAct: Self-Improvement for Multi-Step Reasoning LLM Agent [![arXiv](https://img.shields.io/badge/arXiv-2312.10003-b31b1b.svg)](https://arxiv.org/abs/2312.10003)
* Learning When to Plan: Efficiently Allocating Test-Time Compute for LLM Agents [![arXiv](https://img.shields.io/badge/arXiv-2509.03581-b31b1b.svg)](https://arxiv.org/abs/2509.03581)
* Budget-Aware Tool-Use Enables Effective Agent Scaling [![arXiv](https://img.shields.io/badge/arXiv-2511.17006-b31b1b.svg)](https://arxiv.org/abs/2511.17006)

<a name="structured-search-strategies"></a>
#####  Structured Search

* Language Agent Tree Search Unifies Reasoning Acting and Planning in Language Models [![arXiv](https://img.shields.io/badge/arXiv-2310.04406-b31b1b.svg)](https://arxiv.org/abs/2310.04406)
* ToolChain\*: Efficient Action Space Navigation in Large Language Models with A\* Search [![arXiv](https://img.shields.io/badge/arXiv-2310.13227-b31b1b.svg)](https://arxiv.org/abs/2310.13227)
* ProTIP: Progressive Tool Retrieval Improves Planning [![arXiv](https://img.shields.io/badge/arXiv-2312.10332-b31b1b.svg)](https://arxiv.org/abs/2312.10332)
* Cost-Augmented Monte Carlo Tree Search for LLM-Assisted Planning [![arXiv](https://img.shields.io/badge/arXiv-2505.14656-b31b1b.svg)](https://arxiv.org/abs/2505.14656)

<a name="task-decomposition-and-routing"></a>
#####  Task Decomposition

* HuggingGPT: Solving AI Tasks with ChatGPT and its Friends in Hugging Face [![arXiv](https://img.shields.io/badge/arXiv-2303.17580-b31b1b.svg)](https://arxiv.org/abs/2303.17580)
* ReWOO: Decoupling Reasoning from Observations for Efficient Augmented Language Models [![arXiv](https://img.shields.io/badge/arXiv-2305.18323-b31b1b.svg)](https://arxiv.org/abs/2305.18323)
* AutoGPT+P: Affordance-based Task Planning with Large Language Models [![arXiv](https://img.shields.io/badge/arXiv-2402.10778-b31b1b.svg)](https://arxiv.org/abs/2402.10778)
* BudgetMLAgent: A Cost-Effective LLM Multi-Agent system for Automating Machine Learning Tasks [![arXiv](https://img.shields.io/badge/arXiv-2411.07464-b31b1b.svg)](https://arxiv.org/abs/2411.07464)
* ReSo: A Reward-driven Self-organizing LLM-based Multi-Agent System for Reasoning Tasks [![arXiv](https://img.shields.io/badge/arXiv-2503.02390-b31b1b.svg)](https://arxiv.org/abs/2503.02390)
* Alita: Generalist Agent Enabling Scalable Agentic Reasoning with Minimal Predefinition and Maximal Self-Evolution [![arXiv](https://img.shields.io/badge/arXiv-2505.20286-b31b1b.svg)](https://arxiv.org/abs/2505.20286)

<a name="policy-optimization"></a>

#####  Policy Optimization

* Trial and Error: Exploration-Based Trajectory Optimization for LLM Agents [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2024.acl-long.409/) [![arXiv](https://img.shields.io/badge/arXiv-2403.02502-b31b1b.svg)](https://arxiv.org/abs/2403.02502)
* QLASS: Boosting Language Agent Inference via Q-Guided Stepwise Search [![arXiv](https://img.shields.io/badge/arXiv-2502.02584-b31b1b.svg)](https://arxiv.org/abs/2502.02584)
* Planning without Search: Refining Frontier LLMs with Offline Goal-Conditioned RL [![arXiv](https://img.shields.io/badge/arXiv-2505.18098-b31b1b.svg)](https://arxiv.org/abs/2505.18098)
* Encouraging Good Processes Without the Need for Good Answers: Reinforcement Learning for LLM Agent Planning [![arXiv](https://img.shields.io/badge/arXiv-2508.19598-b31b1b.svg)](https://arxiv.org/abs/2508.19598)
* Planner-R1: Reward Shaping Enables Efficient Agentic RL with Smaller LLMs [![arXiv](https://img.shields.io/badge/arXiv-2509.25779-b31b1b.svg)](https://arxiv.org/abs/2509.25779)

<a name="architectural-synergy-with-memory-and-tools"></a>
#####   Memory and Skill Acquisition

* Voyager: An Open-Ended Embodied Agent with Large Language Models [![arXiv](https://img.shields.io/badge/arXiv-2305.16291-b31b1b.svg)](https://arxiv.org/abs/2305.16291)
* Graph-enhanced Large Language Models in Asynchronous Plan Reasoning [![arXiv](https://img.shields.io/badge/arXiv-2402.02805-b31b1b.svg)](https://arxiv.org/abs/2402.02805)
* GraphReader: Building Graph-based Agent to Enhance Long-Context Abilities of Large Language Models [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2024.findings-emnlp.746/) [![arXiv](https://img.shields.io/badge/arXiv-2406.14550-b31b1b.svg)](https://arxiv.org/abs/2406.14550)
* Sibyl: Simple yet Effective Agent Framework for Complex Real-world Reasoning [![arXiv](https://img.shields.io/badge/arXiv-2407.10718-b31b1b.svg)](https://arxiv.org/abs/2407.10718)
* GAP: Graph-Based Agent Planning with Parallel Tool Use and Reinforcement Learning [![arXiv](https://img.shields.io/badge/arXiv-2510.25320-b31b1b.svg)](https://arxiv.org/abs/2510.25320)


<a name="multi-agent-collaborative-efficiency"></a>
#### Multi-Agent Collaborative Efficiency

<a name="topological-efficiency"></a>

#####  Topological Efficiency and Sparsification

* Chain of Agents: Large Language Models Collaborating on Long-Context Tasks ![NeurIPS](https://img.shields.io/badge/NeurIPS-blue) [![arXiv](https://img.shields.io/badge/arXiv-2406.02818-b31b1b.svg)](https://arxiv.org/abs/2406.02818)
* Scaling Large Language Model-based Multi-Agent Collaboration [![arXiv](https://img.shields.io/badge/arXiv-2406.07155-b31b1b.svg)](https://arxiv.org/abs/2406.07155)
* GroupDebate: Enhancing the Efficiency of Multi-Agent Debate Using Group Discussion [![arXiv](https://img.shields.io/badge/arXiv-2409.14051-b31b1b.svg)](https://arxiv.org/abs/2409.14051)
* Cut the Crap: An Economical Communication Pipeline for LLM-based Multi-Agent Systems [![arXiv](https://img.shields.io/badge/arXiv-2410.02506-b31b1b.svg)](https://arxiv.org/abs/2410.02506)
* S$^2$-MAD: Breaking the Token Barrier to Enhance Multi-Agent Debate Efficiency [![arXiv](https://img.shields.io/badge/arXiv-2502.04790-b31b1b.svg)](https://arxiv.org/abs/2502.04790)
* AgentDropout: Dynamic Agent Elimination for Token-Efficient and High-Performance LLM-Based Multi-Agent Collaboration [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2025.acl-long.1170/) [![arXiv](https://img.shields.io/badge/arXiv-2503.18891-b31b1b.svg)](https://arxiv.org/abs/2503.18891)
* SafeSieve: From Heuristics to Experience in Progressive Pruning for LLM-based Multi-Agent Communication [![arXiv](https://img.shields.io/badge/arXiv-2508.11733-b31b1b.svg)](https://arxiv.org/abs/2508.11733)
* MARS: toward more efficient multi-agent collaboration for LLM reasoning [![arXiv](https://img.shields.io/badge/arXiv-2509.20502-b31b1b.svg)](https://arxiv.org/abs/2509.20502)

<a name="protocol-and-context-optimization"></a>
#####  Protocol and Context Optimization

* Smurfs: Multi-Agent System using Context-Efficient DFSDT for Tool Planning [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2025.naacl-long.169/) [![arXiv](https://img.shields.io/badge/arXiv-2405.05955-b31b1b.svg)](https://arxiv.org/abs/2405.05955)
* CodeAgents: A Token-Efficient Framework for Codified Multi-Agent Reasoning in LLMs [![arXiv](https://img.shields.io/badge/arXiv-2507.03254-b31b1b.svg)](https://arxiv.org/abs/2507.03254)
* CONSENSAGENT: Towards Efficient and Effective Consensus in Multi-Agent LLM Interactions Through Sycophancy Mitigation [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2025.findings-acl.1141/)
* Free-MAD: Consensus-Free Multi-Agent Debate [![arXiv](https://img.shields.io/badge/arXiv-2509.11035-b31b1b.svg)](https://arxiv.org/abs/2509.11035)
* Stop Wasting Your Tokens: Towards Efficient Runtime Multi-Agent Systems [![arXiv](https://img.shields.io/badge/arXiv-2510.26585-b31b1b.svg)](https://arxiv.org/abs/2510.26585)

<a name="distilling-coordination-into-planning"></a>
#####  Distilling Coordination into Planning

* MAGDi: Structured Distillation of Multi-Agent Interaction Graphs Improves Reasoning in Smaller Language Models [![arXiv](https://img.shields.io/badge/arXiv-2402.01620-b31b1b.svg)](https://arxiv.org/abs/2402.01620)
* Debate, Reflect, and Distill: Multi-Agent Feedback with Tree-Structured Preference Optimization for Efficient Language Model Enhancement [![ACL Anthology](https://img.shields.io/badge/ACL%20Anthology-paper-blue)](https://aclanthology.org/2025.findings-acl.475/) [![arXiv](https://img.shields.io/badge/arXiv-2506.03541-b31b1b.svg)](https://arxiv.org/abs/2506.03541)
* SMAGDi: Socratic Multi Agent Interaction Graph Distillation for Efficient High Accuracy Reasoning [![arXiv](https://img.shields.io/badge/arXiv-2511.05528-b31b1b.svg)](https://arxiv.org/abs/2511.05528)

