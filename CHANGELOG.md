# Changelog

All notable changes to this project will be documented in this file.

---

## [1.0.5] - 2026-03-12 — Accuracy audit

Comprehensive fact-check of all 14 pages using parallel sub-agents + manual verification. All factual claims verified against primary sources (arXiv, official docs, leaderboards).

### Corrections

**Benchmark scores (multiple pages):**
- GAIA GPT-4+plugins score: `~30%` → `~15%` (published paper: arxiv.org/abs/2311.12983)
- WebArena site count: `4 functional websites` → `5 websites + Wikipedia` (e-commerce, Reddit, GitLab, CMS, map)
- OSWorld: Removed incorrect claim that agents scored `~72.5%` in late 2024 — `72.36%` is the human baseline; agents reached ~76%+ only in 2025
- SWE-bench progress table: Clarified which benchmark variant (Full/Lite/Verified) applies to each score; Devin's 13.86% on SWE-bench Lite → `~14%` (previously mislabeled as Verified); SWE-agent's 12.47% on Full (not Verified)
- Claude Sonnet 4.5 SWE-bench: `~55%` → `77.2%` (82.0% with parallel compute); confirmed from multiple sources
- BixBench year: `2024` → `2025` (released March 2025 by FutureHouse + ScienceMachine)
- WebGPT date: `2022` → `2021` (arXiv:2112.09332 submitted December 2021; citation year in literature is 2021)
- DeepSeek-R1 date: `Dec 2024` → `Jan 2025` (arXiv:2501.12948 submitted January 22, 2025)

**Reflexion (reasoning.qmd + timeline.qmd):**
- HumanEval baseline: `67%→91%` → `80%→91%`; the published NeurIPS paper states GPT-4 baseline is 80%, Reflexion achieves 91%

**Step-Back Prompting (reasoning.qmd + timeline.qmd):**
- Removed fabricated `+42.8% on multi-hop QA` claim; replaced with actual paper results: +7% MMLU Physics, +11% Chemistry, +27% TimeQA, +7% MuSiQue (PaLM-2L)

