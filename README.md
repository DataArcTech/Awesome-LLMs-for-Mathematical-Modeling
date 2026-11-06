# Awesome-LLMs-for-Mathematical-Modeling [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of systems, benchmarks, and datasets for **LLM-assisted mathematical modeling** — the task of turning an open-ended real-world problem into assumptions, variables, a formulation, executable computation, and a defensible modeling report. Unlike a well-posed math problem, a modeling problem has no fixed variables, no complete assumptions, and often more than one correct formulation.

This list focuses on work where the *artifact is a model or a modeling report*. Method-level work in operations research, differential equations, data science, and multi-criteria decision making is listed separately, because those literatures supply the technical substrate that a modeling workflow has to orchestrate.

## Contents

- [Projects](#projects) — end-to-end mathematical modeling agents
- [Benchmarks](#benchmarks) — modeling-level evaluation
- [Datasets](#datasets)
- [Optimization Modeling & Operations Research](#optimization-modeling--operations-research)
- [PDE & Scientific Computing Agents](#pde--scientific-computing-agents)
- [Data-Science Agents](#data-science-agents)
- [LLM + Multi-Criteria Decision Making](#llm--multi-criteria-decision-making)
- [Agent Skills & Harness](#agent-skills--harness)
- [Background](#background)

## Projects

| Date | Name | Author | Institute | Links | Published |
| :---: | :--- | :--- | :--- | :--- | :--- |
| 2026-11 | TB-MathModel: Terminal-style Mathematical Modeling Bench — The First Agentic and Verifiable Benchmark for Mathematical Modeling | Xiaojun Wu, Cehao Yang, et al. | IDEA Research, HKUST(GZ), DataArcTech | [![arXiv](https://img.shields.io/badge/Arxiv-2611.08237-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2611.08237) [![github](https://img.shields.io/github/stars/wxj630/terminal-bench-math-modeling.svg?style=social)](https://github.com/wxj630/terminal-bench-math-modeling) | arXiv 2026 |
| 2025-05 | MM-Agent: LLM as Agents for Real-World Mathematical Modeling Problem | Fan Liu, Zherui Yang, et al. | HKUST, et al. | [![arXiv](https://img.shields.io/badge/Arxiv-2505.14148-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2505.14148) [![github](https://img.shields.io/github/stars/usail-hkust/LLM-MM-Agent.svg?style=social)](https://github.com/usail-hkust/LLM-MM-Agent) | NeurIPS 2025 |
| 2025-05 | ModelingAgent: Bridging LLMs and Mathematical Modeling for Real-World Challenges | Cheng Qian, Hongyi Du, et al. | UIUC, et al. | [![arXiv](https://img.shields.io/badge/Arxiv-2505.15068-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2505.15068) [![github](https://img.shields.io/github/stars/qiancheng0/ModelingAgent.svg?style=social)](https://github.com/qiancheng0/ModelingAgent) | EMNLP (Findings) 2025 |
| 2025-01 | MathModelAgent | Jihe | - | [![github](https://img.shields.io/github/stars/jihe520/MathModelAgent.svg?style=social)](https://github.com/jihe520/MathModelAgent) | Code Release |
| 2024-05 | Mamo: LLMs for Mathematical Modeling: Towards Bridging the Gap between Natural and Mathematical Languages | Xuhan Huang, Qingning Shen, et al. | CUHK(Shenzhen), et al. | [![arXiv](https://img.shields.io/badge/Arxiv-2405.13144-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2405.13144) [![github](https://img.shields.io/github/stars/FreedomIntelligence/Mamo.svg?style=social)](https://github.com/FreedomIntelligence/Mamo) | NAACL (Findings) 2025 |
| Coming Soon | LightningMathModel: Boosting Lightweight LLMs for Mathematical Modeling via Specialized Knowledge Training and Integration | Coming Soon | Coming Soon | [![github](https://img.shields.io/github/stars/wxj630/Math-Modeling-World-Agent.svg?style=social)](https://github.com/wxj630/Math-Modeling-World-Agent) [![huggingface](https://img.shields.io/badge/🤗-Model%208B-yellow.svg)](https://huggingface.co/IDEA-FinAI/LightningMathModel-8B-v0.1) | |

## Benchmarks

Modeling-level benchmarks score the modeling *process* rather than a final answer. They differ mainly in where the signal comes from: a solver, an expert-style rubric, or both.

| Name | Paper / Project | Description |
| :--- | :--- | :--- |
| **MMBench** | [MM-Agent](https://github.com/usail-hkust/LLM-MM-Agent) | 111 real-world modeling problems from MCM/ICM contests (2000–2025) across 10 domains and 8 task types, with contextual components such as background, requirements, dataset paths, and variable descriptions. Scored on Analysis Evaluation, Modeling Rigorousness, Practicality and Scientificity, and Result and Bias Analysis. |
| **ModelingBench** | [ModelingAgent](https://github.com/qiancheng0/ModelingAgent) | 68 curated problems retained from modeling competitions, spanning 70+ domains and averaging 7.31 subtasks each. Reports are scored by ModelingJudge, which simulates multiple expert roles across structural coherence, solution completeness, modeling/data/analysis groundedness, and innovativeness. |
| **Mamo** | [Mamo](https://github.com/FreedomIntelligence/Mamo) | 1,209 curated questions covering ODEs and optimization (LP/MILP). Models must emit solver-consumable artifacts — Python code for ODEs, `.lp` files for optimization — so that modeling errors can be separated from syntax and formatting errors. |
| **TB-MathModel** | [TB-MathModel](https://arxiv.org/abs/2611.08237) | 18 real CUMCM and MCM problems (2023–2025) delivered as containerized terminal tasks: the agent gets the verbatim statement, official attachments, and figures, and returns one JSON artifact. Scored on the numeric core of the final question against a *panel* of Outstanding-award papers, direction-aware and one-sided (beating the anchor is never penalised), with a two-layer feasibility gate — six decidable invariant forms plus 624 Lean 4 obligations — that zeroes infeasible answers. |

## Datasets

| Name | Paper / Project | Links | Description |
| :--- | :--- | :--- | :--- |
| **Mathematical_Modeling_Speciale_Dataset_v0.1** | LightningMathModel (IDEA Research) | [![huggingface](https://img.shields.io/badge/🤗-Dataset-yellow.svg)](https://huggingface.co/datasets/IDEA-FinAI/Mathematical_Modeling_Speciale_Dataset_v0.1) | A specialized dataset for training and evaluating LLMs on mathematical modeling tasks, focusing on domain knowledge integration. |
| **OptMATH-Train** | [OptMATH](https://arxiv.org/abs/2502.11102) | [![huggingface](https://img.shields.io/badge/🤗-Dataset-yellow.svg)](https://huggingface.co/datasets/Aurora-Gem/OptMATH-Train) | Bidirectionally synthesized (natural language ⇄ optimization model) training data for optimization modeling, generated by a scalable two-stage framework. |

## Optimization Modeling & Operations Research

OR is the most mature corner of the field: the output is a formulation plus solver code, so feasibility, optimality, and objective values give an unusually strong external check — on the *formulation*, not on whether the formulation captures the real problem.

| Date | Name | Venue | Links | What it contributes |
| :---: | :--- | :--- | :--- | :--- |
| 2026-04 | AutoOR: Scalably Post-training LLMs to Autoformalize Operations Research Problems | Preprint | [![arXiv](https://img.shields.io/badge/Arxiv-2604.16804-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2604.16804) | Scalable post-training with solver-verifiable rewards for autoformalizing OR problems. |
| 2025-11 | OR-R1: Automating Modeling and Solving of Operations Research Optimization Problem via Test-Time Reinforcement Learning | AAAI 2026 | [![arXiv](https://img.shields.io/badge/Arxiv-2511.09092-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2511.09092) | Test-time reinforcement learning for OR modeling, using solver-checkable outcomes as the reward signal. |
| 2025-10 | SolverLLM: Leveraging Test-Time Scaling for Optimization Problem via LLM-Guided Search | NeurIPS 2025 | [![arXiv](https://img.shields.io/badge/Arxiv-2510.16916-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2510.16916) | Test-time scaling for optimization modeling: search guided by solver feedback rather than by a single sampled formulation. |
| 2025-08 | A Survey of Optimization Modeling Meets LLMs: Progress and Future Directions | Preprint | [![arXiv](https://img.shields.io/badge/Arxiv-2508.10047-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2508.10047) | Survey of the optimization-modeling-with-LLMs literature: formulation pipelines, data synthesis, training, and open problems. |
| 2025-08 | Toward a Trustworthy Optimization Modeling Agent via Verifiable Synthetic Data Generation | Preprint | [![arXiv](https://img.shields.io/badge/Arxiv-2508.03117-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2508.03117) | Verifiable synthetic data generation pipeline aimed at trustworthy optimization modeling agents. |
| 2025-06 | Step-Opt: Boosting Optimization Modeling in LLMs through Iterative Data Synthesis and Structured Validation | Preprint | [![arXiv](https://img.shields.io/badge/Arxiv-2506.17637-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2506.17637) | Iterative data synthesis with step-level structured validation, so that difficulty increases only where the model has been verified. |
| 2025-03 | OR-LLM-Agent: Automating Modeling and Solving of Operations Research Optimization Problems with Reasoning LLM | Preprint | [![arXiv](https://img.shields.io/badge/Arxiv-2503.10009-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2503.10009) | End-to-end agent on top of a reasoning LLM, with decomposition into problem identification, formulation, code generation, and solver execution. |
| 2025-02 | OptMATH: A Scalable Bidirectional Data Synthesis Framework for Optimization Modeling | Preprint | [![arXiv](https://img.shields.io/badge/Arxiv-2502.11102-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2502.11102) [![github](https://img.shields.io/github/stars/optsuite/OptMATH.svg?style=social)](https://github.com/optsuite/OptMATH) | Bidirectional (natural language ⇄ model) data synthesis that scales training data while keeping the two directions consistent. |
| 2024-12 | Evaluating LLM Reasoning in the Operations Research Domain with ORQA | AAAI 2025 | [![arXiv](https://img.shields.io/badge/Arxiv-2412.17874-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2412.17874) [![github](https://img.shields.io/github/stars/nl4opt/ORQA.svg?style=social)](https://github.com/nl4opt/ORQA) | QA-style OR benchmark that isolates domain reasoning from formulation and solver execution. |
| 2024-11 | Autoformulation of Mathematical Optimization Models Using LLMs | ICML 2025 | [![arXiv](https://img.shields.io/badge/Arxiv-2411.01679-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2411.01679) | Trains autoformulation with a constraint-consistency verifier, so that generated models can be checked without a full reference solution. |
| 2024-10 | LLMOPT: Learning to Define and Solve General Optimization Problems from Scratch | Preprint | [![arXiv](https://img.shields.io/badge/Arxiv-2410.13213-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2410.13213) [![github](https://img.shields.io/github/stars/antgroup/LLMOPT.svg?style=social)](https://github.com/antgroup/LLMOPT) | Unified five-element formulation schema plus a learn-to-define-and-solve training recipe for general optimization problems. |
| 2024-07 | OptiBench Meets ReSocratic: Measure and Improve LLMs for Optimization Modeling | ICLR 2025 | [![arXiv](https://img.shields.io/badge/Arxiv-2407.09887-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2407.09887) [![github](https://img.shields.io/github/stars/yangzhch6/PRIVATE-RS.svg?style=social)](https://github.com/yangzhch6/PRIVATE-RS) | Benchmark with equivalence-based answer detection, plus ReSocratic reverse-construction data synthesis that starts from the model and asks for the problem. |
| 2024-05 | ORLM: A Customizable Framework in Training Large Models for Automated Optimization Modeling | Operations Research 2025 | [![arXiv](https://img.shields.io/badge/Arxiv-2405.17743-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2405.17743) [![github](https://img.shields.io/github/stars/Cardinal-Operations/ORLM.svg?style=social)](https://github.com/Cardinal-Operations/ORLM) | Training framework plus OR-Instruct data synthesis; shows that optimization-modeling ability can be trained rather than only prompted. |
| 2024-05 | Chain-of-Experts: When LLMs Meet Complex Operations Research Problems | ICLR 2024 | [![OpenReview](https://img.shields.io/badge/OpenReview-Forum-blue)](https://openreview.net/forum?id=HobyL1B9CZ) [![github](https://img.shields.io/github/stars/xzymustbexzy/Chain-of-Experts.svg?style=social)](https://github.com/xzymustbexzy/Chain-of-Experts) | Multi-expert decomposition (SoE/CoE) for complex OR problems, where a single prompt fails to cover formulation, modelling, and coding jointly. |
| 2024-02 | OptiMUS: Scalable Optimization Modeling with (MI)LP Solvers and Large Language Models | ICML 2024 | [![arXiv](https://img.shields.io/badge/Arxiv-2402.10172-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2402.10172) | LLM agent that formulates and solves MILPs from natural language using modular code generation, debugging loops, and self-written tests. |
| 2023-03 | NL4Opt Competition: Formulating Optimization Problems Based on Their Natural Language Descriptions | NeurIPS 2022 Competition Track | [![arXiv](https://img.shields.io/badge/Arxiv-2303.08233-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2303.08233) [![github](https://img.shields.io/github/stars/nl4opt/nl4opt-competition.svg?style=social)](https://github.com/nl4opt/nl4opt-competition) | First shared task for natural-language → optimization formulation, with problem/entity extraction and LP/MILP formulation subtasks. |

## PDE & Scientific Computing Agents

Differential equations are the other major modeling family. These works move from solving a given equation toward *generating the solver*, which makes numerical choices — stiffness, discretization, tolerances, boundary conditions — part of the task.

| Date | Name | Venue | Links | What it contributes |
| :---: | :--- | :--- | :--- | :--- |
| 2026-02 | OpInf-LLM: Parametric PDE Solving with LLMs via Operator Inference | Preprint | [![arXiv](https://img.shields.io/badge/Arxiv-2602.01493-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2602.01493) | Connects language-driven PDE specification with operator inference for parametric PDE families. |
| 2025-09 | SciML Agents: Write the Solver, Not the Solution | NeurIPS 2025 Math-AI Workshop | [![arXiv](https://img.shields.io/badge/Arxiv-2509.09936-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2509.09936) | Asks models to produce solver code rather than answers, emphasizing domain-aware numerical choices. |
| 2025-05 | CodePDE: An Inference Framework for LLM-Driven PDE Solver Generation | TMLR | [![arXiv](https://img.shields.io/badge/Arxiv-2505.08783-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2505.08783) [![github](https://img.shields.io/github/stars/LithiumDA/CodePDE.svg?style=social)](https://github.com/LithiumDA/CodePDE) | Inference framework for generating executable PDE solvers, with test-time scaling over generated code and numerical feedback. |
| 2025-02 | PDE-Controller: LLMs for Autoformalization and Reasoning of PDEs | ICML 2025 | [![arXiv](https://img.shields.io/badge/Arxiv-2502.00963-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2502.00963) [![github](https://img.shields.io/github/stars/delta-lab-ai/pde-controller.svg?style=social)](https://github.com/delta-lab-ai/pde-controller) | Autoformalization and reasoning over PDEs, including control-oriented tasks that require physical reasoning beyond symbolic manipulation. |
| 2024-10 | Text2PDE: Latent Diffusion Models for Accessible Physics Simulation | Preprint | [![arXiv](https://img.shields.io/badge/Arxiv-2410.01153-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2410.01153) | Treats natural-language access to physics simulation as a generative interface problem. |
| 2024-07 | MetaOpenFOAM: An LLM-Based Multi-Agent Framework for CFD | Preprint | [![arXiv](https://img.shields.io/badge/Arxiv-2407.21320-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2407.21320) | Multi-agent automation of CFD case setup and simulation, a domain where configuration errors dominate failures. |
| 2024-04 | LLM-SR: Scientific Equation Discovery via Programming with Large Language Models | ICLR 2025 (Oral) | [![arXiv](https://img.shields.io/badge/Arxiv-2404.18400-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2404.18400) | Equation discovery framed as program search, with the LLM proposing and refining candidate expressions. |

## Data-Science Agents

Data science supplies the evidence half of the modeling toolbox. The boundary matters: a data-science task usually starts from a dataset and asks for an analysis, while a modeling task may have little or no data and must first choose an abstraction.

| Date | Name | Venue | Links | What it contributes |
| :---: | :--- | :--- | :--- | :--- |
| 2024-12 | A Survey on Large Language Model-Based Agents for Statistics and Data Science | The American Statistician 2025 | [![arXiv](https://img.shields.io/badge/Arxiv-2412.14222-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2412.14222) | Organizes data agents by capability — instruction understanding, planning, tool interaction, and analysis delivery. |
| 2024-10 | MLE-bench: Evaluating Machine Learning Agents on Machine Learning Engineering | ICLR 2025 | [![arXiv](https://img.shields.io/badge/Arxiv-2410.07095-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2410.07095) [![github](https://img.shields.io/github/stars/openai/mle-bench.svg?style=social)](https://github.com/openai/mle-bench) | 75 Kaggle competitions graded against human medal thresholds; the standard yardstick for ML-engineering agents. |
| 2024-10 | AutoKaggle: A Multi-Agent Framework for Autonomous Data Science Competitions | Preprint | [![arXiv](https://img.shields.io/badge/Arxiv-2410.20424-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2410.20424) [![github](https://img.shields.io/github/stars/multimodal-art-projection/AutoKaggle.svg?style=social)](https://github.com/multimodal-art-projection/AutoKaggle) | Multi-agent Kaggle workflow — read data, plan, implement, evaluate, iterate — with development and unit-test validation stages. |
| 2024-07 | LAMBDA: A Large Model Based Data Agent | JASA 2025 | [![arXiv](https://img.shields.io/badge/Arxiv-2407.17535-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2407.17535) [![github](https://img.shields.io/github/stars/AMA-CMFAI/LAMBDA.svg?style=social)](https://github.com/AMA-CMFAI/LAMBDA) | Code-first data agent with planning, code execution, and iterative refinement over tabular analysis tasks. |
| 2024-02 | MatPlotAgent: Method and Evaluation for LLM-Based Agentic Scientific Data Visualization | Preprint | [![arXiv](https://img.shields.io/badge/Arxiv-2402.11453-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2402.11453) [![github](https://img.shields.io/github/stars/thunlp/MatPlotAgent.svg?style=social)](https://github.com/thunlp/MatPlotAgent) | Treats visualization as an agentic task with query understanding, code generation, and visual self-debugging. |
| 2024-02 | DS-Agent: Automated Data Science by Empowering Large Language Models with Case-Based Reasoning | ICML 2024 | [![arXiv](https://img.shields.io/badge/Arxiv-2402.17453-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2402.17453) [![github](https://img.shields.io/github/stars/guosyjlu/DS-Agent.svg?style=social)](https://github.com/guosyjlu/DS-Agent) | Case-based reasoning over a library of past solutions, with iterative development after each attempt. |

## LLM + Multi-Criteria Decision Making

MCDM is often the bridge from computation to recommendation: forecasts, optimized designs, or simulations still have to be compared across cost, risk, robustness, equity, and feasibility. LLMs enter either as weight/criteria proposers or as judges — both of which can hide value judgments inside fluent prose.

| Date | Name | Venue | Links | What it contributes |
| :---: | :--- | :--- | :--- | :--- |
| 2025-05 | Enhancing Analytic Hierarchy Process Modelling Under Uncertainty With Fine-Tuning LLM | Expert Systems 2025 | [![DOI](https://img.shields.io/badge/DOI-10.1111%2Fexsy.70051-blue)](https://doi.org/10.1111/exsy.70051) | Fine-tunes an LLM for AHP under uncertainty, targeting consistency of judgement matrices. |
| 2025-02 | One for All: A General Framework of LLMs-Based Multi-Criteria Decision Making on Human Expert Level | Preprint | [![arXiv](https://img.shields.io/badge/Arxiv-2502.15778-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2502.15778) | General LLM-MCDM framework across supplier evaluation, customer satisfaction, and air-quality assessment; prompting helps, fine-tuning is needed for expert level. |
| 2024-11 | From Generation to Judgment: Opportunities and Challenges of LLM-as-a-Judge | EMNLP 2025 | [![arXiv](https://img.shields.io/badge/Arxiv-2411.16594-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2411.16594) | Survey of LLM-as-a-judge: what is judged, how judges are built, and where bias and inconsistency enter. |
| 2024-06 | Can LLM Be a Personalized Judge? | Preprint | [![arXiv](https://img.shields.io/badge/Arxiv-2406.11657-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2406.11657) | Measures how reliably LLM judges track individual rater preferences, and where they fall back to population averages. |
| 2024-04 | Can ChatGPT Serve as a Multi-Criteria Decision Maker? A Novel Approach to Supplier Evaluation | ICASSP 2024 | [![DOI](https://img.shields.io/badge/DOI-10.1109%2FICASSP48485.2024.10447204-blue)](https://doi.org/10.1109/ICASSP48485.2024.10447204) | Tests whether an LLM can act directly as a multi-criteria decision maker on supplier evaluation. |
| 2024-02 | Enhancing Multi-Criteria Decision Analysis with AI: Integrating Analytic Hierarchy Process and GPT-4 for Automated Decision Support | Preprint | [![arXiv](https://img.shields.io/badge/Arxiv-2402.07404-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2402.07404) | Uses GPT-4 to construct AHP hierarchies and pairwise comparisons, automating the structuring step of MCDA. |

## Agent Skills & Harness

As modeling systems mature, more of the capability lives outside the weights: reusable skills, retrieval, tool protocols, and the harness that sequences them. This line is directly relevant to *what should be trained, what retrieved, and what verified*.

| Date | Name | Venue | Links | What it contributes |
| :---: | :--- | :--- | :--- | :--- |
| 2026-04 | Externalization in LLM Agents: A Unified Review of Memory, Skills, Protocols and Harness Engineering | Preprint | [![arXiv](https://img.shields.io/badge/Arxiv-2604.08224-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2604.08224) | Unified review arguing that memory, skills, protocols, and harness structure are becoming the main locus of agent capability. |
| 2026-02 | SkillsBench: Benchmarking How Well Agent Skills Work Across Diverse Tasks | Preprint | [![arXiv](https://img.shields.io/badge/Arxiv-2602.12670-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2602.12670) [![github](https://img.shields.io/github/stars/benchflow-ai/skillsbench.svg?style=social)](https://github.com/benchflow-ai/skillsbench) | Measures how much curated skills actually help across task suites — the empirical check on the skills hypothesis. |
| 2025 | Equipping Agents for the Real World with Agent Skills | Anthropic | [![Web](https://img.shields.io/badge/Web-Blog-blue)](https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills) | Packages procedural knowledge as loadable skills, separating reusable know-how from the model and the prompt. |
| 2024-11 | Introducing the Model Context Protocol | Anthropic | [![Web](https://img.shields.io/badge/Web-Blog-blue)](https://www.anthropic.com/news/model-context-protocol) | Standard protocol for exposing tools and data to agents, now the common substrate for tool-equipped harnesses. |
| 2023-05 | Voyager: An Open-Ended Embodied Agent with Large Language Models | Preprint | [![arXiv](https://img.shields.io/badge/Arxiv-2305.16291-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2305.16291) | Early demonstration of a growing library of reusable, self-written skills as agent memory. |

## Background

Backbone references for the reasoning, tool-use, and benchmark lineage that modeling work builds on.

| Date | Name | Venue | Links | What it contributes |
| :---: | :--- | :--- | :--- | :--- |
| 2023-02 | Toolformer: Language Models Can Teach Themselves to Use Tools | NeurIPS 2023 | [![arXiv](https://img.shields.io/badge/Arxiv-2302.04761-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2302.04761) | Self-supervised learning of when and how to call external APIs. |
| 2022-10 | ReAct: Synergizing Reasoning and Acting in Language Models | ICLR 2023 | [![arXiv](https://img.shields.io/badge/Arxiv-2210.03629-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2210.03629) | Interleaves reasoning traces with tool actions — the loop that solver-aided modeling agents extend. |
| 2022-01 | Chain-of-Thought Prompting Elicits Reasoning in Large Language Models | NeurIPS 2022 | [![arXiv](https://img.shields.io/badge/Arxiv-2201.11903-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2201.11903) | Establishes explicit intermediate reasoning as a lever on multi-step problem solving. |
| 2021-10 | Training Verifiers to Solve Math Word Problems (GSM8K) | Preprint | [![arXiv](https://img.shields.io/badge/Arxiv-2110.14168-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2110.14168) | Grade-school word problems: the canonical answer-accuracy benchmark that modeling work departs from. |
| 2021-03 | Measuring Mathematical Problem Solving With the MATH Dataset | NeurIPS 2021 | [![arXiv](https://img.shields.io/badge/Arxiv-2103.03874-b31b1b.svg?logo=arXiv)](https://arxiv.org/abs/2103.03874) | Competition-style symbolic problems with step-by-step solutions; fixed problem, fixed answer. |

## Contributing

Pull requests are welcome. To keep the list useful:

- Add work where the artifact is a **model, a formulation, or a modeling report** to the main tables; method-level work belongs in the related sections.
- Include a working link — arXiv abstract page, DOI, or repository — and state the venue only if it is confirmed.
- Put new entries in date order within their section, and one entry per paper (no duplicates under different titles).

## Citation

If you find this list useful, please cite the papers listed above. The list itself can be referenced as:

```bibtex
@misc{awesome-llms-mathematical-modeling,
  title  = {Awesome-LLMs-for-Mathematical-Modeling},
  author = {DataArcTech},
  year   = {2025},
  url    = {https://github.com/DataArcTech/Awesome-LLMs-for-Mathematical-Modeling}
}
```
