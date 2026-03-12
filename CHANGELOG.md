# Changelog

All notable changes to this project will be documented in this file.

---

## [1.0.0] - 2026-03-12

### Initial release

First complete version of the LLM Agents Survey website, compiled March 2026.

#### Site structure
- 8-page Quarto website published to GitHub Pages
- Light/dark theme (Flatly/Darkly), responsive layout, table of contents on all pages

#### Pages added
- **Home** (`index.qmd`) — Overview, stats bar, navigation card grid
- **Taxonomy** (`taxonomy.qmd`) — Conceptual framework: 5 design dimensions (reasoning, memory, action space, multiplicity, autonomy), 7 architectural families, key design tensions, field evolution timeline
- **Foundations 2022–2023** (`foundations.qmd`) — Major survey papers (Wang et al., Xi et al., Luo et al.), foundational papers: ReAct, Chain-of-Thought, Toolformer, MRKL, WebGPT, HuggingGPT/JARVIS, SayCan, Voyager, AutoGPT, BabyAGI; standard agent decomposition table; 2021–2023 milestone timeline
- **Reasoning & Planning** (`reasoning.qmd`) — CoT family (Wei, Kojima, Wang), structured reasoning (ToT, GoT, Algorithm of Thoughts), planning architectures (LLM+P, Plan-and-Execute, RAP, DEPS, Inner Monologue, ADaPT, Step-Back), reflection (Reflexion, Self-Refine, CRITIC), search-based planning (MCTS, Large Language Monkeys), reasoning models (o1/o3, DeepSeek-R1, s1); benchmarks table; reasoning paradigm taxonomy
- **Multi-Agent Systems** (`multiagent.qmd`) — Foundational papers: CAMEL, Generative Agents, MetaGPT, ChatDev, AutoGen, AgentVerse, DyLAN, SPP, AgentScope; open-source frameworks: LangChain, LangGraph, AutoGen, CrewAI, DSPy, Semantic Kernel, Haystack, OpenAI Swarm; orchestration patterns; MCP protocol; evaluation benchmarks: AgentBench, WebArena, GAIA, OSWorld, ST-WebAgentBench; timeline
- **Memory, Tools & Actions** (`memory-tools.qmd`) — Memory taxonomy (working/episodic/semantic/procedural); MemGPT, Generative Agents memory, ReadAgent, Cognitive Architectures, ENGRAM; tool use: Toolformer, OpenAI function calling, Gorilla, ToolLLM, HuggingGPT, AnyTool, CodeAct, Tool Makers; action spaces: web browsing (WebGPT, Mind2Web, WebArena, WebAgent), GUI/computer use (CogAgent, AppAgent, UFO, OS-Copilot, OSWorld, Anthropic Computer Use), code execution (OpenHands, SWE-agent, Aider), embodied (SayCan, PaLM-E, RT-2); RAG (Self-RAG, agentic patterns); timeline
- **2024–2026 Frontier** (`recent.qmd`) — SWE-bench progress table (12% → 77%); coding agents: SWE-agent, OpenHands, Devin, Claude Code/Agent SDK, GitHub Copilot Agent, Aider; major products: OpenAI Operator + Deep Research + ChatGPT Agent, Anthropic Computer Use, Manus AI (→ Meta), Google ADK; protocols: MCP (Anthropic, Nov 2024), A2A (Google, Apr 2025 → Linux Foundation); framework consolidation: Microsoft Agent Framework (AutoGen + Semantic Kernel), LangGraph v1.0, Goose; browser/computer-use ecosystem: browser-use (78k stars), Skyvern, Stagehand; key blog posts: Anthropic "Building Effective Agents," Google Cloud "Lessons from 2025," applied-llms.org; 2025 arXiv surveys; agent safety (prompt injection, AgentDojo, AgentHarm, reversibility); 2024–2026 timeline; open questions
- **Resources** (`resources.qmd`) — Curated entry points, key papers by category with arXiv links, framework GitHub table, influential blog posts, benchmarks, courses & tutorials

#### Coverage
- Time range: 2022 – March 2026
- ~200+ papers, blog posts, repos, and tools referenced
- Academic papers, preprints, practitioner blog posts, GitHub repos, benchmarks, products, and protocols

#### Research methodology
- 5 parallel research sub-agents (Claude Haiku) gathered primary material across 5 domains
- Additional targeted web search for 2025–2026 material (blogs, repos, products, protocols)
- Manual synthesis and editorial pass by John P. Lake