**Foundations and surveys:**
- Xi et al. author count: `30` → `29` co-authors (verified via arXiv + GitHub BibTeX)
- AutoGPT attribution: `Riedl et al. (community)` → `Toran Bruce Richards (Significant Gravitas)` — Marcus Riedl is an unrelated GT professor
- Agent AI survey arXiv:2401.03568: `Wang et al.` → `Durante et al.` (first author: Zane Durante, Stanford)
- Voyager results: `3× faster at milestones` → `3.3× more unique items collected, 2.3× longer distances`
- Llama 3.1 context window: `400k` → `128k` (Meta's official figure)

**Multi-agent page:**
- MetaGPT title: `"Meta Programming for a Generalizable Agent System"` → `"Meta Programming for A Multi-Agent Collaborative Framework"` (actual paper title)
- TapeAgents: removed erroneous `Cohere` attribution — ServiceNow only
- CrewAI GitHub: updated repo from `joaomdmoura/crewAI` → `crewAIInc/crewAI` (org moved); star count updated to 40k+
- GAIA score: `~30%` → `~15%` (corrected in multiagent.qmd as well)

**Science agents page:**
- CISPO description: was `"combining elements of GRPO with stability constraints"` — actually Clipped Importance Sampling Policy Optimization, which clips importance sampling weights (not token updates like PPO/GRPO); distinct algorithm from GRPO
- SkyDiscover URL: `sky.cs.berkeley.edu/project/skydiscover` → `skydiscover-ai.github.io` (actual project URL; old link 404s)

**Gartner (safety.qmd):**
- Date: `(2024)` → `(2025)` (Gartner prediction published June 2025)

**InjecAgent (safety.qmd):**
- Changed "30+ attack patterns" → "30 LLM-based agents across 17 user tools and 62 attacker tools" (accurate to the benchmark structure)

---

## [1.0.4] - 2026-03-12

### Structural reorganization

**New pages (4):**
- `timeline.qmd` — Single consolidated field timeline covering 2021–2026, replacing the three separate timelines that were scattered across foundations.qmd, multiagent.qmd, memory-tools.qmd, and recent.qmd
- `topics.qmd` — Hub page for cross-cutting themes with navigation cards to sub-pages
- `evaluation.qmd` — Dedicated Evaluation & Benchmarks page: coding benchmarks (SWE-bench, HumanEval, Aider leaderboard), web/computer use (WebArena, OSWorld, Mind2Web), general capability (GAIA, AgentBench, tau-bench), METR time horizons, science benchmarks (PaperBench, LabBench), safety benchmarks (AgentDojo, InjecAgent, AgentHarm), and the benchmark lifecycle problem
- `safety.qmd` — Dedicated Safety & Alignment page: prompt injection / IPI, privilege escalation, tool misuse, unintended side effects; safety principles (reversibility, minimal footprint, HIL checkpoints, sandboxing, tool discipline); MIT AI Agent Index findings; Constitutional AI; agent-specific alignment challenges; web conduct gaps; safety benchmarks table; research agenda

**Navbar restructure:**
- Added `timeline.qmd` as top-level nav item
- "Core Areas" dropdown: Foundations, Reasoning & Planning, Multi-Agent Systems, Memory/Tools & Actions
- "Topics" dropdown: Topics Overview, Evaluation & Benchmarks, Safety & Alignment, Science & Research Agents
- Reduced top-level nav clutter from 10 flat items to 7 items (2 with dropdowns)

**Existing pages updated:**
- `foundations.qmd` — Timeline replaced with "see Timeline →" link
- `multiagent.qmd` — Timeline replaced with "see Timeline →" link
- `memory-tools.qmd` — Timeline replaced with "see Timeline →" link
- `recent.qmd` — Timeline replaced with "see Timeline →" link; Safety section replaced with callout box pointing to safety.qmd
- `resources.qmd` — Blog posts section substantially expanded: added Saurabh Alone Hitchhiker's Guide, Leonie Monigatti on memory, Anthropic multi-agent system engineering, Devin Agents 101, Martin Fowler CLI coding agent, 47 Billion production guide, Google Cloud lessons from 2025, Strix series (3 posts), emsh.cat browser build, OpenAI Harness Engineering; organized into three sub-categories (Introductions, Production guides, Builder diaries)
- `index.qmd` — Homepage cards updated to reflect new Topics page instead of standalone Science Agents card

---

## [1.0.3] - 2026-03-12

### Featured addition: Plaat et al. (2025) — *Agentic Large Language Models, a survey* (JAIR)

A peer-reviewed survey from Leiden University (Plaat, van Duijn, van Stein, Preuss, van der Putten, Batenburg), published in JAIR Vol. 84, December 2025. arXiv:2503.23037. Companion site: askeplaat.github.io/agentic-llm-survey-site/. Also at alphaxiv.org/abs/2503.23037.

### What this paper adds and where it changed the survey

**Taxonomy page:** Added explicit discussion of competing taxonomic frameworks (Wang et al. component-based vs. Plaat et al. Reason–Act–Interact), explaining both and showing how they map onto the survey's organization. Added new "Virtuous Cycle" section with diagram: the three capabilities (Reason, Act, Interact) are mutually reinforcing *and* generate new training data, addressing the "running out of training data" problem.

**Foundations page:** Added full entry for Plaat et al. as a major survey paper, including its five original contributions: virtuous cycle, Thinking Fast & Slow connection, Theory of Mind coverage, emergent social norms, and research agenda.

**Reasoning & Planning page:** Added Thinking Fast & Slow callout box connecting Kahneman's dual-process theory to LLM reasoning: System 1 (fast, associative generation) vs. System 2 (slow, deliberate CoT/tree search), with RL-trained reasoning models (o1, DeepSeek-R1) representing attempts to internalize System 2 through training rather than prompting.

**Multi-Agent page:** Added Theory of Mind & Social Capabilities section (strategic behavior, negotiation, ToM benchmarks) and Emergent Social Behavior section (agent societies, emergent norms, social science simulation, alignment implications).

**Resources page:** Added Plaat et al. to the "Getting Started" top list (item 2) and to the survey papers table.

---

## [1.0.2] - 2026-03-12

### Updates to existing pages

- **Multi-Agent Systems** — Added full production case study: Anthropic's multi-agent research system engineering post. Covers orchestrator-worker architecture, key numbers (90.2% improvement over single-agent, 4×/15× token multipliers, 80% BrowseComp variance explained by tokens alone), when multi-agent works vs. doesn't, and engineering lessons from shipping Claude Research to production

- **2024–2026 Frontier (Coding Agents)** — Added Devin/Cognition's "Agents 101" guide: 6 practical principles for working effectively with coding agents (specify how not just what; defensive prompting; CI/test feedback loops; immediate delegation; human ownership of correctness)

- **Science & Research Agents** — Added PaperCoder (arXiv:2504.17192, ICLR 2026): multi-agent framework that transforms ML papers into working code repositories via planning → analysis → generation pipeline with specialized agents per stage; evaluated on PaperBench, validated by paper authors; github.com/going-doer/Paper2Code

- **Community & Independent Agents** — Added new "Reverse Engineering Agent Design" section: x1xhlol/system-prompts-and-models-of-ai-tools (30,000+ lines of system prompts from Cursor, Devin, Claude Code, Windsurf, v0, Manus, Replit, Perplexity, Warp, Kiro, Junie, Lovable, and 15+ more). Analyzes cross-cutting patterns: defensive prompting is universal; AGENTS.md context files are standard; tool definitions are tightly specified; safety/scope baked in; diversity of autonomy assumptions

---

## [1.0.1] - 2026-03-12

### New Pages

- **Science & Research Agents** (`science-agents.qmd`) — FutureHouse Platform (Crow/Falcon/Owl/Phoenix), Google AI Co-Scientist, SkyRL (NovaSky/Berkeley), MiniMax Forge (scalable agent RL), Search-R1++ (deep research training), METR task time horizons (doubling every 7 months), AgentEvolver (self-evolving agents), NeurIPS 2025 KV cache hyper-scaling, Google's science of scaling agent systems, Moonshot AI / Kimi K2.5, GLM-5 agentic engineering

- **Community & Independent Agents** (`community.qmd`) — OpenClaw (self-hosted personal agent runtime), Strix by Tim Kellogg (stateful ambient agent on Discord with full build diary), Pi by badlogic (AI agent toolkit: unified LLM API, coding agent CLI, Slack bot, TUI/web UI, vLLM pod management), crow-cli (minimal MCP/ACP two-layer agent with PTY terminal), Agno (production framework: build/run/manage agents at scale with AgentOS control plane), Orchestra (cognitive load distribution via composition), TapeAgents (Bahdanau et al. — tape-centric framework with full audit trail; blackboard system echoes), AgentFS/Turso (SQLite-based filesystem for agents — auditability, reproducibility, portability), papercomputeco/stereOS (NixOS-based Linux hardened for AI agents: tapes telemetry, agentd daemon, masterblaster sandboxes), practitioner posts: Saurabh Alone Hitchhiker's Guide, Martin Fowler CLI coding agent, emsh.cat one-human-one-agent-one-browser, Leonie Monigatti memory in AI agents

### Updates to Existing Pages

- **Memory, Tools & Actions** — Added mem0 (26% accuracy improvement over OpenAI Memory, 91% faster, 90% fewer tokens; YC-backed, 27k stars), Letta/MemGPT evolution (full stateful agent platform with inspectable memory blocks, Letta Code CLI, model leaderboard), AgentFS cross-reference

- **Multi-Agent Systems** — Added TapeAgents (tape-centric agent framework with blackboard system connections), Agno (full-stack production framework)

- **2024–2026 Frontier** — Added: METR time horizons benchmark (doubling every 7 months), OpenAI Harness Engineering (0 manual code, 1M+ generated lines, 3→7 engineers, 5 months), OpenAI Codex long-horizon tasks guidance, GLM-5 vibe coding to agentic engineering (Zhipu AI), MIT AI Agent Index (aiagentindex.mit.edu — 30 agents, transparency gap, geographic divergence)

### Site structure
- Homepage: 6 → 8 navigation cards, stats updated to 300+ resources and 8 major themes
- Navbar updated with Science Agents and Community pages
- `_quarto.yml` render list updated (8 → 10 pages)

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
