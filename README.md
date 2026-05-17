# Awesome AI-SDLC [![Awesome](https://awesome.re/badge-flat.svg)](https://awesome.re)

> A curated, time-aware collection of resources documenting how GenAI is transforming the Software Development Life Cycle — from requirements to production, from individual tools to organizational change.

**Why this list?** The AI-SDLC landscape is evolving faster than any previous shift in software engineering. Resources from 6 months ago may already be outdated. This list captures not just *what* exists, but *when* it emerged and *what the evidence says*.

## How This List Is Organized

Most awesome lists organize by tool category. This one organizes by **SDLC phase** because the transformation is uneven — some phases are 10x disrupted while others remain stubbornly human. Each entry includes a date tag to track the rapid evolution.

**Date tags:** `[YYYY-MM]` — when the resource was published or last significantly updated.

**Evidence ratings:**
- 🟢 Empirical study (RCT, large-scale data, peer-reviewed)
- 🟡 Industry report (survey-based, vendor research)
- 🔵 Practitioner insight (blog, talk, experience report)
- 🟠 Theoretical / opinion (thought leadership, predictions)

---

## Contents

- [The Big Picture](#the-big-picture)
  - [State of AI in Software Engineering](#state-of-ai-in-software-engineering)
  - [Productivity Paradoxes & Measurement](#productivity-paradoxes--measurement)
  - [Organizational Impact](#organizational-impact)
- [SDLC Phase: Requirements & Design](#sdlc-phase-requirements--design)
  - [AI-Assisted Requirements Engineering](#ai-assisted-requirements-engineering)
  - [Spec-Driven Development](#spec-driven-development)
  - [Architecture & System Design](#architecture--system-design)
- [SDLC Phase: Development](#sdlc-phase-development)
  - [Code Generation & Completion](#code-generation--completion)
  - [Agentic Coding](#agentic-coding)
  - [Agentic Coding Failure Modes](#agentic-coding-failure-modes)
  - [Code Review & Quality](#code-review--quality)
  - [Refactoring & Migration](#refactoring--migration)
- [SDLC Phase: Testing & QA](#sdlc-phase-testing--qa)
  - [Test Generation](#test-generation)
  - [TDD with AI Agents](#tdd-with-ai-agents)
  - [Visual & E2E Testing](#visual--e2e-testing)
- [SDLC Phase: CI/CD & Release](#sdlc-phase-cicd--release)
  - [Pipeline Automation](#pipeline-automation)
  - [Release Management](#release-management)
  - [Feature Flags & Progressive Delivery](#feature-flags--progressive-delivery)
- [SDLC Phase: Operations & Observability](#sdlc-phase-operations--observability)
  - [AIOps & Incident Response](#aiops--incident-response)
  - [Self-Healing Systems](#self-healing-systems)
  - [Monitoring & Alerting](#monitoring--alerting)
- [SDLC Phase: Security](#sdlc-phase-security)
  - [AI-Assisted Security](#ai-assisted-security)
  - [Agent Security & Governance](#agent-security--governance)
  - [Supply Chain Security](#supply-chain-security)
- [SDLC Phase: Documentation & Knowledge](#sdlc-phase-documentation--knowledge)
  - [Automated Documentation](#automated-documentation)
  - [Knowledge Graphs & Semantic Layers](#knowledge-graphs--semantic-layers)
  - [Codebase Comprehension](#codebase-comprehension)
- [Cross-Cutting Concerns](#cross-cutting-concerns)
  - [Developer Experience (DevEx)](#developer-experience-devex)
  - [Skill Formation & Learning](#skill-formation--learning)
  - [Team Topologies & Agent Topologies](#team-topologies--agent-topologies)
  - [The Middle Loop (Supervisory Engineering)](#the-middle-loop-supervisory-engineering)
  - [Roles & Career Evolution](#roles--career-evolution)
  - [Enterprise & On-Prem Delivery](#enterprise--on-prem-delivery)
  - [Open Source Ecosystem Impact](#open-source-ecosystem-impact)
- [Building Software for Agents](#building-software-for-agents)
  - [The Agent-Native Thesis](#the-agent-native-thesis)
  - [Protocols & Standards](#protocols--standards)
  - [Agent-Native Architecture](#agent-native-architecture)
  - [Agent Commerce & Pricing](#agent-commerce--pricing)
  - [Agent-to-Agent Ecosystems](#agent-to-agent-ecosystems)
- [Frameworks & Maturity Models](#frameworks--maturity-models)
- [Timeline](#timeline)
- [Contributing](#contributing)

---

## The Big Picture

### State of AI in Software Engineering

- 🟢 `[2026-01]` [Who is using AI to code? Global diffusion and impact of generative AI](https://www.science.org/doi/10.1126/science.adz9311) - Landmark Science paper: 160K devs, 30M commits. AI writes 29% of new US code but only seniors see 3.6% productivity gain.

  <details><summary>Key findings</summary>

  - **Complexity Science Hub (CSH) Vienna** — examined AI impact across 6 countries
  - AI-authored code grew **6x** from 5% (2022) → 29% (end of 2024) for Python functions by US contributors
  - **Overall productivity gain: only 3.6%** — far below vendor claims
  - **The expertise paradox:** juniors adopt AI more (37% of code) but seniors (27%) capture all the productivity gains
  - Seniors use AI to explore new technical domains; juniors use it as a crutch
  - Estimated value: $23-38B globally in additional code value/year
  - *"AI tools are skill amplifiers, not skill equalizers"*

  </details>

- 🟡 `[2026-05]` [Microsoft: State of Global AI Diffusion 2026](https://blogs.microsoft.com/on-the-issues/2026/05/07/the-state-of-global-ai-diffusion-in-2026/) - GenAI usage reached **17.8% of the working-age population** in Q1 2026. **Git pushes up 78% YoY globally**, driven by AI coding tools. Enterprise dev tooling is the fastest-growing diffusion segment.

  <details><summary>Key findings</summary>

  - **17.8% of working-age population** using GenAI in Q1 2026 — fastest-diffusing tech wave on record
  - **Git pushes +78% YoY globally** — Claude Code, Codex, Copilot driving raw output volume
  - Enterprise developer tooling is the **fastest-growing diffusion segment**
  - Suggestive evidence of **Jevons paradox**: cheaper code → more software built → demand for developers may rise, not fall
  - Distinct adoption patterns across regions/industries; US/UK/India lead enterprise dev adoption

  </details>

- 🟡 `[2026-05]` [Anthropic: 2026 Agentic Coding Trends Report](https://resources.anthropic.com/hubfs/2026%20Agentic%20Coding%20Trends%20Report.pdf) - First systematic Anthropic report on how coding agents are reshaping the SDLC — covers adoption, autonomy levels, governance gaps, and the gap between "AI-assisted" and "AI-led" workflows. Companion to the Claude Code field data.

- 🟡 `[2026-04]` [NYT: The Big Bang — A.I. Has Created a Code Overload](https://www.nytimes.com/2026/04/06/technology/ai-code-overload.html) - Financial services firm went from 25K to 250K lines/month with Cursor, creating 1M-line review backlog. Code overload forcing companies to rethink velocity vs. absorption capacity.

- 🟢 `[2026-04]` [Stanford HAI 2026 AI Index Report](https://hai.stanford.edu/ai-index/2026-ai-index-report) - 400+ page annual report. AI boosts SW dev productivity 26%, but entry-level hiring declining. SWE-bench Verified jumped from ~60% (2024) to nearly 100% (2025). AI adopted faster than any previous technology wave. GenAI tools valued at $172B/year for US consumers.

  <details><summary>Key findings</summary>

  - Employment for **software developers aged 22–25 has fallen ~20%** since late 2022, while devs 30+ grew 6–12% at same companies
  - **SWE-bench Verified** jumped from ~60% (2024) to **nearly 100%** (2025) — AI can now resolve most real-world GitHub issues autonomously
  - AI adopted **faster than any previous technology wave**; AI companies generating revenue faster than any prior tech boom
  - **26% productivity boost** in software development (14% in customer service)
  - Estimated value of GenAI tools to US consumers: **$172B annually**
  - Sources: [Stanford HAI](https://hai.stanford.edu/news/inside-the-ai-index-12-takeaways-from-the-2026-report) · [MIT Tech Review](https://www.technologyreview.com/2026/04/13/1135675/want-to-understand-the-current-state-of-ai-check-out-these-charts/) · [crypto.news](https://crypto.news/ai-jobs-devs-under-26-lost-20-of-work-since-2022/)

  </details>

- 🟡 `[2026-04]` [DX Q1 2026 AI Impact Report](https://newsletter.getdx.com/p/ai-assisted-engineering-q1-2026-impact) - Adoption at 93%. Juniors who use AI daily now save 4.9 hrs/wk, edging Staff+ at 4.8 hrs (reversal from Q4 2025). Engineering managers shipping 4x more PRs vs. ~2x last quarter — the "player-coach" comeback. Shadow-AI risk growing.

- 🟡 `[2026-04]` [Cloudflare: Internal AI Engineering Stack — 93% R&D Adoption](https://blog.cloudflare.com/internal-ai-engineering-stack/) - 3,683 users (93% of R&D, 60% company-wide) actively use AI coding tools. 241B tokens routed through AI Gateway in 30 days. Built on own platform (Workers AI, AI Gateway). Tiger team "iMARS" builds internal MCP servers and agentic tooling.

  <details><summary>Key findings</summary>

  - **3,683 AI coding tool users** — 93% of R&D, 60% of entire company
  - **241 billion tokens** routed through AI Gateway in last 30 days
  - **295 teams** using agentic AI tools
  - **47.95M AI requests** processed
  - Built entirely on their own platform (Workers AI, AI Gateway) — dog-fooding at scale
  - Formed tiger team **"iMARS"** to build internal MCP servers and agentic tooling
  - Companion post details CI-native AI code review system across **5,169 repos**

  </details>

- 🟡 `[2026-04]` [Google: 75% of New Code Is AI-Generated](https://indianexpress.com/article/technology/artificial-intelligence/google-75-percent-ai-generated-code-sundar-pichai-10656702/) - Sundar Pichai disclosed that AI-generated code (approved by humans) rose from 50% last fall to 75%. A "complex code migration" completed 6× faster using mixed AI-agent + human teams.

- 🟡 `[2026-04]` [JetBrains AI Pulse: 90% of Devs Use AI at Work](https://www.ajeetraina.com/which-ai-coding-tools-are-developers-actually-using-at-work-in-2026/) - Survey of 10,000+ devs: 74% use purpose-built AI coding tools. GitHub Copilot still #1 (29%) but growth stalled. Claude Code fastest mover: 18% adoption (6× growth in 3 quarters), 91% CSAT, 54 NPS — highest loyalty on the market. Cursor plateaued at 18%.

  <details><summary>Key findings</summary>

  - **90% of developers** use AI at work (Jan 2026 survey, 10K+ respondents)
  - **74%** use purpose-built AI coding tools (not just ChatGPT)
  - GitHub Copilot still #1 at **29% adoption** but growth has stalled
  - **Claude Code: fastest mover** — 18% adoption (6× growth in 3 quarters), 91% CSAT, 54 NPS
  - Cursor plateaued at **18%** adoption
  - **22%** of developers use coding agents; **66%** of companies plan agent adoption within 12 months

  </details>

- 🟡 `[2026-04]` [Datadog: 2026 State of AI Engineering](https://www.datadoghq.com/state-of-ai-engineering/) - Analyzed telemetry from 1000+ customers. OpenAI share dropped from 75% → 63% as Gemini/Claude gained 20-23pp. 70%+ of orgs now use 3+ models. Teams building "model portfolios" per workload — multi-provider pattern creates new platform engineering challenges.

- 🟡 `[2026-04]` [Amazon Mandates 3× Release Velocity via AI-Native Practices](https://www.businessinsider.com/amazon-tracks-ai-use-engineers-internal-friction-2026-4) - Internal doc shows 2,100+ retail engineering teams tracked on AI tool adoption. A subset of 25 teams targets 10× output. S-Team monitors progress; internal friction growing as some engineers push back against top-down mandates.

- 🔵 `[2026-04]` [AI Dev 26 SF Conference: 3,000+ Devs Debate AI-First Engineering](https://www.theregister.com/2026/04/28/software_development_ai_dev25xsf/) - Andrew Ng argued frontier teams are trending toward 100% AI-generated code; reviewing code makes humans the bottleneck. AWS VP Marc Brooker countered: "The opportunity for agents is limited by the defect rate" — reducing errors matters more than pushing frontiers. Oracle predicted dev roles blur into agent orchestration + product management.

  <details><summary>Key takeaways</summary>

  - **Andrew Ng (DeepLearning.AI):** frontier teams trending toward **100% AI-generated code**; human review is the bottleneck
  - **Marc Brooker (AWS VP):** *"The opportunity for agents is limited by the defect rate"* — error reduction > speed
  - **Richmond Alake (Oracle):** developer roles blurring into **agent orchestration + product management**
  - **Spec-driven development** produces better AI results — echoes McKinsey/QuantumBlack SDD pattern
  - Highlighted tools: Hydro (Rust distributed protocols), Cedar (authorization language), Strata (automated reasoning)
  - 3,000+ developers gathered; signals AI-first engineering now mainstream conference topic

  </details>

- 🟢 `[2026-05]` [Agentic AI in the SDLC — Comprehensive Survey (Bhati)](https://arxiv.org/abs/2604.26275) - Synthesizes evidence across Anthropic, OpenAI, DeepMind, Microsoft Research, Princeton, Stanford. SWE-bench Verified rose from 1.96% → 78.4% (Oct 2023 – Apr 2026). Controlled studies show 13.6%–55.8% time savings. Proposes 6-layer reference architecture for agentic SE systems.

  <details><summary>Key findings</summary>

  - **SWE-bench Verified** performance trajectory: **1.96% → 78.4%** (Oct 2023 – Apr 2026)
  - Controlled studies show **13.6%–55.8% time savings** depending on task complexity
  - Anthropic's 2026 data: **49% of sampled jobs** now use AI for ≥25% of tasks
  - Proposes **6-layer reference architecture** for agentic SE systems
  - Identifies 5 open problems: evaluation, governance, tech debt, skill redistribution, economics of attention

  </details>

- 🟡 `[2026-05]` [Preuve.ai: AI Coding Tool Adoption at 84%](https://preuve.ai/blog/ai-coding-models-statistics-2026) - Compilation of 50+ stats: Stack Overflow 2025 survey pegged adoption at 84% (up from 76% prior year), with 80% of professional devs now having AI in their workflow.

- 🟡 `[2026-04]` [Lightrun 2026: State of AI-Powered Engineering](https://lightrun.com/ebooks/state-of-ai-powered-engineering-2026/) - Survey of 200 SRE/DevOps leaders: 43% of AI-generated code changes still need manual debugging in production after QA + staging. 0% can validate an AI fix in a single redeploy; 88% need 2–3 cycles. Amazon's March 2026 outages (6.3M lost orders) traced to AI-assisted code.

  <details><summary>Key findings — the "trust wall"</summary>

  - **43%** of AI-generated code changes require manual debugging in production after passing QA
  - **0%** of leaders are "very confident" in AI-generated code correctness
  - **88%** need 2–3 redeploy cycles to verify AI fixes; 11% need 4–6
  - Amazon's March 2026 outages (**6.3M lost orders**) traced to AI-assisted code deployed without safeguards
  - Sources: [TechBooky](https://www.techbooky.com/survey-43-of-ai-generated-code-changes-still-break-in-production/) · [VentureBeat](https://venturebeat.com/technology/43-of-ai-generated-code-changes-need-debugging-in-production-survey-finds)

  </details>

- 🟡 `[2026-04]` [MIT Tech Review / Thoughtworks: Agentic AI in Software Engineering](https://www.technologyreview.com/2026/04/14/1134397/redefining-the-future-of-software-engineering/) - Survey of 300 engineering execs: 51% already use agentic AI, 98% expect time-to-market acceleration averaging 37%. 41% aim for full AI-managed SDLC within 18 months. Compute costs and integration are top barriers.

- 🟡 `[2026-04]` [Gartner: AI-Native Development Platforms — Top 2026 Strategic Trend](https://www.itpro.com/technology/artificial-intelligence/gartner-top-strategic-technology-trends-for-2026-ai-native-development-platforms) - "Spec-driven development" and AI-native dev platforms as paradigm shift: domain knowledge becomes more important than coding skill. Forecasts 60% of new code will be AI-generated by end of 2026.

  <details><summary>Key findings</summary>

  - Financial services team jumped from **25K to 250K lines/month** after rolling out Cursor
  - Review capacity did **not** scale with generation capacity, creating a **1M-line backlog**
  - The bottleneck moved from writing code to **absorbing, reviewing, and validating** it
  - Strong illustration of the new failure mode: local developer speed up, system throughput flat or worse

  </details>

- 🟡 `[2026-04]` [Fortune/NBER: "Solow's Paradox" Repeating for AI](https://fortune.com/article/why-do-thousands-of-ceos-believe-ai-not-having-impact-productivity-employment-study/) - Study of 6,000 executives (US, UK, Germany, Australia): ~90% of firms report no measurable impact from AI on employment or productivity over past 3 years. Average AI usage among adopters: just 1.5 hrs/week. Apollo's chief economist: "AI is everywhere except in the incoming macroeconomic data."

  <details><summary>Key findings — the macro-micro paradox</summary>

  - **6,000 executives** surveyed across US, UK, Germany, Australia
  - **~90% of firms** report no measurable AI impact on employment or productivity over past 3 years
  - Average AI usage among adopters: **just 1.5 hrs/week**
  - Executives still forecast +1.4% productivity and +0.8% output gains over the next 3 years
  - Fed Reserve St. Louis: only **1.9% cumulative excess productivity growth** since ChatGPT's late-2022 introduction — measurable but far below hype
  - Apollo's chief economist: *"AI is everywhere except in the incoming macroeconomic data"*
  - **Key tension:** micro-level studies show 25–55% developer productivity gains; macro-level data shows almost nothing

  </details>

- 🟡 `[2026-04]` [BCG: AI Will Reshape More Jobs Than It Replaces](https://www.bcg.com/publications/2026/ai-will-reshape-more-jobs-than-it-replaces) - Engineers shift toward system-level thinking, orchestration, and product design. AI helps engineers do jobs more effectively rather than replacing them, making direct displacement unlikely.

  <details><summary>Key findings</summary>

  - Work shifts upward from raw implementation toward **system thinking, orchestration, and design**
  - The more durable change is **job redesign**, not headcount elimination
  - Reinforces the emerging pattern that AI changes the mix of engineering work faster than it removes engineering roles

  </details>

- 🟡 `[2026-02]` [DX Research: 93% of Devs Use AI, Productivity Still +10%](https://lauratacho.com/research) - 121K developers, 450+ companies. Productivity plateaued at ~10%. Onboarding time halved.

  <details><summary>Key findings</summary>

  - **Laura Tacho (CTO, DX)** — largest ongoing developer productivity survey
  - 92.6% of devs use AI coding assistant monthly; 75% weekly
  - Time savings plateaued at **~4 hrs/week** (unchanged since Q2 2025)
  - AI-authored production code: **26.9%** (up from 22% last quarter)
  - **Onboarding time cut in half** (time to 10th PR)
  - Well-structured orgs see **50% fewer incidents**; struggling orgs see **2x MORE incidents**
  - *"AI exposes flaws instead of fixing them"* in weak organizations
  - *"This is a management problem, not a technology problem"*

  </details>

- 🟡 `[2025-12]` [DORA 2025 AI Capabilities Model](https://services.google.com/fh/files/misc/2025_dora_ai_capabilities_model.pdf) - 7 organizational capabilities for AI success. 25% more AI adoption → 7.2% drop in delivery stability.

  <details><summary>Key findings</summary>

  - **Google's DevOps Research and Assessment** — first dedicated AI impact report
  - 2024: AI adoption decreased both stability AND throughput
  - 2025: throughput rebounded, **but instability persists**
  - **7 AI capabilities:** clear AI stance, version control, quality platforms, small batches, healthy data, AI-accessible data, user-centric focus
  - **Batch size paradox:** large batches feel more productive to individual devs but hurt product performance
  - *"AI amplifies strengths of high-performing orgs AND dysfunctions of struggling ones"*
  - Recommends **value stream mapping** before AI adoption
  - Overhead, review friction, and tooling mismatch explain why small batches feel slower despite better outcomes

  </details>

- 🟡 `[2025-01]` [Bain 2025 Technology Report](https://www.bain.com/insights/technology-report-2025/) - 25-30% engineering productivity with full SDLC AI adoption; most orgs see only 5-15%.

- 🔵 `[2026-02]` [ThoughtWorks Future of Software Development Retreat](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - 10 themes from senior practitioners including Middle Loop, risk tiering, TDD as prompt engineering.

  <details><summary>10 key themes</summary>

  1. **Rigor migrates, doesn't disappear** — engineering discipline moves to specs, test suites, type systems, risk mapping
  2. **The "Middle Loop"** — new category of work: supervising agents (between inner-loop coding and outer-loop CI/CD)
  3. **Conway's Law applies to agents** — agent topology mirrors team topology; speed mismatch creates decision fatigue
  4. **Security is dangerously underdeveloped** — lowest session attendance = the warning sign
  5. **Self-healing systems still far off** — missing prerequisites: change ledger, agent identity, fitness functions
  6. **Productivity & developer experience are decoupling** — orgs get more output even when devs report lower satisfaction
  7. **Junior devs more valuable, not less** — AI gets juniors past net-negative phase faster; real risk is mid-level
  8. **PM & developer roles converging** — nobody can define PM in AI-first world
  9. **Knowledge graphs having a moment** — telecom captured entire domain ontology in ~286 concepts
  10. **Agile evolving, not dying** — XP practices rediscovered; governance is the real threat

  Key attendees: Martin Fowler, Kent Beck, Annie Vella, Rachel Laycock, Steve Yegge, Gene Kim

  </details>

- 🟡 `[2026-02]` [Opsera: AI Coding Impact 2026 Benchmark Report](https://opsera.ai/resources/report/ai-coding-impact-2026-benchmark-report/) - 250K+ developers, 60+ enterprises. AI reduces time-to-PR by 58%, but AI-generated PRs wait 4.6x longer in review. AI code introduces 15-18% more security vulnerabilities.

  <details><summary>Key findings</summary>

  - **250,000+ developers across 60+ enterprise organizations** — one of the largest field studies
  - Nearly **90% of enterprise teams** now use AI in the dev lifecycle — adoption is universal, no longer differentiating
  - AI-driven coding reduces **time to pull request by up to 58%**
  - But AI-generated PRs **wait 4.6x longer in review** without governance frameworks
  - AI-generated code introduces **15-18% more security vulnerabilities**, increasing risk as autonomy expands
  - **Senior engineers realize ~5x the productivity gains** of junior engineers — widening the execution gap
  - **21% of AI licenses remain underutilized**, limiting ROI
  - Confirms the pattern: speed gains upstream, bottleneck moves downstream

  </details>

- 🟠 `[2026-02]` [Jon Radoff: The State of AI Agents in 2026](https://meditations.metavert.io/p/the-state-of-ai-agents-in-2026) - 200+ slide research deck. AI inference costs dropped 92% in 3 years. METR task horizons doubled to 14.5 hours. Only 6% of orgs report >5% EBIT impact from AI despite $1.5T total spending.

  <details><summary>Key findings</summary>

  - **AI inference costs:** dropped from $30/M tokens (2023) → $0.10-$2.50 (Feb 2026) — a **92% decline**
  - **METR task horizons:** autonomous work increased from ~4 minutes (early 2024) to **14.5 hours** (Feb 2026) — doubling every 123 days
  - At current rate: week-long autonomous tasks by late 2026, month-long by mid-2027
  - **SWE-Bench Verified:** Claude Opus 4.5 hit 80.9% (up from 33% eighteen months ago)
  - **GPQA Diamond:** Claude Opus 4.6 scored 91.3%, exceeding human experts at 69.7%
  - **The value gap:** $211B in AI VC (half of all global VC), $1.5T total AI spending — but only 6% of orgs report >5% EBIT impact
  - **6x output gap** between top-quartile AI users and everyone else
  - **67% increase** in merged PRs per engineer at Anthropic
  - *"The bottleneck isn't engineering capacity anymore. It's imagination."*

  </details>

- 🔵 `[2026-02]` [Pragmatic Engineer Summit: 6 Predictions for Future of SE](https://newsletter.pragmaticengineer.com/p/the-future-of-software-engineering-with-ai) - Gergely Orosz hosts Laura Tacho, Thomas Dohmke (ex-GitHub CEO), Rajeev Rajan (Atlassian CTO). Some Atlassian teams write zero hand-written code — all agent-orchestrated, 2-5x output.

  <details><summary>Key highlights</summary>

  - **Atlassian CTO Rajeev Rajan** bought a personal laptop because corporate IT blocked Claude Code — *"best answer to investors asking about incumbent defense"*
  - Some Atlassian teams: **zero lines of hand-written code**, all agent-orchestrated, producing 2-5x more output
  - Bank CTOs run agents at night on side projects for 2 weeks, then mandate org-wide rollout
  - **Thomas Dohmke (ex-GitHub CEO):** *"AI native is the new cloud native"* — building Entire.io as AI-native startup
  - Agents as "sparring partners" that make **remote work advantageous again**
  - Laura Tacho keynote confirmed: 92% adoption, 4h/week savings plateau, AI as space-race analogy
  - **Mid-level engineers' "quiet crisis"** discussed behind closed doors by eng leaders
  - XP practices (pairing, ensemble) making comeback on Agile's 25th anniversary

  </details>

- 🟡 `[2026-03]` [2026 AI Coding Statistics (Panto)](https://panto.io/ai-coding-statistics) - Comprehensive meta-analysis: 84% developer adoption, 51% daily usage among pros, ~3.6 hrs/week saved average. **Critical finding: AI-coauthored PRs show ~1.7× more issues than human-only PRs** (CodeRabbit analysis). 22% of merged code now AI-authored. Daily AI users merge ~60% more PRs.

- 🔵 `[2026-03]` [Google Agent Smith Internal Launch](https://www.businessinsider.com) - Google deploying autonomous coding agent "Agent Smith" internally, driven by Sergey Brin's agent-first push. Limited details on productivity/quality metrics.

- 🔵 `[2026-03]` [GitHub Copilot Opt-Out Policy Change](https://github.blog/changelog/2026-03-27-copilot-training-data-opt-out-change) - Starting April 24, 2026, GitHub defaulting Copilot Free/Pro/Pro+ users into AI training pipeline (opt-out, not opt-in). Individual devs' code/prompts/interactions used for model training unless manually disabled. Enterprise/Business customers exempt. Community backlash significant (117 thumbs-down on announcement).

- 🟡 `[2026-03]` [Ryz Labs: 70% Developer AI Adoption Milestone](https://learn.ryzlabs.com/ai-coding-assistants/github-copilot-vs-aider-which-ai-coding-assistant-reigns-in-2026) - Survey finds nearly 70% of developers now rely on AI-assisted coding to enhance productivity and reduce debugging time. Marks mainstream adoption threshold crossed.

- 🟡 `[2026-03]` [Jellyfish Benchmark: AI Coding Boom Doubles Output, Quality Holds](https://www.businessinsider.com/ai-coding-boom-more-software-shipped-no-hit-quality-2026-3) - 700 companies, 200K engineers, 20M PRs. High-adoption teams merge 2.2 PRs/engineer/week (2x low-adoption). 63% of companies use AI for most coding. Revert rates barely move (0.61% → 0.65%). "Claude Christmas" coined for the Dec 2025 inflection point.

  <details><summary>Key findings</summary>

  - **Jellyfish engineering intelligence platform** — largest recent field study of AI coding tool adoption
  - Median AI tool adoption: **63%** across companies in dataset
  - **64% of companies** now generate majority of code with AI assistance
  - High-adoption companies (75-100% of engineers using AI 3+ days/week): **2.2 PRs/engineer/week**
  - Low-adoption companies: **1.12 PRs/engineer/week** — nearly half
  - Revert rates (code rolled back): **0.61% (low adoption) → 0.65% (high adoption)** — minimal quality degradation
  - **"Claude Christmas"** — head of research stopped writing code himself in fall 2025; named the Dec 2025 moment when AI coding tools crossed the usability threshold
  - Autonomous agent PRs (opened/committed by AI agents) still small share but climbing rapidly among top adopters
  - *"Lots of folks are accepting that AI helps you code faster and are starting to think about all of the follow-on problems"*

  </details>

- 🟢 `[2026-04]` [An Empirical Study of Generative AI Adoption in Software Engineering](https://arxiv.org/html/2512.23327) - 204 respondents, 37 countries. GenAI deeply integrated into implementation, V&V, maintenance. 80% regular use. Critical gap: most teams lack objective productivity/quality metrics. Top concerns: skill erosion, over-reliance, IP/ethical issues.

  <details><summary>Key findings</summary>

  - **Eindhoven, Izmir, PUC-Rio, Blekinge, fortiss collaboration** — international survey of SE practitioners
  - **80% use GenAI regularly**, daily or near-daily usage common
  - Top use cases: **implementation** (coding, completion), **verification & validation**, **personal assistance**, **maintenance**
  - Reported benefits: **reduced cycle time**, enhanced knowledge work, perceived quality and productivity gains
  - **Measurement gap:** most teams don't use objective metrics for productivity/quality impact — opportunity to standardize measurement
  - Key challenges: **accuracy/reliability**, prompt engineering, validation overhead, **security/privacy concerns**
  - **Organizational readiness varies:** many provide tool access; fewer invest in training, clear policies, or governance
  - Practitioners expect GenAI to **redefine roles, not replace them** — moderate concern about job market contraction
  - *"Adoption must move beyond ad-hoc towards systematic, sustainable, and responsible integration"*

  </details>

- 🔵 `[2026-03]` [Cursor's Crossroads: $30B AI Startup's Rapid Rise](https://fortune.com/2026/03/21/cursor-ceo-michael-truell-ai-coding-claude-anthropic-venture-capital/) - Fortune deep-dive on Cursor. Used by 67% of Fortune 500, generating 150M lines of enterprise code daily. *"Coding is the first real place AI productivity gains have been quantifiable and undeniable."* $29.3B valuation.

  <details><summary>Key highlights</summary>

  - **Fortune feature interview** with CEO Michael Truell (25 years old, MIT background)
  - Cursor now at **$29.3 billion valuation** (as of March 2026)
  - **67% of Fortune 500 companies** actively using Cursor platform
  - Platform generates **150 million lines of enterprise code daily**
  - Backed by Andreessen Horowitz, Thrive, Accel (billions raised in 4 years)
  - *"Coding has been the first real place the productivity gains [from AI] have been quantifiable and undeniable"*
  - Market positioning: AI-native coding versus GitHub's incremental AI features
  - **Rapid speed as existential risk:** "slow down for even a week, and you might get left behind"
  - Irony noted: CEO admires Robert Caro (decades-long biographer) while running hyper-speed AI startup

  </details>

### Productivity Paradoxes & Measurement

- 🟡 `[2026-05]` [Jellyfish 2026 State of Engineering Management](https://jellyfish.co/blog/ai-adoption-improving-engineering-productivity-and-job-satisfaction-jellyfish-report-finds/) - **64% of leaders report ≥25% velocity gains** from AI; top-quartile AI adopters merge **2× more PRs** than bottom-quartile. Volume continues to climb but the quality gap between adopters widens — outcomes still depend on management foundations, not tooling.

- 🟢 `[2026-05]` ["The Fast and Spurious": Developer Productivity with GenAI (arXiv 2510.24265)](https://arxiv.org/html/2510.24265v2) - SPACE-framework study finds **surface speed gains are offset by review burden, verification load, and unchanged collaboration patterns**. Frequent GenAI users complete tasks faster but the team-level effect washes out. Heavily cited as the empirical anchor for the velocity paradox.

  <details><summary>Key findings</summary>

  - Uses the **SPACE framework** (Satisfaction, Performance, Activity, Communication, Efficiency) to measure AI impact
  - Frequent GenAI users complete tasks faster but **cognitive load + review burden offset the gain**
  - **Collaboration patterns largely unchanged** — AI does not improve cross-team communication
  - Reinforces the "lab vs real-world" gap: speed gains shrink dramatically outside controlled settings
  - Often paired with the Meta-analysis (g=0.33) as the strongest evidence base in early-2026 research

  </details>

- 🟡 `[2026-05]` [Faros AI: The Productivity Paradox (1,255 Teams / 10K+ Devs)](https://www.faros.ai/blog/ai-software-engineering) - Telemetry shows **individual gains are real but don't aggregate to org throughput**: downstream bottlenecks (review, QA, deploy) absorb upstream AI speed. Confirms the company-level translation gap.

- 🟡 `[2026-05]` [LoopStudio: State of AI in Software Development 2026](https://loopstudio.dev/the-state-of-ai-in-software-development/) - **84% of devs use or plan to use AI tools**, but **trust in AI output dropped to 29%** (down 11 pts from 2024). Cites **Veracode finding that 45% of AI-generated code contains OWASP Top 10 vulnerabilities**. Frames AI as "a productivity tool, not a productivity strategy."

  <details><summary>Key findings</summary>

  - **84% adoption** — AI coding tools now table stakes
  - **Trust in AI output: 29%** (down 11 pts YoY) — the trust gap is widening even as adoption rises
  - **45% of AI-generated code** contains OWASP Top 10 vulnerabilities (Veracode)
  - Review cycles **lengthening**, post-merge fixes **increasing**
  - Frames AI as **"productivity tool, not productivity strategy"** — org design and review infra now the bottleneck

  </details>

- 🟢 `[2026-05]` [AI-Generated Code Debt Study (arXiv 2603.28592)](https://arxiv.org/html/2603.28592v2) - **22.7% of issues introduced by AI-authored code survive at HEAD** across 464K tracked items — real technical debt accumulating in mainline codebases. First large-scale longitudinal measurement of AI-introduced code debt.

- 🟢 `[2026-05]` [Beyond the Commit: 6 Productivity Dimensions for AI-Era SE (ICSE-SEIP 2026 — arXiv 2602.03593)](https://arxiv.org/abs/2602.03593) - Argues commit/PR throughput misses the actual impact of AI tools. Surfaces **six productivity dimensions**: self-sufficiency, cognitive load, peer-review ease, expertise growth, ownership, and long-term skill development — the last of which is critically under-studied.

- 🟢 `[2026-05]` [DORA: Impact of Generative AI in Software Development](https://dora.dev/ai/gen-ai-report/) - Heavy GenAI users report **more flow, higher satisfaction, less burnout** — but **39% still trust AI outputs "a little" or "not at all"**. Trust is now the gate on productivity, not capability.

- 🟡 `[2026-05]` [Deloitte 2026 Software Industry Outlook](https://www.index.dev/blog/developer-productivity-statistics-with-ai-tools) - Projects **30–35% productivity gains across the SDLC**, but cautions that low-maturity orgs see **quality regressions** that erode the gain. Adds to the "AI amplifies what's already there" pattern.

- 🟡 `[2026-05]` [TFiR: AI Code Quality 2026 — The Year of Guardrails](https://tfir.io/ai-code-quality-2026-guardrails/) - Industry pivot from raw productivity to governance: **AI-assisted code shows ~1.7× issue density** and **48% of AI snippets contain security findings without guardrails**. 2026 framed as the year guardrails — not throughput — become the dominant procurement criterion.

- 🟢 `[2026-04]` [GitHub + Accenture: 55% Faster Task Completion (4,800 Devs)](https://firstlinesoftware.com/blog/ai-software-development-2026-2035/) - Large-scale empirical study across 4,800 developers finds 55% faster task completion. McKinsey separately reports 30% lower time-to-market. Early-stage builds see up to 80% cost reduction.

- 🟡 `[2026-04]` [Exceeds AI: Enterprise AI Coding ROI Benchmarks](https://blog.exceeds.ai/enterprise-ai-coding-roi-studies/) - Case studies: Bancolombia 30%, JPMorgan 10–20%, EchoStar 25% productivity gains. GitHub Copilot delivers 376% 3-year ROI per Forrester TEI study. But METR's RCT found 19% net slowdown for experienced devs on complex tasks — verification overhead often exceeds code-writing time.

- 🟢 `[2026-04]` [Fortune/NBER: "Solow Paradox 2.0" — 90% of CEOs Report No AI Impact](https://fortune.com/article/why-do-thousands-of-ceos-believe-ai-not-having-impact-productivity-employment-study/) - Study of 6,000 executives across US, UK, Germany, Australia. Average AI usage among adopters: only 1.5 hrs/week. Economists draw parallel to Solow's 1987 computer productivity paradox. Fed Reserve St. Louis observed only 1.9% cumulative excess productivity growth since ChatGPT's launch.

  <details><summary>Key findings</summary>

  - **~90% of firms** report no measurable impact from AI on employment or productivity over past 3 years
  - Average AI usage among adopters: **only 1.5 hrs/week**
  - Executives still forecast **+1.4% productivity** and **+0.8% output** gains over next 3 years
  - Apollo's chief economist: *"AI is everywhere except in the incoming macroeconomic data"*
  - Fed Reserve St. Louis: only **1.9% cumulative excess productivity growth** since ChatGPT's late-2022 introduction
  - Directly parallels Solow's 1987 observation: *"You can see the computer age everywhere but in the productivity statistics"*

  </details>

- 🔵 `[2026-04]` [Wawandco: The AI Velocity Paradox — Teams Ship 19% Slower](https://wawand.co/blog/posts/the-ai-velocity-paradox-why-faster-coding-slows-shipping/) - Analysis citing 2025 DORA report: developers perceive 20% speed increase with AI assistants, but teams deliver 19% slower due to downstream friction. Faros AI data (10K+ devs): heavy AI users create 98% more PRs but review times balloon 91%. Code churn rose from 3.1% (2020) to 5.7% (2024).

- 🟡 `[2026-04]` [PanDev: Cursor Users Log 65% More Coding Hours Than VS Code Users](https://dev.to/arthur_pandev/the-ai-copilot-effect-how-ai-assistants-changed-coding-time-in-2026-4427) - Analysis of 100+ B2B companies shows Cursor users average 50.5h vs VS Code's 30.6h per person. Caution: likely self-selection bias (early adopters), but longer sessions suggest AI reduces micro-interruptions and sustains flow state.

- 🟡 `[2026-04]` [DORA: ROI of AI-Assisted Software Development (Updated Apr 2026)](https://dora.dev/ai/roi/report/) - Practical framework + ROI calculator for measuring AI adoption ROI in the SDLC. Addresses the "initial productivity dip" during rollout. Companion Faros analysis (22K devs, 4K teams, 2 years of telemetry) reveals sharp quality tradeoffs.

  <details><summary>Key findings — DORA + Faros companion telemetry</summary>

  - **DORA ROI Calculator:** interactive financial framework for eng leaders to model AI tooling business case
  - **Faros companion analysis** (22K devs, 4K teams, 2 years of telemetry):
    - Task throughput per dev: **+33.7%**
    - Code-related tasks per team: **+210%**
    - But incidents per PR: **+242.7%**
    - Bugs per dev: **+54%**
  - Both reports agree on a **"verification tax"** on senior engineers
  - Sources: [DORA Report](https://dora.dev/ai/roi/report/) · [Faros Analysis](https://www.faros.ai/blog/dora-ai-roi-calculator-telemetry-inputs)

  </details>

- 🔵 `[2026-05]` [Hostinger: Vibe Coding Statistics — Context-Dependent Productivity](https://www.hostinger.com/blog/vibe-coding-statistics) - Controlled studies show results ranging from 55% speedup to 19% slowdown depending on task type, developer experience, and codebase complexity. Highlights how context-dependent AI productivity claims really are.

- 🟡 `[2026-05]` [McKinsey: AI Productivity Paradox — Sustained Impact Elusive](https://www.mckinsey.com/capabilities/strategy-and-corporate-finance/our-insights/where-ai-will-create-value-and-where-it-wont) - New McKinsey piece argues GenAI adoption is growing and investment accelerating, but "sustained impact on performance is elusive" for most orgs. Highlights gap between pilot wins and enterprise-wide value capture.

- 🔵 `[2026-04]` [QASource: DORA Metrics Are Now Insufficient for AI-Era Engineering](https://www.qasource.com/blog/software-engineering-metrics-beyond-dora) - AI-generated code pushes throughput up 30–40%, doubles code churn, but drops delivery stability by 7.2%. DORA captures none of the new failure modes. Proposes supplementary metrics: AI code quality ratio, developer experience (DX), context-switching overhead (devs lose 6+ hrs/week to tool fragmentation).

- 🟡 `[2026-04]` [DORA: ROI of AI-Assisted Software Development (Updated Apr 2026)](https://dora.dev/ai/roi/report/) - Practical framework + ROI calculator for measuring AI adoption ROI in the SDLC. Addresses the "initial productivity dip" during rollout and provides budget-defense calculations.

- 🟡 `[2026-04]` [Pragmatic Engineer AI Survey: 3 Developer Archetypes (900+ Respondents)](https://newsletter.pragmaticengineer.com/p/the-impact-of-ai-on-software-engineers-2026) - "Builders" spend more time debugging AI slop, "Shippers" move fast but accumulate tech debt, "Coasters" uplevel quickly but generate low-quality code. Companies spending ~$200/mo per dev on AI tools. ~30% of engineers hit tool usage limits.

  <details><summary>Key findings</summary>

  - **3 developer archetypes** emerging under AI:
    - **Builders:** spend more time debugging AI output ("AI slop")
    - **Shippers:** move fast but accumulate technical debt faster
    - **Coasters:** uplevel quickly but generate low-quality code
  - **~30%** of engineers hit AI tool usage limits
  - Companies spending **~$200/mo per dev** on AI tools; some CTOs admit budgets unsustainable
  - Engineer and EM roles converging as orchestration replaces hands-on coding

  </details>

- 🟡 `[2026-04]` [Faros.ai: 2 Years of AI Coding Agent Telemetry (22K Devs)](https://www.faros.ai/blog/best-ai-coding-agents-2026) - Analysis of AI coding agents' real impact across 22,000 developers. Highlights the "productivity paradox" — more code output doesn't always mean better outcomes. Confirms verification overhead as primary limiting factor.

- 🟡 `[2026-04]` [StartEdge: "30% AI-Generated Code" Metric Is Misleading](https://startedgeservices.com/how-ai-and-software-development-are-changing/) - Argues vanity metrics like % AI-generated code provide zero insight into actual productivity. Real measurement requires DORA-style metrics: cycle time, deployment frequency, change failure rate, and business value delivered.

- 🔵 `[2026-04]` [DORA Metrics 2026: AI Expansion Meets Visibility Crisis](https://byteiota.com/dora-metrics-2026-ai-expansion-meets-visibility-crisis/) - DORA grew from 4 to 20+ metrics including AI-specific KPIs (GenAI tool ROI, AI coding productivity). Key finding: "AI doesn't fix teams, it amplifies what's already there." 90% use AI tools, 80% believe they boost productivity, but 30% don't trust AI-generated code. AI improves throughput but increases change failure rate.

- 🟢 `[2026-05]` [Meta-Analysis: GenAI Coding Assistants Show Moderate Productivity Gains (g=0.33), No Learning Effect](https://arxiv.org/abs/2605.04779) - Rigorous meta-analysis of 23 studies (27 effect sizes) finds statistically significant but moderate positive effect on developer productivity (Hedges' g = 0.33). Gains larger in controlled experiments than real-world contexts. Crucially, no significant effect on learning outcomes (g = 0.14).

  <details><summary>Key findings</summary>

  - **23 studies, 27 effect sizes** — most rigorous meta-analysis of GenAI coding tools to date
  - Productivity effect: **Hedges' g = 0.33** — statistically significant but moderate
  - Gains **larger in lab settings**, smaller in real-world OSS/enterprise contexts
  - **No significant effect on learning** (g = 0.14) — raises concerns about long-term skill development
  - Confirms the pattern: AI helps speed, but the effect is more modest than vendor claims suggest
  - Complements Anthropic's skill formation study showing 17% comprehension reduction

  </details>

- 🟡 `[2026-04]` [Pragmatic Engineer AI Survey: 3 Developer Archetypes (900+ Respondents)](https://newsletter.pragmaticengineer.com/p/the-impact-of-ai-on-software-engineers-2026) - "Builders" debug AI slop, "Shippers" accumulate tech debt, "Coasters" generate low-quality code. EM and IC roles converging. Companies spending ~$200/mo per dev on AI tools, with some CTOs admitting budgets are unsustainable.

  <details><summary>Key findings — three archetypes</summary>

  - **900+ respondents** in latest Pragmatic Engineer survey
  - **"Builders"** spend more time debugging AI slop
  - **"Shippers"** move fast but accumulate tech debt faster
  - **"Coasters"** uplevel quickly but generate low-quality code
  - Engineer and EM roles converging as orchestration replaces hands-on coding
  - Companies spending **~$200/mo per dev** on AI tools; some CTOs admit budgets are unsustainable
  - ~30% of engineers hit AI tool usage limits regularly

  </details>

- 🟢 `[2025-07]` [METR: Experienced OSS Devs 19% Slower with AI](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/) - RCT finding experienced developers were slower. Influential but now being revised.

  <details><summary>Key findings</summary>

  - Randomized controlled trial, developers paid **$150/hr**
  - Tasks took **19% longer** with AI (confidence interval: +2% to +39%)
  - Workflow friction: prompting, reviewing, integrating AI suggestions
  - Developers **believed they were 20% faster** (they weren't)
  - *"The overhead of managing AI output exceeded the time saved"*

  </details>

- 🟢 `[2026-02]` [METR Update: We Are Changing Our Experiment Design](https://metr.org/blog/2026-02-24-uplift-update/) - Original slowdown likely reversed. Devs now refuse to work without AI, making measurement impossible.

  <details><summary>Key findings</summary>

  - New study (Aug 2025+): 57 developers, 143 repos, 800+ tasks at $50/hr
  - **Selection bias catastrophic:** 30-50% of devs decline to submit tasks to AI-disallowed condition
  - Returning devs from original study now show **18% speedup** (vs 19% slowdown before)
  - New developers show **4% speedup** (confidence interval: -15% to +9%)
  - Quote: *"My head's going to explode if I try to do too much the old fashioned way because it's like trying to get across the city walking when all of a sudden I was more used to taking an Uber"*
  - One developer **did not complete any tasks** assigned to AI-disallowed condition
  - Some devs run **multiple AI agents concurrently**, making time measurement unreliable
  - **Cultural tipping point:** can no longer construct valid without-AI baselines
  - Raw data: [github.com/METR](https://github.com/METR/Measuring-Late-2025-AI-on-OSS-Devs)

  </details>

- 🟢 `[2026-01]` [Harvard & Jellyfish: AI Makes Devs Faster, But Where's the Business Impact?](https://jellyfish.co/blog/harvard-jellyfish-ai-is-making-developers-faster/) - 100K engineers, 500 companies. Faster coding, no increase in features shipped.

  <details><summary>Key findings</summary>

  - Coding speed: ✅ up
  - Code quality: ✅ maintained
  - **Features shipped: ❌ no significant increase**
  - **Higher-value work: ❌ no observable shift**
  - Why: *"Coding isn't the bottleneck"* — requirements, design, review, testing, cross-team coordination are
  - AI-assisted PRs are **18% larger** on average
  - Companies playing it safe — pointing AI at bugs/maintenance, not customer-facing features

  </details>

- 🟢 `[2026-04]` [arXiv: AI Assistance Reduces Persistence and Hurts Independent Performance](https://arxiv.org/abs/2604.04721) - Empirical study (Liu et al.) finds developers using AI chatbots give up faster on hard problems and underperform on follow-up independent tasks. Adds to evidence of AI-induced cognitive dependency.

- 🟢 `[2026-02]` [FORGE '26: GenAI Impact on Agile Teams (13-month longitudinal)](https://arxiv.org/html/2602.13766v1) - Performance ↑ and Efficiency ↑ while Activity stays flat. AI increases value density, not volume.

  <details><summary>Key findings</summary>

  - Large IT consulting firm (300K+ employees, 150+ countries)
  - Used **SPACE framework** across 13 months pre/post AI adoption
  - **Performance ↑ and Efficiency ↑ while Activity stayed FLAT**
  - AI increases "value density" of work, not volume
  - Devs focus more on complex reasoning/validation, less on routine coding
  - Single-metric studies (lines of code, PRs) miss this completely

  </details>

- 🟡 `[2025-11]` [Harness: The AI Velocity Paradox](https://www.harness.io/) - 67% of teams report "balloon effect" — faster coding inflates downstream bottlenecks.

- 🔵 `[2025-10]` [Logilica: The Shifting Bottleneck](https://www.logilica.com/) - 77% of merges still require human decision-making.

- 🟡 `[2026-03]` [Multitudes: The Struggle to Prove AI Productivity Gains](https://leaddev.com/ai/the-struggle-to-prove-ai-productivity-gains) - 700+ engineering professionals: 75% struggle to measure AI's impact. 60% cite productivity as expected outcome. 40% feel board-level pressure to adopt, 39% to demonstrate improvement. Traditional metrics break down with AI.

- 🟡 `[2026-02]` [Faros AI Field Study: 91% PR Review Time Increase](https://medium.com/@fernando.garcia.varela/ai-coding-taming-the-new-pet-4e85bb2c0967) - 10K+ devs, 1,255 teams: +21% tasks, +98% PRs merged, but +91% review time, +9% bugs/dev, +154% PR size. Bottleneck moved downstream.

  <details><summary>Key findings & CTO experience report</summary>

  - **Faros AI field study** — one of the most rigorous large-scale analyses available
  - 10,000+ developers across 1,255 real engineering teams
  - High-AI-adoption teams: **+21% tasks completed, +98% more PRs merged**
  - But: **+91% PR review time, +9% bugs per developer, +154% avg PR size**
  - **The bottleneck didn't disappear — it moved downstream**
  - CTO experience report identifies **novel failure modes:**
    - Parallel AI sessions creating "quantum state" bugs (code integrates cleanly but behaves incorrectly)
    - Architectural drift across stateless sessions
    - Non-serializable cognitive commits (AI reasoning vanishes when session ends)
  - Quote: *"Your team can be confidently, productively wrong — and the feedback loop is long enough that nobody notices until a client does"*
  - METR devs estimated they were 20% faster when they were actually 19% slower — same overconfidence pattern

  </details>

- 🟢 `[2026-03]` [Harvard/HBS: The GenAI Wall Effect](https://www.library.hbs.edu/working-knowledge/gen-ai-boosts-productivity-but-cant-turn-novices-into-experts) - AI helps adjacent professionals perform unfamiliar tasks but hits a wall with distant outsiders. Marketing specialists matched web analysts with AI help; software developers lagged 13%. "Knowledge distance" determines AI benefit — AI is a skill amplifier, not a skill equalizer.

  <details><summary>Key findings</summary>

  - **Harvard Business School** (Bojinov, McFowland) + Stanford — experiment at IG Group (derivatives trader)
  - 78 workers across 3 groups: web analysts (insiders), marketing specialists (adjacent), technology specialists (distant)
  - All groups used AI to write investing articles for IG's website
  - Marketing specialists with AI scored **3.92/5** — matching web analysts at **3.96/5**
  - Technology specialists with AI scored only **3.42/5** — **13% below** despite identical AI access
  - AI helped equally with ideation/organization; the gap emerged in execution quality
  - **"Knowledge distance" is key:** adjacent skills transfer well with AI; distant skills hit a wall
  - Confirms the expertise paradox: *"AI makes you feel like you can do anything. But can you do it as well as people whose job it is?"*
  - Implications for job design: AI enables horizontal movement for adjacent roles, not universal skill transfer

  </details>

- 🟢 `[2026-02]` [Russinovich & Hanselman: Redefining Software Engineering for AI (ACM)](https://dl.acm.org/doi/10.1145/3779312) - Microsoft Azure CTO + VP: AI gives seniors "boost" and juniors "drag." Agents exhibit intern-like behaviors (thread.sleep for race conditions, hiding crashes).

  <details><summary>Key findings</summary>

  - **Mark Russinovich (CTO Azure) + Scott Hanselman (VP Dev Community)** — ACM opinion paper
  - AI agents exhibit **"intern-like behaviors":**
    - Inserting `thread.sleep()` to "fix" race conditions
    - Dismissing crashes and hangs as not relevant
    - Leaving debug code behind
    - Duplicating common code throughout codebase
    - Making code work for specific tests but not generally
  - Senior engineers get **"AI boost"**, early-in-career (EiC) get **"AI drag"**
  - Russinovich: *"This is a hot topic in all our customer engagements — they all say they see it at their companies"*
  - Proposal: **"preceptor-based organization"** where seniors explicitly mentor juniors paired with AI
  - Universities need classes where **using AI is considered cheating**
  - Microsoft starting internal pilot on preceptor model
  - Companion [Harvard study](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5425555): junior employment declines sharply at AI-adopting firms

  </details>

### Organizational Impact

- 🟠 `[2026-05]` [Coinbase Lays Off 14%, CEO Cites AI Productivity](https://www.ai-supremacy.com/p/is-generative-ai-creating-more-jobs-than-it-disrupts-early-2026) - CEO Brian Armstrong: *"engineers use AI to ship in days what used to take a team weeks."* Adds to the pattern of tech companies invoking AI productivity to justify headcount reductions — raises **AI-washing** concerns (real productivity vs. cover for restructuring).

- 🟡 `[2026-05]` [Google Pilots Gemini in Software Engineering Interviews](https://www.businessinsider.com/google-job-interview-software-engineers-ai-assistant-coding-2026-5) - Google will allow candidates to use Gemini AI during **"code comprehension" rounds** for junior/mid-level engineering roles in a limited US pilot. Signals AI-augmented coding becoming a **baseline professional skill**, not a crutch. Reshapes what hiring evaluates: judgment with AI, not coding-without-AI.

- 🟡 `[2026-05]` [BLS Projects 15% SWE Job Growth Through 2034 — But "Programmer" Roles Decline 6%](https://en.wikipedia.org/wiki/AI_boom) - Bureau of Labor Statistics: software engineering **+15%** (~129K openings/year) vs **−6%** for "computer programmer" (task-based) roles. Tactical coding shrinks, strategic engineering grows — the role bifurcation is now in official labor stats.

- 🟡 `[2026-05]` [Intellias: Only 41% of GenAI POCs Make It to Production](https://lesechos-comfi.lesechos.fr/press-release/intellias-nasdaq-turning-ai-into-results-remains-a-challenge-for-enterprises-intellias-helps-to-make-a-step-from-experimentation-to-autonomous-ai-operations-at-scale-wgafhFeYzpD) - Nearly half of CIOs report AI initiatives **performing below expectations**. Matches Gartner's finding that **50%+ of GenAI POCs are abandoned** post-pilot due to data-quality and ROI gaps. The production gap remains the central enterprise challenge.

- 🟡 `[2026-04]` [CNN: The Demise of Software Engineering Jobs Has Been Greatly Exaggerated](https://www.cnn.com/2026/04/08/tech/ai-software-developer-jobs) - Engineers doing less routine coding, more oversight of AI agent swarms. Time shifts to architecture, design, and orchestration. Reframes the narrative from displacement to transformation.

- 🟡 `[2026-04]` [Gartner: Only 28% of AI Infrastructure Projects Fully Pay Off](https://www.gartner.com/en/newsroom/press-releases/2026-04-07-gartner-says-artificial-intelligence-projects-in-infrastructure-and-operations-stall-ahead-of-meaningful-roi-returns) - Survey of 782 I&O managers: 20% failure rate, 57% experienced at least one AI project failure. Skill gaps (38%) and poor data quality (38%) are top causes. GenAI succeeds mainly in ITSM and cloud ops (53% success).

- 🟡 `[2026-04]` [Gartner: Successful AI Orgs Invest 4x More in Foundations](https://techedgeai.com/gartner-says-organizations-with-successful-ai-initiatives-invest-up-to-four-times-more-in-data-and-analytics-foundations/) - The differentiator isn't the AI model — it's the foundational investment. Organizations with successful AI initiatives invest up to 4x more in data quality, governance, and change management.

  <details><summary>Key findings</summary>

  - Only **28%** of AI infrastructure and operations projects delivered full expected returns
  - **20%** failed outright, and **57%** of leaders saw at least one project fail
  - Top blockers: **skill gaps** and **poor data quality** (both 38%)
  - Best-performing use cases were mature operational domains like **ITSM** and **cloud ops**

  </details>

- 🟠 `[2026-02]` [Bloomberg: The Great Productivity Panic of 2026](https://www.bloomberg.com/news/articles/2026-02-26/ai-coding-agents-like-claude-code-are-fueling-a-productivity-panic-in-tech) - AI coding agents fueling anxiety across tech. 16% decline in junior SWE job postings.

  <details><summary>Key findings</summary>

  - AI coding agents (Claude Code, Cursor, Codex) fueling **anxiety, not just productivity**
  - **16% decline in junior SWE job postings**
  - Production engineers push back: *"debugging AI-generated code takes 3x longer"*
  - Goldman Sachs values AI coding tool market at **$45 billion**
  - Cursor announced major update as market accelerates
  - Governance/audit of autonomous agent commits remains **unsolved**

  </details>

- 🔵 `[2026-02]` [Karpathy: Programming "Unrecognizable" Since December](https://x.com/karpathy/status/2026731645169185220) - AI agents crossed from unreliable to functional in Dec 2025. Weekend projects → 30 minutes.

  <details><summary>Key findings</summary>

  - Karpathy drew **a hard line in time**: December 2025 as the month agents crossed from unreliable to functional
  - Example: handed agent a single dense prompt (SSH setup, model benchmarking, video analysis dashboard, system services) — **agent ran 30 minutes, finished everything**
  - *"All of this could easily have been a weekend project just three months ago"*
  - Coined **"agentic engineering"** as the new practice
  - On expertise: *"At the top tiers, deep technical expertise may be even more of a multiplier than before"*
  - *"It's not magic, it's delegation"* — people who decompose work well for junior engineers decompose it well for agents
  - DHH agreed: *"Biggest and fastest change in the 40 years I've tried to make computers do my bidding"*
  - **Pushback from production engineers:**
    - Daniel Ost: *"When AI fails, debugging takes 3x longer because you're trying to understand code you never wrote"*
    - Yacine Mahdid: *"You can outsource your thinking but you cannot outsource your understanding"*
    - Leandro Alvarenga: governance, sandboxing, audit of autonomous commits — **nobody offered answers**

  </details>

- 🔵 `[2026-02]` [Forrester: Takeaways from Future of Software Retreat](https://www.forrester.com/blogs/takeaways-from-the-future-of-software-development-retreat-just-because-you-can-doesnt-mean-youre-ready-to/) - "Just because you can doesn't mean you should." Mid-career engineers at most risk.

  <details><summary>Key findings</summary>

  - **"Gas Town" existential crisis** — when appgen engines outperform dev squads, what's left?
  - **$300K in Claude API calls** to generate an app that generates apps — gurus unfazed, *"costs will come down"*
  - *"Just because you can doesn't mean you should"* — quality/safety concerns reasserted dominance
  - **Nobody worried about AI economics** — *"we'll build more nuclear reactors"* 🤷
  - Mid-career engineers identified as most at risk (not juniors, not seniors)

  </details>

- 🟡 `[2025-02]` [Dan Shapiro: 5 Levels of AI Coding](https://danshapiro.com/) - L0 (manual) → L5 (dark factory). StrongDM operates at L4.

  <details><summary>Key findings</summary>

  - **L0:** Manual coding (traditional)
  - **L1:** AI-assisted (autocomplete, suggestions)
  - **L2:** AI-augmented (significant AI code generation with human review)
  - **L3:** AI-led (AI does most coding, human architects and reviews)
  - **L4:** AI-driven (PM validates behavior, not code) — **StrongDM operates here**, $1000/day tokens per engineer
  - **L5:** Dark factory (fully autonomous code generation and deployment)
  - **Attractor repo pattern:** NLSpecs only, no code — feed to coding agent
  - **Key insight:** Validation is the hard problem (external scenario holdouts + Digital Twin Universe)

  </details>

- 🟢 `[2026-02]` [Harvard: Junior Employment Declines at AI-Adopting Firms](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5425555) - Junior hiring drops sharply at firms adopting AI; senior employment unchanged. Referenced by Microsoft ACM paper.

- 🔵 `[2026-02]` [Pragmatic Summit: Mid-Level Engineers' Quiet Crisis](https://newsletter.pragmaticengineer.com/p/the-future-of-software-engineering-with-ai) - Eng leaders discuss behind closed doors: juniors adapt faster to AI, seniors have experience, mid-levels squeezed from both sides.

- 🟡 `[2026-04]` [Kotak: Anthropic Mythos Poses 3–3.5% Growth Headwind to IT Services](https://economictimes.indiatimes.com/tech/artificial-intelligence/ai-models-like-anthropics-mythos-pose-disruption-risks-to-indias-it-services-growth-kotak/articleshow/130209486.cms) - Kotak Institutional Equities warns that Mythos's "step-jump in benchmark performance across software engineering tasks" raises near-to-medium-term disruption risks for India's IT services sector, especially application development.

- 🟡 `[2026-04]` [Entry-Level Dev Hiring Collapsed 67%](https://medium.com/@speed_enginner/i-spent-a-week-researching-the-2025-26-coding-job-market-heres-what-s-actually-happening-6894e0afbd13) - Analysis finds AI has made junior developers uneconomical for many organizations, accelerating the shift toward senior+AI hybrid teams.

- 🔵 `[2026-04]` [HumanX Conference: "Models Are Good Enough, Your Org Isn't"](https://www.techbyjohan.com/tech-insights-2026-week-16/) - Key quote from May Habib (Writer CEO): transformation requires end-to-end workflow authority, not just bolting AI onto existing processes. Francis deSouza (Google Cloud COO): "A thousand flowers blooming often ends up with a thousand dead flowers."

- 🟢 `[2026-04]` [Anthropic: Labor Market Impacts of AI — "Observed Exposure" Metric](https://www.anthropic.com/research/labor-market-impacts) - Introduces "observed exposure," combining theoretical LLM capability with real-world usage data. Actual AI coverage remains a fraction of theoretical capability. No systematic unemployment increase in highly-exposed occupations yet, but suggestive evidence of slowed hiring of younger workers.

  <details><summary>Key findings</summary>

  - New metric: **"observed exposure"** — combines theoretical LLM capability with real-world usage data
  - AI is **far from reaching theoretical capability**; actual coverage remains a fraction of feasible
  - **No systematic unemployment increase** for highly-exposed workers since late 2022
  - Suggestive evidence that **hiring of younger workers has slowed** in exposed occupations
  - Challenges binary "will AI take jobs?" framing with nuanced usage-adjusted measurement

  </details>

- 🟡 `[2026-04]` [Oracle Lays Off ~30K Globally, Partly AI-Driven](https://www.newslaundry.com/2026/04/27/will-ai-replace-me-anxiety-grips-tech-workers-amid-mass-layoffs-slowing-recruitment) - Bloomberg-sourced: Oracle cut 10-12K in India alone (Mar 31), citing cash crunch from AI data center investment and reduced need for certain roles due to AI. Part of a broader wave including Meta's April 23 cuts.

- 🟢 `[2026-04]` [Management Science: Junior Devs Gain Most from AI Coding Tools](https://en.wikipedia.org/wiki/AI_boom) - Peer-reviewed study found less experienced developers have higher AI adoption rates and greater productivity gains than seniors. Suggests AI is an equalizer more than an amplifier of existing skill — contrasting the CSH/Science finding.

- 🟠 `[2026-04]` [Univ. Innsbruck: AI Is "No Fairy Dust" — Software Engineering Live Workshop](https://www.uibk.ac.at/en/newsroom/2026/software-development-in-the-ai-transformation/) - ~50 experts from academia/industry concluded: AI code generation is gaining performance but cannot fully automate SW dev. Architecture decisions, requirements, testing remain human tasks. Developer roles shifting from coding → orchestrating, evaluating, and controlling AI systems.

- 🟠 `[2026-05]` [HBR: From AI Experimentation to Transformation](https://hbr.org/2026/04/how-to-move-from-ai-experimentation-to-ai-transformation) - Harvard Business Review notes GenAI has "sprinted from novelty to boardroom priority" but not every company is realizing bottom-line improvement. Frames the shift from experimentation to transformation as requiring structural org changes, not just tool adoption.

- 🟠 `[2026-05]` [Alenezi: "Rethinking SE for Agentic AI"](https://arxiv.org/abs/2604.10599) - Argues code is transitioning from scarce, crafted artifact to abundant, disposable commodity. SE must reorganize around 3 competencies: orchestration of multi-agent systems, verification of AI outputs, and structured human-AI collaboration. Proposes changes to curricula, tooling, lifecycle processes, and governance.

- 🔵 `[2026-05]` [Chamath Palihapitiya: Faster Coding Without Captured Reasoning Is Dangerous](https://www.benzinga.com/markets/tech/26/05/52206777/openais-greg-brockman-says-ai-went-from-writing-20-to-80-of-code-in-a-single-month) - Argues the industry is over-focusing on speed while losing the "why" behind engineering decisions — context capture and decision rationale must accompany AI-generated code.

- 🟡 `[2026-04]` [Gartner Apr 2026: Only 39% Believe AI Improves Financial Performance](https://www.dqchannels.com/news/gartner-ai-report-april-2026-reveals-why-most-ai-investments-still-fall-short-11752572) - Successful orgs invest 4× more in foundations (data quality, governance, talent, change mgmt). Only 23% of leaders confident in AI governance/security. Recommends shift to AI-first mindset and dynamic governance models.

---

## SDLC Phase: Requirements & Design

### AI-Assisted Requirements Engineering

*Resources on using AI to improve requirements gathering, user story writing, and spec quality.*

<!-- Entries welcome: AI tools for requirements, NLP for user stories, automated acceptance criteria -->

### Spec-Driven Development

*The shift from code-first to spec-first development, where specifications become the highest-leverage artifact.*

- 🟢 `[2026-05]` ["Triadic Data for Long-Horizon SWE Agents" (arXiv)](https://arxiv.org/abs/2605.02244) - Argues current SWE-agent benchmarks are saturated on short-horizon tasks while failing senior-level work (multi-week, ambiguous-spec). Proposes "triadic data" — synchronized capture of human-human conversations, human-AI sessions, and cross-functional deliverables — as the missing training substrate. Includes a 4-tier evidence framework for corpus quality.

  <details><summary>Key contributions</summary>

  - Current benchmarks **saturated on short-horizon tasks** but fail senior-level work (multi-week, ambiguous-spec)
  - Proposes **"triadic data"**: synchronized capture of human-human conversations, human-AI sessions, and cross-functional deliverables
  - Includes a **4-tier evidence framework** for corpus quality
  - Claims **12–18 months** to build with existing methods
  - Signals the field's pivot from "can agents fix bugs?" to "can agents do senior engineering work?"

  </details>

- 🔵 `[2026-02]` [McKinsey/QuantumBlack: Agentic Workflows for Software Development](https://medium.com/quantumblack/agentic-workflows-for-software-development-dc8e64f4a79d) - Field-tested two-layer pattern: deterministic orchestration + bounded agent execution. Spec-driven development (SDD) eliminates ad hoc prompts.

  <details><summary>Key architecture pattern</summary>

  - **The problem:** copilots make individual devs faster, but enterprise efficiency improvement from idea to live feature is "less significant" — handoffs are where context dies
  - **Two-layer model:**
    - **Orchestration layer:** deterministic, rule-based workflow engine. Enforces phase transitions, manages dependencies, tracks artifact state via frontmatter
    - **Execution layer:** bounded agent tasks within strict conventions
  - **Why agents shouldn't orchestrate themselves:** on larger codebases, agents "routinely skipped steps, created circular dependencies, or got stuck in analysis loops"
  - **Folder structures and naming conventions** create machine-readable workflows — the directory IS the state machine
  - **Each artifact has a state machine** (draft → in-review → approved → complete) stored in frontmatter
  - *"AI assistants can accelerate the work within a phase of the SDLC as long as you don't expect them to fix the boundaries between them"*

  </details>

- 🔵 `[2026-02]` [Microsoft: AI-Led SDLC with Azure and GitHub](https://techcommunity.microsoft.com/blog/appsonazureblog/an-ai-led-sdlc-building-an-end-to-end-agentic-software-development-lifecycle-wit/4491896) - End-to-end agentic SDLC using GitHub Spec Kit, Copilot agents, and Azure SRE agents. University-style requirements translation now done by agents in minutes.

  <details><summary>Key insights</summary>

  - **GitHub Spec Kit** (open-source, 2025): places specification at the center of engineering process — specs drive implementation, checklists, and task breakdowns
  - Manual requirements translation (2-year university module) — now handled by agents generating comprehensive lists, service blueprints, and code scaffolds
  - **"Breakpoints are dead"** — Azure SRE agents transform debugging from stepping through code to conversational log analysis
  - **Cognitive load concern:** if AI handles all "donkey work," engineers only deal with the most complex problems — potential for burnout
  - **Developer skills question:** will developers/architects lose ability to innovate as AI handles more advanced tasks?
  - **Pragmatic position (early 2026):** "We are on the precipice" of fully agentic SDLCs, but not there yet

  </details>

- 🔵 `[2026-02]` [ThoughtWorks Retreat: EARS Syntax & State Machines for AI Specs](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Structured spec formats (EARS, decision tables) rediscovered as precision input for AI agents.

- 🔵 `[2026-04]` [Martin Fowler / Thoughtworks: Structured Prompt-Driven Development (SPDD)](https://martinfowler.com/articles/structured-prompt-driven/) - Introduces SPDD, treating prompts as first-class delivery artifacts with the REASONS Canvas (Requirements, Entities, Approach, Structure, Operations, Norms, Safeguards). Key insight: individual speed improves with AI but doesn't automatically translate to system-level throughput.

  <details><summary>Key concepts — the REASONS Canvas</summary>

  - **SPDD** treats prompts as **first-class delivery artifacts**, not throwaway instructions
  - **REASONS Canvas** — structured framework for prompt engineering at team scale:
    - **R**equirements, **E**ntities, **A**pproach, **S**tructure, **O**perations, **N**orms, **S**afeguards
  - Key insight: individual speed improves with AI but doesn't automatically translate to system-level throughput
  - Analogy: *"like buying a Ferrari on muddy roads"* — org-level friction dominates tool-level speed
  - Complements McKinsey/QuantumBlack SDD pattern with a more practitioner-friendly framework

  </details>

- 🔵 `[2025-08]` [Attractor: NLSpecs-Only Repo Pattern](https://danshapiro.com/) - Repository containing only natural language specs, no code. Code generated entirely by agents.

<!-- Entries welcome: EARS tools, structured requirement formats, spec-to-code pipelines -->

### Architecture & System Design

*AI-assisted architecture decisions, design review, and system modeling.*

- 🟢 `[2026-05]` [Architectural Constraint Alignment for AI-Assisted Development (CAiSE'26)](https://arxiv.org/abs/2605.04973) - RAG + agentic clarification loops enforce architectural constraints, infrastructure dependencies, and org standards during AI code generation. Results show improved consistency and deployability vs general-purpose codegen.

  <details><summary>Key findings</summary>

  - Addresses AI tools' **lack of awareness** of architectural constraints, infrastructure dependencies, and org standards during rapid prototyping
  - Proposes **retrieval-augmented scaffolding** combining platform-based code generation with agentic clarification loops
  - Results: improved **consistency and deployability** vs general-purpose AI codegen
  - To appear at **CAiSE'26** — signals growing academic attention to architecture-aware AI coding
  - Practical implication: AI coding tools need architectural context, not just code context

  </details>

---

## SDLC Phase: Development

### Code Generation & Completion

*Tools and models for code generation, autocomplete, and inline assistance.*

- [GitHub Copilot](https://github.com/features/copilot) - AI pair programmer with autocomplete-style suggestions.
- [Cursor](https://www.cursor.sh/) - Code editor built for AI-first development.
- [Cline](https://cline.bot/) - Autonomous coding agent for CLI and editor.
- [Continue](https://continue.dev/) - Open source autopilot for VS Code and JetBrains.
- [Tabnine](https://www.tabnine.com/) - Code completions trained on your codebase.
- [Amazon Q Developer](https://aws.amazon.com/q/developer/) - AWS assistant for software development.
- [Sourcegraph Cody](https://about.sourcegraph.com/cody) - Codebase-aware completions and edits.

### Agentic Coding

*Autonomous AI agents that can plan, execute, and iterate on multi-file coding tasks.*

- [Claude Code](https://www.anthropic.com/claude-code) - Agentic coding tool in the terminal. ~4% of GitHub commits by Feb 2026.
- [OpenAI Codex](https://openai.com/index/codex/) - Cloud-based coding agent with sandbox.
- [Aider](https://aider.chat) - Terminal-based pair programming with git integration.
- [Windsurf](https://windsurf.com/) - IDE optimized for agent-developer collaboration.
- 🔵 `[2026-03]` [AI Agent Tools Study: 177K Tools, Software Development Dominates](https://www.coffeefranchisehub.com/archives/47192) - Analysis of Model Context Protocol repositories (Nov 2024–Feb 2026). Software development = **67% of all AI agent tools**, **90% of downloads**. Action tools (file/system modification) surged from 27% → 65%. Shift from passive data gathering to active environment manipulation.

  <details><summary>Key findings</summary>

  - Analyzed **177,000+ AI agent tools** created between November 2024 and February 2026
  - Data source: **Model Context Protocol repositories** tracking how AI agents interact with external tools
  - **Software development tools: 67% of all AI agent tools, 90% of total downloads** — massively dominant category
  - **Action tools** (directly modifying files, systems, emails, platforms) grew from **27% → 65%** share over 16 months
  - Shift from passive AI (perception/data gathering) → **active AI** (environment manipulation)
  - Most action tools classified as **medium-risk operations**; some involve high-risk activities (financial transactions)
  - Tool categories: **perception** (data gathering), **reasoning** (analysis), **action** (modification)
  - Underscores AI agents' crucial role in software development workflows

  </details>

- 🔵 `[2026-04]` [InfoQ: Birgitta Böckeler — State of Play: AI Coding Assistants](https://www.infoq.com/presentations/ai-coding-assistants/) - QCon talk covering the evolution from autocomplete to agents. Key themes: context engineering maturation (rules → skills → subagents), progressive context loading, and "harness engineering" as a new senior developer competency.

  <details><summary>Key insights</summary>

  - The frontier moved from **autocomplete** to **agent supervision**
  - Context engineering is maturing from static prompts to **skills, subagents, and staged context loading**
  - "**Harness engineering**" becomes a distinct competency: shaping the environment around the model, not just prompting it

  </details>

- 🔵 `[2026-04]` [Shopify VP Engineering: AI-First Engineering Playbook](https://newsletter.pragmaticengineer.com/p/shopifys-ai-first-engineering-playbook) - Farhan Thawar reports ~20% productivity gain. Key insight: standardize infrastructure (LLM proxy), not tools. Cultural adoption via "make it look easy" beats top-down mandates. Non-engineers (sales, finance) creating custom software.

  <details><summary>Key insights</summary>

  - Reported productivity gain around **20%**, but the bigger story is operating model change
  - Shopify standardized the **infrastructure layer** (proxy, shared plumbing), while letting teams choose surface tools
  - Adoption spread through visible practitioner wins, not only mandates
  - AI software creation expanded beyond engineering into **sales and finance** workflows

  </details>

- [Plandex](https://github.com/plandex-ai/plandex) - Multi-file task engine with version control.
- [Kiro](https://kiro.dev/) - IDE for spec-driven development with AI agents.
- 🔵 `[2026-03]` [JetBrains Central: Open System for Agentic Software Development](https://blog.jetbrains.com/blog/2026/03/24/introducing-jetbrains-central-an-open-system-for-agentic-software-development/) - Control and execution plane for agent-driven software production. Connects JetBrains IDEs, third-party IDEs, Claude Agent, Codex, Gemini CLI. Provides governance, cost attribution, and shared semantic context across repos. JetBrains AI Pulse survey: 90% of 11K devs use AI at work, 22% use coding agents, 66% of companies plan adoption within 12 months — but only 13% use AI across the full SDLC.
- 🟡 `[2026-04]` [Microsoft Copilot 2026: Agentic "Work IQ" Layer for Enterprise](https://windowsnews.ai/article/microsoft-copilots-2026-strategy-agentic-work-layer-enterprise-licensing-and-governance-challenges.413548) - Microsoft pivots Copilot from chatbot to agentic work layer with new licensing models and governance. Agents now orchestrate across M365 apps, turning intent into execution without context-switching.

- 🟡 `[2026-04]` [Gartner: First Hype Cycle for Agentic AI](https://xpander.ai/blog/gartner-hype-cycle-for-agentic-ai-what-it-means-for-ai-agent-development-platforms) - AI agent development platforms placed at "Peak of Inflated Expectations" with High benefit rating, 2–5 year timeline to mainstream. Signals agentic coding workflows moving from experimentation to enterprise strategy.

- 🔵 `[2026-04]` [Boris Cherny (Anthropic/Claude Code) on Lenny's Podcast: "Coding Is Being Solved"](https://medium.com/@prock13/the-future-of-software-engineering-in-an-ai-native-world-709e14696110) - VP Engineering recap argues we're in a "printing press moment" — value shifting from writing code to system design, problem definition, and AI orchestration. Engineers who think in systems are thriving.

- 🔵 `[2026-04]` [Kent Beck — "Nobody Wants Agents"](https://tidyfirst.substack.com/p/genie-lessons-nobody-wants-agents) - Working with Augment Code's multi-agent system (coordinator + implementer + verifier), Beck argues the industry confuses multi-agent orchestration with outcome-orientation. Developers want results, not coordination overhead. Flags "multiplayer" (multiple humans steering AI together) as the unsolved frontier.

- 🔵 `[2026-05]` [Martin Fowler — Guides & Sensors for AI Agents](https://martinfowler.com/recent-changes.html) - Proposes that reliable agents = **feedforward Guides** (constraints, examples, harnesses) + **feedback Sensors** (linters, tests, telemetry) wired into a tight loop. An emerging architectural primitive: agents need both *prescription* and *observation*, not just clever prompts.

- 🔵 `[2026-05]` [Martin Fowler — The Feedback Flywheel](https://martinfowler.com/) - Pattern for converting **individual AI interactions into team-wide learning**. Context management is reframed as the new core craft — capturing and replaying prompts/decisions so the org compounds, not just the individual.

- 🔵 `[2026-05]` [Pragmatic Engineer: Fowler & Beck on Cycles of Disruption in Tech](https://newsletter.pragmaticengineer.com/p/cycles-of-disruption-in-the-tech) - Both Fowler and Beck call the AI shift **larger than anything prior**. Beck's "Genies" framing: LLMs as collaborators pushing teams **back to XP-style small, customer-proximate practice** — tight loops, frequent verification, working software over big upfront design.

- 🔵 `[2026-05]` [Ingo Eichhorst — State of AI Coding Efficiency 2026](https://ingoeichhorst.medium.com/state-of-ai-coding-efficiency-2026-1abfa0ab7434) - Practitioner synthesis: **skill-of-prompting is now the differentiator**, not whether a team uses AI. *"AI-assisted coding is a skill, not a tool toggle"* — frames the next phase as **deliberate AI craftsmanship** vs. ambient adoption.

- 🔵 `[2026-04]` [Martin Fowler — "Harness Engineering"](https://martinfowler.com/articles/exploring-gen-ai/harness-engineering-memo.html) - Analyzes OpenAI's write-up on building a 1M+ LOC product with zero manually typed code. Deterministic linters, structural tests, context engineering, and periodic "garbage collection" agents. Sees harnesses as the future of service templates. Notes a gap in behavioral verification.

  <details><summary>Key insights</summary>

  - Analyzes how OpenAI built a **1M+ LOC product with zero manually typed code**
  - Key pattern: **deterministic harnesses** — linters, structural tests, context engineering
  - Periodic **"garbage collection" agents** clean up accumulated AI debt
  - Fowler sees harnesses as the **future of service templates**
  - Gap identified: **behavioral verification** still needs human judgment
  - Harness engineering = shaping the environment around the model, not just prompting it

  </details>

- 🟡 `[2026-05]` [OpenAI Symphony: Issue Trackers as Agent Control Planes](https://www.infoworld.com/article/4164173/openais-symphony-spec-pushes-coding-agents-from-prompts-to-orchestration.html) - Open-source spec that turns issue trackers (e.g. Linear) into control planes for Codex coding agents. Internal teams saw PRs land 500% more in first 3 weeks. Shifts agents from interactive prompting to autonomous orchestration with CI monitoring, rebasing, and conflict resolution.

  <details><summary>Key findings</summary>

  - Turns **issue trackers** (Linear, GitHub Issues) into **control planes** for coding agents
  - Internal OpenAI teams saw PRs land **500% more** in first 3 weeks
  - Agents autonomously handle **CI monitoring, rebasing, and conflict resolution**
  - Shifts paradigm from interactive prompting to **autonomous orchestration**
  - Open-source spec — signals infrastructure-level investment in agentic coding workflows

  </details>

- 🔵 `[2026-05]` [Karpathy at AI Ascent 2026: From Vibe Coding to Agentic Engineering](https://www.franksworld.com/2026/05/01/andrej-karpathy-on-the-evolution-from-vibe-coding-to-agentic-engineering/) - Described "Software 3.0" where context/prompts replace traditional code. Hasn't personally typed code since December. AI automation accelerates fastest where output is easily verifiable, producing "jagged" capability profiles across tasks.

- 🔵 `[2026-05]` [OpenAI's Brockman: AI Coding Jumped from 20% → 80% in One Month](https://www.benzinga.com/markets/tech/26/05/52206777/openais-greg-brockman-says-ai-went-from-writing-20-to-80-of-code-in-a-single-month) - At Sequoia Capital, Brockman said agentic coding tools went from writing 20% to 80% of developer code within December alone. Human sign-off before merge remains mandatory at OpenAI.

- 🟡 `[2026-05]` [Delivery Hero Herogen: Autonomous AI Agent = ~130 Senior Engineers](https://www.yuyjo.com/archives/62946) - In-house "council of agents" (multi-model evaluation) autonomously writes, tests, and submits code. 85% PR acceptance rate, 100+ code changes merged/day, ~250K manual hours saved annually. 18% of engineering workforce using it, targeting 20% of all code change requests by year-end.

  <details><summary>Key findings</summary>

  - Uses a **"council of agents"** — multi-model evaluation for quality
  - **85% PR acceptance rate**, 100+ code changes merged/day
  - **~250K manual hours saved annually** — equivalent to ~130 senior engineers
  - Currently **18% of engineering workforce** using it
  - Targeting **20% of all code change requests** by year-end

  </details>

- 🔵 `[2026-05]` [Augment Code Launches "Intent" — Spec-Driven Agentic IDE](https://www.augmentcode.com/product/intent) - New developer workspace where agents are coordinated around living specs with isolated workspaces. Signals market moving from autocomplete-style copilots toward architecture-first, intent-driven development.

- 🔵 `[2026-05]` [LangChain/Cisco: Agentic Engineering with Agent Swarms](https://www.langchain.com/blog/agentic-engineering-redefining-software-engineering) - Cisco engineers publish a reference architecture for multi-agent coordinated software delivery using LangGraph/LangSmith. Shift from "write code faster" to "move software through the system faster and safely." Agents modeled as team members with defined responsibilities and shared context.

- 🟡 `[2026-04]` [GitLab + AWS: Agentic DevSecOps via Bring Your Own Model](https://www.stocktitan.net/news/GTLB/git-lab-collaborates-with-aws-to-bring-agentic-dev-sec-ops-to-n87kz4d9bnjq.html) - GitLab Duo Agent Platform routes inference through Amazon Bedrock — no new vendor onboarding. Keeps source code and inference in customer AWS environments. Key signal: AI agents generating enough code/MRs that governance tooling is now a requirement.

- 🔵 `[2026-04]` [Microsoft: Getting Started with Agentic DevOps](https://devblogs.microsoft.com/all-things-azure/getting-started-with-agentic-devops-part-1-foundations/) - Introduces Agentic DevOps — AI agents working across the full SDLC (planning, coding, testing, deployment, ops), moving from suggestions to end-to-end task execution with human approval.

- 🔵 `[2026-04]` [OpenAI Agentic Engineering Case Study: Codex App in Weeks](https://www.techbyjohan.com/tech-insights-2026-week-17/) - OpenAI rebuilt their desktop app as unified React/TypeScript codebase. Full feature parity in ~2 months for 3M users using agentic coding workflows. Makes the case for consolidating multi-platform codebases as AI makes unified stacks dramatically more efficient.

- 🔵 `[2026-04]` [OpenAI Agentic Engineering Case Study: Codex App Rebuilt in Weeks](https://www.techbyjohan.com/tech-insights-2026-week-17/) - OpenAI rebuilt their desktop app in React/TypeScript as a unified codebase using agentic coding workflows. Full feature parity for 3M users achieved in ~2 months. Makes the case for consolidating multi-platform codebases as AI makes unified stacks dramatically more efficient.

- 🔵 `[2026-05]` [Simon Willison: Vibe Coding and Agentic Engineering Are Converging](https://simonwillison.net/2026/May/6/vibe-coding-and-agentic-engineering/) - Even experienced engineers are no longer reviewing every line of AI-generated code, blurring the line between "vibe coding" and responsible agentic engineering. Argues the key question is trust calibration — treating AI output like code from another team. 650+ HN points, 725 comments.

  <details><summary>Key insights</summary>

  - Even **disciplined practitioners** admit they're lowering code review intensity on AI output
  - The boundary between "vibe coding" (no review) and "agentic engineering" (supervised) is **collapsing in practice**
  - Key question: **trust calibration** — treat AI output like code from a capable but fallible teammate
  - 650+ HN points with 725 comments — struck a nerve across the industry
  - Makes the accountability and quality assurance questions **increasingly urgent**

  </details>

- 🟢 `[2026-05]` [SWE-WebDevBench: Benchmarking Vibe Coding Platforms as Virtual Software Agencies](https://arxiv.org/abs/2605.04637) - 68-metric benchmark evaluating 6 AI app-builder platforms reveals: specification bottleneck compresses business requirements, polished UIs mask broken backends, no platform scores >60% on engineering quality, security scores max at 65% vs 90% target.

  <details><summary>Key findings</summary>

  - **35-page benchmark** evaluating 6 AI app-builder platforms across **68 metrics**
  - **Specification bottleneck:** business requirements get compressed through natural language
  - **Polished UIs mask broken backends** — demo-quality ≠ production-quality
  - **No platform scores >60%** on engineering quality
  - **Security scores max at 65%** vs 90% target; concurrency handling as low as **6%**
  - Tests the gap between demo-quality output and **production-grade software**
  - Sobering data for anyone betting on "vibe coding" replacing engineering discipline

  </details>

- 🔵 `[2026-05]` [Cloudflare: Agents Can Now Autonomously Create Accounts, Buy Domains, and Deploy](https://blog.cloudflare.com/agents-stripe-projects/) - AI agents can perform full end-to-end deployment workflows — from account creation to domain purchase to deployment — raising questions about expanding autonomy of coding agents in production infrastructure.

- 🔵 `[2026-05]` [Tilde.run: Agent Sandbox with Transactional, Versioned Filesystem](https://tilde.run/) - Sandboxed environment for coding agents featuring transactional filesystem semantics, enabling rollback and version control of agent-produced artifacts. 178 HN points on launch.

- 🟡 `[2026-04]` [GitLab + AWS: Agentic DevSecOps via BYOM](https://www.stocktitan.net/news/GTLB/git-lab-collaborates-with-aws-to-bring-agentic-dev-sec-ops-to-n87kz4d9bnjq.html) - GitLab Duo Agent Platform now routes inference through Amazon Bedrock — no new vendor onboarding. Source code and inference stay in customer AWS environments. Key signal: AI agents generating enough code/MRs/pipeline activity that governance tooling is now a requirement.

- 🟡 `[2026-04]` [InfoWorld: Best Practices for Agentic Systems in Software Engineering](https://www.infoworld.com/article/4154570/best-practices-for-building-agentic-systems.html) - Anthropic data: ~50% of AI agent deployments are in software engineering. Less than half of orgs report measurable ROI from agentic AI experiments. Multi-agent "factories" for complex knowledge work expected to emerge in 2026.

- 🟡 `[2026-04]` [PanDev Metrics: Cursor Users Log 65% More Coding Hours](https://dev.to/arthur_pandev/the-ai-copilot-effect-how-ai-assistants-changed-coding-time-in-2026-4427) - Analysis of 100+ B2B companies: Cursor users average 50.5h vs VS Code's 30.6h per person. Attributed to AI-assisted "flow state," fewer context switches, and self-selection bias. Cursor's 72% acceptance rate post-Supermaven acquisition notable.

- 🔵 `[2026-02]` [Anthropic: Building a C Compiler with Vibe Coding](https://www.anthropic.com/engineering/building-c-compiler) - Case study of AI agent building a working C compiler.

- 🟠 `[2026-02]` [Steve Yegge: Welcome to Gas Town](https://steve-yegge.medium.com/welcome-to-gas-town-4f25ee16dd04) - When appgen engines run circles around dev squads, what's left?

### Agentic Coding Failure Modes

*Novel failure patterns unique to AI-assisted development that didn't exist before.*

- 🔵 `[2026-02]` [Parallel AI Sessions: "Quantum State" Bugs](https://medium.com/@fernando.garcia.varela/ai-coding-taming-the-new-pet-4e85bb2c0967) - Multiple AI sessions on same codebase create internally consistent but mutually contradictory changes. Code integrates cleanly but behaves incorrectly.

  <details><summary>How it works</summary>

  Before AI, humans were "gloriously, usefully slow" — one task at a time serialized work naturally. AI removes that constraint: a single developer can run 2-4 AI tasks in parallel. One session refactors the auth module while another implements a feature depending on it. Both operate on what they believe is the "current state" — but the codebase has **two current states simultaneously**. The result isn't a merge conflict (those are caught). It's code that integrates cleanly but behaves incorrectly because each session's changes were internally consistent but mutually contradictory. The problem surfaces days or weeks later, in production.

  </details>

- 🔵 `[2026-02]` [Architectural Drift & Non-Serializable Cognitive Commits](https://medium.com/@fernando.garcia.varela/ai-coding-taming-the-new-pet-4e85bb2c0967) - AI's reasoning vanishes when session ends. Micro-decisions across stateless sessions silently reverse architecture established in earlier sessions.

  <details><summary>How it works</summary>

  - **Drift:** slow accumulation of micro-decisions across sessions that individually seem reasonable but collectively move the codebase away from its original design. The model has no cross-session memory. By session five, it's making choices anchored to recent context that quietly contradict the architecture established at session one.
  - **Non-serializable cognitive commits:** architectural decisions made during a session vanish when the session ends. When a human makes an architectural call, it ends up in a PR description, a ticket, a design doc. When an AI session makes the same call, it ends up in a chat log nobody reads. Six months later, a developer or a new AI session reverses the decision without knowing it was made.
  - **Silent scope expansion:** the model, trying to be helpful, refactors code you didn't ask it to touch. Each change is reasonable in isolation. Together they introduce a regression nobody was watching for.

  </details>

- 🔵 `[2026-04]` [Practitioner: "40% of Our Codebase Is AI-Generated" — AI Debt](https://dev.to/adioof/my-team-tracks-ai-generated-code-the-number-shocked-us-25a2) - Team deployed Buildermark to scan git history. Found 12% of AI-generated lines reach production without anyone understanding them ("AI debt"). Introduced pre-commit hooks tagging AI lines; PRs over 50% AI require extra review.

- 🔵 `[2026-04]` [HN Discussion: "Technical, Cognitive, and Intent Debt"](https://news.ycombinator.com/item?id=47865661) - Active debate on how AI-generated code introduces new forms of technical debt — "cognitive debt" (code no one fully understands) and "intent debt" (code that works but doesn't reflect actual design intent). Deep domain knowledge increasingly valuable as differentiator.

- 🔵 `[2026-05]` ["The Bottleneck Was Never the Code"](https://www.thetypicalset.com/blog/thoughts-on-coding-agents) - Essay arguing AI coding agents shift the bottleneck from implementation to specification and organizational coordination. Invokes Brooks' Mythical Man-Month: code is the "residue" of human negotiation, and making the residue cheaper doesn't make the negotiation faster. 561 HN points.
- 🟢 `[2026-05]` [IACDM: Verification-First Framework for AI-Assisted Development](https://arxiv.org/abs/2604.16399) - Addresses the "verification gap": experienced devs using frontier AI models were measurably slower in objective evaluations despite *believing* they were faster. 10.3% of AI-generated apps in a production showcase had critical security flaws. Proposes 8-phase adversarial verification methodology. Tool-agnostic, tested across 20+ projects.

- 🔵 `[2026-02]` [Context Window Collapse](https://medium.com/@fernando.garcia.varela/ai-coding-taming-the-new-pet-4e85bb2c0967) - In long sessions, specs from early exchanges become effectively invisible. Idempotency requirements forgotten by completion time.

- 🟢 `[2026-02]` [Microsoft ACM: Agent Intern-Like Behaviors](https://dl.acm.org/doi/10.1145/3779312) - Agents insert thread.sleep() for race conditions, dismiss crashes, leave debug code, make code work for specific tests but not generally.

  <details><summary>Specific failure examples</summary>

  From Russinovich & Hanselman's ACM paper:
  - **Race condition "fix":** Agent inserts `thread.sleep()` delay instead of proper synchronization — at best disguises the problem
  - **Crash dismissal:** Agent dismisses crashes and hangs as "not relevant"
  - **Debug artifacts:** Leaves debug code behind in production paths
  - **Code duplication:** Duplicates common code throughout the codebase instead of using shared utilities
  - **Test-specific code:** Makes code work for specific tests but not generally — passes CI, fails in production
  - **Overfitting to prompt:** Implements exactly what was asked without considering edge cases an experienced engineer would catch
  - Only an engineer familiar with synchronization patterns has the confidence to *"point out the agent's mistakes"*

  </details>

### Code Review & Quality

*AI-assisted code review, quality gates, and automated feedback.*

- [CodeRabbit](https://coderabbit.ai) - AI code review for pull requests.
- [Pixee](https://pixee.ai) - Finds security and quality issues, opens merge-ready PRs.
- 🔵 `[2026-02]` [ThoughtWorks: Code Review Is Being Unbundled](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Four functions of code review (mentorship, consistency, correctness, trust) each need a new home.
- 🔵 `[2026-04]` [InfoWorld: How Agile Practices Ensure Quality in GenAI-Assisted Development](https://www.infoworld.com/article/4155901/how-agile-practices-ensure-quality-in-genai-assisted-development.html) - Practitioner framework: TDD, BDD, ATDD, pair programming and CI as guardrails for GenAI code. Cites Stanford finding that AI assistants increase security vulnerabilities; McKinsey confirms rethinking practices is required.

  <details><summary>Key findings</summary>

  - Classic agile quality practices become **more important**, not less, with AI coding
  - TDD, BDD, ATDD, pairing, and CI act as **guardrails** against fast low-quality generation
  - Core argument: the more code generation accelerates, the more teams need disciplined validation loops

  </details>

- 🟡 `[2026-04]` [CircleCI: 2026 State of Software Delivery](https://circleci.com/resources/2026-state-of-software-delivery/) - Analysis of 28M CI workflows. Average throughput +59%, but top 5% doubled while median rose just 4%. AI creating code faster than teams can review, test, and ship. Less code reaching production despite higher volume.

  <details><summary>Key findings</summary>

  - Based on **28M CI workflows**, giving this unusual scale
  - Average throughput rose **59%**, but the **median improved only 4%**
  - Top 5% of teams pulled away, suggesting AI amplifies already-strong systems
  - Quantifies the same pattern seen elsewhere: code volume up faster than review, test, and release capacity

  </details>

- 🟡 `[2026-02]` [Faros AI: PR Review Time +91% at Scale](https://medium.com/@fernando.garcia.varela/ai-coding-taming-the-new-pet-4e85bb2c0967) - AI-generated PRs are 154% larger on average. Review becomes the new bottleneck.

- 🟠 `[2026-04]` [O'Reilly Radar: AI Is Writing Code Faster Than We Can Verify It](https://www.oreilly.com/radar/ai-is-writing-our-code-faster-than-we-can-verify-it/) - Argues verification is the new bottleneck. Proposes AI-generated "quality playbooks" that infer project intent from chats/schemas/READMEs and auto-build test + review infrastructure.

- 🔵 `[2026-04]` [code-review-graph: 49x Token Reduction for AI Code Reviews](https://github.com/tirth8205/code-review-graph) - Open-source tool builds a local knowledge graph of codebases so AI reads only relevant context. Claims 6.8x fewer tokens on reviews, up to 49x on daily coding. Practical approach to cost-effective AI coding at scale.

- 🟢 `[2026-04]` [arXiv: Brevity Constraints Improve LLM Accuracy by 26pp](https://www.innovatrixinfotech.com/blog/code-review-graph-claude-code-token-usage-reduction) - March 2026 paper (arXiv:2604.00025) tested 31 LLM models on 1,485 problems. Large models improved accuracy by 26 percentage points with brevity constraints — counterintuitive finding with implications for AI-assisted code review.

- 🟢 `[2026-05]` [Developers Mostly Accept LLM Refactoring Suggestions Without Changes (PROMISE'26)](https://arxiv.org/abs/2605.04835) - Study of 169 GitHub commits linked to ChatGPT conversations finds developers overwhelmingly apply LLM-generated refactoring suggestions as-is. When modifications are made, they tend to be major and follow 5 distinct patterns.

- 🔵 `[2026-04]` [endjin: AI-Assisted Coding Is Four Decisions, Not One](https://endjin.com/blog/ai-assisted-coding-is-four-decisions-not-one) - 4-layer mental model: Harness → Capabilities → Model → Provider. Key insight: harness choice (system prompts, agentic workflows, memory) often matters more than model choice for productivity.

- 🟡 `[2026-04]` [Cloudflare: AI Code Review at Scale — 7 Specialized Agents Across 5,169 Repos](https://blog.cloudflare.com/ai-code-review/) - CI-native AI code review using OpenCode. Launches up to 7 specialized reviewer agents (security, performance, code quality, docs, release mgmt, compliance) per merge request. Coordinator agent deduplicates and judges severity. Median first-review wait time dropped from hours to minutes.

  <details><summary>Key findings</summary>

  - **7 specialized AI reviewer agents** per merge request (vs. one generic prompt)
  - Agents cover: **security, performance, code quality, docs, release management, compliance**
  - **Coordinator agent** deduplicates findings and judges severity
  - Ran across **5,169 repos** from March–April 2026
  - Median first-review wait time dropped from **hours to minutes**
  - Built using OpenCode as the review engine

  </details>

- 🟡 `[2026-04]` [GitHub Copilot Code Review → Billing Change (June 1, 2026)](https://github.blog/changelog/2026-04-27-github-copilot-code-review-will-start-consuming-github-actions-minutes-on-june-1-2026/) - Copilot's agentic code review will start consuming GitHub Actions minutes on private repos. Each review billed via AI Credits + Actions minutes. Impacts Pro, Pro+, Business, Enterprise plans. Budget planning required.

- 🔵 `[2026-04]` [Gitar Launches with $9M: AI-Generated Code Outpaces Validation Capacity](https://www.prnewswire.com/news-releases/gitar-launches-from-stealth-with-9m-as-ai-generated-code-outpaces-teams-ability-to-validate-and-ship-software-safely-302743190.html) - Startup addresses the gap between AI code generation speed and teams' ability to validate/ship safely. Tracks CI failures, agent decisions, and validation outcomes. Signals verification as the new industry bottleneck.

- 🔵 `[2026-04]` [SD Times: AI Code Looks Clean But Hides Contextual Bugs](https://sdtimes.com/ai/rethinking-code-review-in-the-era-of-ai/) - AI-generated code passes surface-level review but fails on system context: missing edge cases, wrong API assumptions, generic security. ~70% of devs report productivity gains, but top frustration is debugging "almost correct" AI output.

- 🔵 `[2026-04]` ["Tokenmaxxing" Is Hurting Developer Productivity](https://www.progressiverobot.com/2026/04/18/tokenmaxxing-developer-productivity-guide/) - Practitioner analysis argues reflexively dumping maximum context into AI prompts is counterproductive. Cites "Lost in the Middle" research: models degrade on buried relevant info. Deliberate context selection > brute-force context.

- 🔵 `[2026-04]` [Gitar Launches with $9M: AI-Generated Code Outpaces Validation](https://www.prnewswire.com/news-releases/gitar-launches-from-stealth-with-9m-as-ai-generated-code-outpaces-teams-ability-to-validate-and-ship-software-safely-302743190.html) - New startup addresses the gap between AI code generation speed and validation capacity. Tracks CI failures, agent decisions, and validation outcomes. Signals the industry bottleneck is shifting from "writing code" to "verifying code."

- 🔵 `[2026-04]` [GitHub Ships Stacked PRs for AI-Driven Code Velocity](https://www.infoworld.com/article/4158575/github-adds-stacked-prs-to-speed-complex-code-reviews.html) - GitHub shipped Stacked PRs to handle increased volume from AI-assisted coding. Traditional linear review can't keep up with AI-accelerated generation. Structural tooling adapting to the new pace.

- 🟡 `[2026-03]` [GitKraken AI Impact Metrics Platform](https://www.gitkraken.com/ai-impact-metrics) - New platform tracks 8 metrics to measure GenAI tool effects: code duplication, rework %, post-PR fixes, prompt/tab acceptance rates. Specifically addresses concern that AI assistants "duplicate code rather than abstract or reuse it," leading to higher maintenance costs if unchecked.

- 🟢 `[2026-02]` [When AI Teammates Meet Code Review: Collaboration Signals Shaping Agent-Authored PRs](https://arxiv.org/html/2602.19441) - Empirical study of how human reviewers interact with AI-authored pull requests. Identifies collaboration signals and integration patterns for agent-generated code in team workflows.

- 🟢 `[2026-02]` [A Survey of Code Review Benchmarks and Evaluation Practices in Pre-LLM and LLM Era](https://arxiv.org/html/2602.13377v1) - Comprehensive survey of code review benchmarks across SE and AI venues. Maps how evaluation practices evolved from pre-LLM to LLM-assisted code review automation.

### Refactoring & Migration

*AI-assisted codebase modernization, language migration, and technical debt reduction.*

<!-- Entries welcome: migration tools, legacy modernization, AI-driven refactoring -->

---

## SDLC Phase: Testing & QA

### Test Generation

*AI tools for generating unit tests, integration tests, and test data.*

- [Diffblue Cover](https://www.diffblue.com/) - AI-powered Java unit test generation.
- 🟢 `[2026-03]` [Diffblue Testing Agent Benchmark](https://www.diffblue.com/resources/benchmark-2026) - Autonomous test generator achieved **81% line coverage** vs. only **32% from senior developer using AI coding agent alone** (2.5x advantage) across 8 real-world Java projects. Highlights gap between AI experiments and production-ready engineering workflows; diminishing returns make manual iteration beyond 50% coverage difficult without orchestration layer.
- [CodiumAI](https://www.codium.ai/) - Analyzes code and generates meaningful tests.
- [Tusk](https://usetusk.ai/) - AI-generated tests for pull requests.

### TDD with AI Agents

*Test-driven development as the interface between human intent and AI generation.*

- 🔵 `[2026-02]` [ThoughtWorks: TDD as Strongest Form of Prompt Engineering](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Tests before code prevents agents from writing tests that verify broken behavior.

  <details><summary>Why TDD matters more with AI</summary>

  Without TDD, agents can write tests that verify broken behavior — the tests pass, the code is wrong, and nobody catches it because the test suite is green. TDD inverts this: the human specifies intent through tests first, then the agent generates code to satisfy them. This makes TDD the **strongest form of prompt engineering** — it constrains the agent's solution space to correct behavior. The ThoughtWorks retreat identified this as one of the most actionable insights for teams adopting AI coding tools.

  </details>

### Visual & E2E Testing

*AI-powered visual regression, end-to-end testing, and browser automation.*

- [Tricentis Tosca](https://www.tricentis.com/) - AI-powered continuous testing.
- [VirtuosoQA](https://www.virtuoso.qa/) - Natural language E2E testing.

---

## SDLC Phase: CI/CD & Release

### Pipeline Automation

*AI-assisted CI/CD pipeline generation, optimization, and troubleshooting.*

- 🟢 `[2026-03]` [Sustainable Code Generation Using LLMs: Systematic Literature Review](https://arxiv.org/html/2603.00989) - Examines energy consumption and efficiency of LLM-generated code. Many studies claim efficiency gains but lack empirical energy analysis.

- 🟢 `[2026-02]` [DeCEAT: Decoding Carbon Emissions for AI-driven Software Testing](https://arxiv.org/html/2602.18012v1) - Measures carbon footprint of AI-driven testing across LLMs and SLMs. First systematic analysis of environmental cost of GenAI in testing workflows.

<!-- Entries welcome: pipeline generators, build optimization, flaky test detection -->

### Release Management

*AI-driven release decisions, changelog generation, and version management.*

- 🟡 `[2026-05]` [GitHub Copilot Moves to Usage-Based Billing (AI Credits, Jun 1)](https://github.blog/news-insights/company-news/github-copilot-is-moving-to-usage-based-billing/) - GitHub announced Copilot usage will consume "AI Credits" starting June 1, 2026. Signals shift from flat-rate to consumption model — likely reflecting cost pressure from high-volume agentic usage patterns.

<!-- Entries welcome: automated changelogs, semantic versioning tools, release risk scoring -->

### Feature Flags & Progressive Delivery

*Tools and patterns for decoupling deployment from release.*

- 🔵 `[2026-02]` [DORA 2025: Working in Small Batches](https://services.google.com/fh/files/misc/2025_dora_ai_capabilities_model.pdf) - Small batches counteract AI generating large unstable changes. Large batches feel productive but hurt stability.

  <details><summary>The batch size paradox</summary>

  DORA found that very small batches are associated with a medium increase in product performance and a medium decrease in friction — but large and very large batch sizes lead to substantial increases in *individual effectiveness* (how it feels to the developer). AI tools naturally encourage larger batches because agents can generate more code faster. This creates an active regression: AI enabling large batch releases reverses the DORA research on deployment stability. The discipline of decomposition and verification *"may feel like a loss of individual speed, but it is precisely this discipline that can unlock sustainable team-level performance."*

  </details>

---

## SDLC Phase: Operations & Observability

### AIOps & Incident Response

*AI-assisted incident detection, root cause analysis, and remediation.*

<!-- Entries welcome: AIOps platforms, RCA tools, automated runbooks -->

### Self-Healing Systems

*Autonomous system recovery and performance optimization.*

- 🔵 `[2026-02]` [ThoughtWorks: Self-Healing Prerequisites](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Requires change ledger, agent identity, fitness functions. Code changes should be last resort for remediation.

- 🟠 `[2026-02]` [ThoughtWorks: "Angry Agents" for Incident Response](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - LLMs tend toward agreement; incident response needs agents that challenge the dominant hypothesis.

### Monitoring & Alerting

*AI-enhanced observability and anomaly detection.*

<!-- Entries welcome: LLM-powered log analysis, anomaly detection, observability tools -->

---

## SDLC Phase: Security

### AI-Assisted Security

*AI tools for vulnerability detection, SAST/DAST, and security review.*

<!-- Entries welcome: AI SAST/DAST tools, vulnerability scanners, security copilots -->

### AI-Assisted Security

*AI tools for vulnerability detection, SAST/DAST, and security review.*

- 🟡 `[2026-02]` [Cycode: State of Product Security in the AI Era 2026](https://cycode.com/state-of-product-security-ai-era-2026/) - Survey of 400 CISOs/security leaders. AI-generated code is #1 blind spot for AppSec teams. 100% of orgs expect increased AI security budgets in 2026.

  <details><summary>Key findings</summary>

  - **400 CISOs and security leaders** surveyed on AI-era security
  - AI-generated code identified as **#1 blind spot** for AppSec/Product Security teams
  - Majority of organizations **lack full visibility** into how and where AI is used across the SDLC
  - **100% of organizations** expect increased budget for AI security-related initiatives in 2026
  - Shadow AI compounds challenge — creating exposure layers that can't be fully seen or governed
  - *"As AI-generated code becomes the norm, organizations must move from fragmented controls to converged platforms"*
  - Endorsed by former TikTok CSO, IDC research managers, and OWASP contributors

  </details>

### Agent Security & Governance

*Securing AI agents themselves — permissions, sandboxing, audit trails.*


- 🟡 `[2026-04]` [Gartner: 25% of Enterprise GenAI Apps Will Face ≥5 Security Incidents/Year by 2028](https://www.gartner.com/en/newsroom/press-releases/2026-04-09-gartner-predicts-25-percent-of-all-enterprise-gen-ai-applications-will-experience-at-least-five-minor-security-incidents-per-year-by-2028) - Gartner survey of 782 I&O leaders predicts rising security incident frequency as GenAI apps proliferate across enterprises.

- 🟠 `[2026-05]` [ACM TechBrief: "AI-Assisted Software Development (Vibe Coding) — Benefits and Risks"](https://bioengineer.org/new-report-explores-the-impact-of-ai-on-software-development/) - ACM's Technology Policy Council warns that AI-generated code frequently bypasses critical engineering disciplines (testing, security review, maintainability). Agentic coding assistants that autonomously execute code expand the attack surface. Recommends treating AI output as untrusted by default.

  <details><summary>Key recommendations</summary>

  - AI-generated code frequently **bypasses critical engineering disciplines** (testing, security review, maintainability)
  - Agentic coding assistants that **autonomously execute code** expand the attack surface
  - Recommends treating **AI output as untrusted by default**
  - Published by ACM's Technology Policy Council — carries weight as a professional society position
  - Sources: [bioengineer.org](https://bioengineer.org/new-report-explores-the-impact-of-ai-on-software-development/) · [techxplore.com](https://techxplore.com/news/2026-04/ai-impacting-software.html)

  </details>

- 🔵 `[2026-05]` [CIO.com: "From Copilot to Control Plane" — AI Governance for Engineering](https://www.cio.com/article/4165609/from-copilot-to-control-plane-where-serious-ai-governance-starts.html) - Argues AI governance in engineering has moved beyond "which copilot to approve" to identity, permissions, model access, prompt retention, and audit trails. Software dev is where the governance problem surfaces first; the real issue is the enterprise-wide AI control plane.

- 🟡 `[2026-05]` [Black Hat Asia: Bug-to-Exploit Window Collapsed from 5 Months → 10 Hours](https://www.neuralbuddies.com/p/ai-news-recap-may-1-2026) - RunSybil CEO reports frontier LLMs are doing heavy offensive lifting, collapsing the vulnerability-to-exploit window from 5 months (2023) to 10 hours (2026). Raises urgent questions about AI-generated code security and exposure.
- 🔵 `[2026-04]` [Linux Kernel: Official Policy for AI-Assisted Code Contributions](https://github.com/torvalds/linux/blob/master/Documentation/process/coding-assistants.rst) - The kernel allows AI-assisted code, but contributors own every line, must review everything manually, and cannot treat AI output as a substitute for understanding. High-signal governance pattern for serious engineering organizations.

  <details><summary>Why this matters</summary>

  - One of the clearest real-world governance patterns from a high-rigor engineering project
  - Policy is **pragmatic, not prohibitionist**: AI is allowed, but accountability stays with the human contributor
  - Explicitly frames AI like any other external aid: useful, but **not an excuse** for poor review or lack of understanding
  - Strong template for enterprise policy: allow use, require ownership, keep review standards human

  </details>

- 🟠 `[2026-05]` [Accountability Gap in AI Coding Agents (AIware'26)](https://arxiv.org/abs/2605.04532) - Analysis of Terms of Service for major AI coding tools reveals consistent pattern of shifting responsibility for correctness, safety, and legal compliance onto users. Presents a research roadmap for accountable agents in SE.

  <details><summary>Key findings</summary>

  - Analyzed **ToS for major AI coding tools** — significant gaps in ownership, liability, and responsibility allocation
  - Consistent pattern: **responsibility shifted to developers** when agents generate or modify code
  - No clear framework for when agent-generated code causes harm or legal issues
  - Presents **research roadmap** for accountable AI agents in software engineering
  - Accepted at **AIware 2026** — signals growing academic attention to governance gaps

  </details>

- 🔵 `[2026-02]` [ThoughtWorks: Security Is Dangerously Behind](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Email access alone enables full account takeover. Platform engineering must enforce secure defaults.
- 🟠 `[2026-02]` [Goldman Sachs: AI Coding Tool Market Valued at $45B](https://www.bloomberg.com/news/articles/2026-02-26/ai-coding-agents-like-claude-code-are-fueling-a-productivity-panic-in-tech) - Market valuation with thin track record on autonomous code safety.

### Supply Chain Security

*AI-related risks in software supply chains and dependency management.*

- 🟢 `[2026-01]` [Vibe Coding Kills Open Source](https://arxiv.org/abs/2601.15494) - AI agents selecting libraries without human engagement threatens OSS maintainer sustainability.

  <details><summary>Key findings</summary>

  - **CEU/Kiel economists** model OSS sustainability under AI coding
  - AI agents select, compose, and modify packages end-to-end — the human developer may not know which upstream components were used
  - **Productivity channel:** AI lowers cost of using packages ✅
  - **Demand-diversion channel:** maintainers capture less engagement and less private return ⚠️
  - When OSS is monetized through direct user engagement, greater vibe coding adoption **lowers entry and sharing, reduces availability and quality of OSS, and reduces welfare** despite higher productivity
  - SWE-bench: Claude went from **1.96% → 74.2%** issue resolution (2024→2026)
  - LLMs gravitate toward large/established libraries, **homogenizing** library selection and making it harder for newer OSS tools to gain traction
  - *"Sustaining OSS at its current scale under widespread vibe coding requires major changes in how maintainers are paid"*

  </details>

- 🟡 `[2026-02]` [Synopsys OSSRA 2026: OSS Components Per App +30%](https://devops.com/ai-fueled-development-pushes-open-source-risk-to-extremes-report/) - OSS in 98% of audited apps. AI agents pulling in more dependencies, expanding attack surface.

---

## SDLC Phase: Documentation & Knowledge

### Automated Documentation

*AI-generated documentation, API docs, and README generation.*

- [Autodoc](https://github.com/context-labs/autodoc) - Auto-generates documentation from codebases using LLMs.

### Knowledge Graphs & Semantic Layers

*Domain ontologies and semantic layers as grounding for AI agents.*

- 🔵 `[2026-04]` [Graphify: Knowledge Graphs as Context Layer for AI Coding](https://graphify.net/knowledge-graph-for-ai-coding-assistants.html) - Claims 71.5× token reduction vs raw file reads by giving agents a structural graph of the codebase. Integrates with Claude Code, Codex, OpenCode. Addresses the context-window ceiling problem.

- 🔵 `[2026-04]` ["Tokenmaxxing" Is Hurting Developer Productivity](https://www.progressiverobot.com/2026/04/18/tokenmaxxing-developer-productivity-guide/) - Practitioner analysis argues reflexively dumping maximum context into AI prompts is counterproductive. Cites "Lost in the Middle" research: models degrade on buried relevant info. Productivity comes from shorter intent→code→verify loops, not bigger prompts.

- 🔵 `[2026-02]` [ThoughtWorks: Knowledge Graphs Having a Moment](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Decades-old tech suddenly critical. Telecom domain ontology captured in ~286 concepts.

  <details><summary>Why this matters now</summary>

  Knowledge graphs are decades-old technology suddenly becoming critical infrastructure for domain-aware AI agents. One telecom company captured its **entire domain ontology in ~286 concepts** — compact enough to serve as grounding for agents. LLMs can now auto-generate event storming artifacts from legacy code, making it possible to build domain ontologies retroactively. For organizations adopting AI coding agents, having a formal domain model means agents can make architecturally consistent decisions instead of guessing from code context.

  </details>

### Codebase Comprehension

*Tools for understanding and navigating large codebases with AI assistance.*

<!-- Entries welcome: code explanation tools, architecture visualization, dependency mapping -->

---

## Cross-Cutting Concerns

### Developer Experience (DevEx)

- 🟡 `[2026-02]` [DX Research: AI Succeeds When DevEx Foundations Are Strong](https://lauratacho.com/research) - Fast CI, clear docs, well-defined services are prerequisites. AI exposes flaws in weak orgs.

- 🔵 `[2026-02]` [ThoughtWorks: Reframe as "Agent Experience"](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Wallets open faster for agent experience. Overlap with developer experience is nearly complete.

- 🟡 `[2026-04]` [DORA 2026: Elite Teams + Platform Engineering See 40% Fewer Failures](https://www.ai-infra-link.com/how-platform-engineering-cuts-downtime-by-40-in-2026/) - Platform engineering + AI-assisted DevOps continues to separate elite performers. Elite teams using platform engineering see 40% fewer environment-related failures.

### Skill Formation & Learning

- 🟢 `[2026-01]` [Anthropic: How AI Impacts Skill Formation](https://arxiv.org/abs/2601.20245) - AI assistance reduces comprehension by 17%. Delegation hurts; conceptual questioning preserves learning.

  <details><summary>Key findings</summary>

  - **Anthropic RCT:** 52 junior engineers learning Trio (async Python library)
  - AI group scored **50% vs 67%** for manual group on comprehension quiz
  - Biggest gap in **debugging** questions
  - **No statistically significant productivity gain** from AI assistance
  - **6 interaction patterns identified**, 3 preserve learning:
    - ✅ Asking follow-up questions after generating code (scores 65%+)
    - ✅ Combining code generation with explanations (scores 65%+)
    - ✅ Using AI only for conceptual questions, coding independently (scores 65%+)
    - ❌ Complete AI delegation for code generation (scores <40%)
    - ❌ Progressive reliance / gradual handoff to AI (scores <40%)
    - ❌ Iterative AI debugging without understanding (scores <40%)
  - **Key insight:** *How* you use AI matters more than *whether* you use it
  - Anthropic now ships **"Learning Mode"** in Claude Code as mitigation
  - Independent confirmation: [University of Maribor 2024 study](https://www.mdpi.com/2076-3417/14/10/4115) found near-identical results

  </details>

- 🟢 `[2024-05]` [University of Maribor: LLM Use and Student Performance](https://www.mdpi.com/2076-3417/14/10/4115) - 10-week RCT: LLM use for code generation correlates negatively with grades; explanations do not.

- 🔵 `[2026-02]` [ThoughtWorks: Juniors More Valuable, Not Less](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - AI gets juniors past net-negative phase faster. Real risk is mid-level engineers.

- 🟢 `[2026-04]` [JetBrains HAX @ ICSE 2026: Long-Term Telemetry vs. Self-Reports](https://blog.jetbrains.com/research/2026/04/ai-impact-developer-workflows/) - 2-year log analysis of 800 devs + survey/interviews. Finding: AI redistributes and reshapes workflows in ways that "elude developers' own perceptions" — observed behavioral shifts often don't match what devs say changed.

- 🟢 `[2026-04]` [arXiv: GenAI Reshaping SE Research Landscape (457-Researcher Survey)](https://arxiv.org/html/2604.11184v1) - Large-scale survey of SE researchers (2023–2025). GenAI use is widespread but concentrated in writing and early-stage activities. Methodological/analytical tasks remain human-driven. Researchers report pressure to adopt, with concerns about trust and correctness persisting.

- 🟢 `[2026-04]` [IBM Research @ ICSE 2026: Enterprise AI Coding Assistants](https://research.ibm.com/publications/usage-effects-and-requirements-for-ai-coding-assistants-in-the-enterprise-an-empirical-study) - Survey of 57 enterprise developers + meta-analysis of 35 existing user surveys. CodeLLMs are "becoming ubiquitous" but questions readiness for real-world enterprise use cases. Key gap: enterprise-specific requirements (security, compliance, domain context) remain underserved.

- 🟢 `[2026-04]` [ICSE 2026 Mining Challenge: AI-Authored PRs in Open Source](https://conf.researchr.org/track/icse-2026/icse-2026-research-track) - Dataset of thousands of AI-authored pull requests in open-source projects, with 62 published papers analyzing long-term impact. First large-scale academic mining of AI code in the wild.

- 🟡 `[2026-04]` [Scaler India: Only 19% of Engineers Are "AI-Ready"](https://www.tribuneindia.com/news/advertorial-disclaimer/scaler-becomes-indias-first-fully-ai-native-tech-career-platform-finds-only-19-of-engineers-are-truly-ai-ready) - AI talent demand projected to nearly double by 2027 (Deloitte-NASSCOM), yet only 16% of IT professionals are currently AI-skilled. AI skills now the single hardest capability to source globally.

- 🔵 `[2026-04]` [Univ. Innsbruck "Software Engineering Live" Workshop](https://www.uibk.ac.at/en/newsroom/2026/software-development-in-the-ai-transformation/) - ~50 experts from academia/industry concluded: AI code generation is gaining performance but cannot fully automate SW dev. Architecture decisions, requirements, testing, and QA remain human tasks. Developer roles shifting from coding → orchestrating, evaluating, and controlling AI systems.

- 🔵 `[2026-04]` [AI Infra Link: Developer Enablement vs Dependency](https://www.ai-infra-link.com/developer-enablement-vs-dependency-key-differences-for-2026-teams/) - Gartner finding: 65% of teams using unsupervised AI code generation spent >30% of time fixing AI-generated code. Recommends mandatory AI output audits, architecture review boards, and treating AI tech debt as first-class backlog item. Spotify's "Tech Health" model (20% sprint allocation to debt) highlighted as best practice.

- 🟢 `[2026-02]` [Russinovich & Hanselman: Preceptor-Based Organizations (ACM)](https://dl.acm.org/doi/10.1145/3779312) - Senior engineers must explicitly mentor juniors to preserve skills pipeline. Universities need classes where AI use is "cheating."

- 🔵 `[2026-02]` [Pragmatic Summit: Atlassian CTO Bought Personal Laptop](https://newsletter.pragmaticengineer.com/p/the-future-of-software-engineering-with-ai) - Corporate IT blocks Claude Code. CTOs run agents on personal devices at night, then mandate org-wide rollout. XP practices making comeback.

### Team Topologies & Agent Topologies

- 🔵 `[2026-04]` [DORA Metrics 2026: AI Expansion Meets Visibility Crisis](https://byteiota.com/dora-metrics-2026-ai-expansion-meets-visibility-crisis/) - DORA grew from 4 to 20+ metrics including AI-specific KPIs. Key finding: "AI doesn't fix teams, it amplifies what's already there." 90% use AI tools, 80% believe they boost productivity, but 30% don't trust AI-generated code. AI improves throughput but increases change failure rate.

- 🔵 `[2026-04]` [GitHub Stacked PRs: Response to AI-Driven Code Velocity](https://www.infoworld.com/article/4158575/github-adds-stacked-prs-to-speed-complex-code-reviews.html) - GitHub shipped Stacked PRs to handle increased volume of changes from AI-assisted coding. Traditional linear review can't keep up with AI-accelerated generation. Structural tooling adapting to the new pace.

- 🔵 `[2026-02]` [ThoughtWorks: Conway's Law Applies to Agents](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Agent drift, speed mismatch, decision fatigue as new bottleneck.

  <details><summary>Key insights</summary>

  - Agent topology mirrors team topology — agents drift over time like teams do
  - **Speed mismatch:** agents clear backlogs in days → hit human-speed bottlenecks (architecture reviews, approvals)
  - **Decision fatigue = new delivery constraint** — managers become approval bottlenecks when agents produce faster
  - This directly validates the on-prem absorption problem: faster dev doesn't mean faster customer deployment

  </details>

- 🟠 `[2026-02]` [ThoughtWorks: Agent Swarm Topologies](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - "Patrol workers on loops" more common than swarms. Strong APIs are prerequisite.

### The Middle Loop (Supervisory Engineering)

*The emerging category of work between inner-loop coding and outer-loop delivery.*

- 🔵 `[2026-02]` [ThoughtWorks: The Middle Loop](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Directing, evaluating, and fixing AI agent output. Nobody has named this role yet.

  <details><summary>What is the Middle Loop?</summary>

  - **Inner loop:** writing code (now increasingly done by AI)
  - **Middle loop:** supervising agents — delegation, orchestration, architecture mental models, rapid output assessment
  - **Outer loop:** CI/CD, deployment, delivery
  - Skills required: decomposition of work for agents, quality assessment of generated code, architectural consistency enforcement
  - Career ladders don't recognize this yet
  - Parallel to computer graphics evolution: 1992 (hand-coded polygons) → 1994 (animation/lighting direction)
  - The person at the top still needs to know what good output looks like, but the mechanics collapse into a monitoring function

  </details>

- 🔵 `[2026-02]` [Karpathy: "Agentic Engineering"](https://x.com/karpathy/status/2026731645169185220) - Proposed term for supervisory engineering with AI agents. "Deep technical expertise is even more of a multiplier."

- 🔵 `[2026-04]` [From Vibe to Agentic: The 2026 Maturation of AI-Driven Development](https://medium.com/technologai/from-vibe-to-agentic-the-2026-maturation-of-ai-driven-development-1bfb0844b5a6) - Traces the evolution from Karpathy's "vibe coding" (Feb 2025) to "agentic engineering" (Feb 2026). Gartner: 40% of enterprise apps to include task-specific agents by end of 2026 (up from <5% in 2025). Claude Opus 4.6 leads SWE-Bench at 80.8%. Anthropic: engineers use AI for ~60% of work but fully delegate only 0-20%.

### Roles & Career Evolution

- 🟢 `[2026-01]` [CSH/Science: Only Senior Devs See Productivity Gains](https://www.science.org/doi/10.1126/science.adz9311) - Juniors use AI 37% more but gain nothing. AI is a skill amplifier, not equalizer.

- 🔵 `[2026-02]` [Forrester: Mid-Career Engineers at Most Risk](https://www.forrester.com/blogs/takeaways-from-the-future-of-software-development-retreat-just-because-you-can-doesnt-mean-youre-ready-to/) - "It's the mid-career engineers energized by the joy of coding that we realized are in trouble."

- 🟠 `[2026-02]` [ThoughtWorks: PM & Developer Roles Converging](https://www.thoughtworks.com/content/dam/thoughtworks/documents/report/tw_future%20_of_software_development_retreat_%20key_takeaways.pdf) - Nobody can define PM in AI-first world. Some training PMs in Markdown.

- 🟢 `[2026-02]` [Harvard: Junior Employment Declines Sharply at AI-Adopting Firms](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5425555) - Studied job postings at AI-adopting vs non-adopting firms. Junior roles drop; senior unchanged.

- 🟢 `[2026-02]` [Microsoft ACM: AI Boost for Seniors, AI Drag for Juniors](https://dl.acm.org/doi/10.1145/3779312) - Azure CTO: "hot topic in all customer engagements — they all say they see it."

- 🟠 `[2026-02]` [CIO: How Agentic AI Will Reshape Engineering Workflows in 2026](https://www.cio.com/article/4134741/how-agentic-ai-will-reshape-engineering-workflows-in-2026.html) - Agentic AI won't just help engineers code — it'll run first drafts of the SDLC, leaving humans to steer, review, and think bigger.

- 🟢 `[2025-11]` [GENIUS Project: The Future of Generative AI in Software Engineering](https://arxiv.org/abs/2511.01348) - Vision paper from 30+ European industrial and academic partners. Maps GenAI potential across all SDLC phases, identifies research challenges in reliability, accountability, security, and data privacy.

- 🟢 `[2026-02]` [Guidelines for Empirical Studies in SE Involving LLMs](https://arxiv.org/abs/2508.15503) - Addresses reproducibility crisis: LLM non-determinism, opaque training data, and rapidly evolving models threaten empirical validity. Proposes methodological standards for SE research with LLMs.

- 🟢 `[2026-03]` [Measuring AI R&D Automation (METR)](https://arxiv.org/html/2603.03992v2) - Framework for measuring AI's ability to automate R&D tasks. Notes Cursor proposing a standard for labelling AI-generated code. Addresses challenge of tracking human vs AI contributions.

- 🔵 `[2026-02]` [Thomas Dohmke (ex-GitHub CEO): AI Native Is the New Cloud Native](https://newsletter.pragmaticengineer.com/p/the-future-of-software-engineering-with-ai) - Building AI-native startup Entire.io. Agents as "sparring partners" that make remote work advantageous again.

### Enterprise & On-Prem Delivery

*Challenges of AI-accelerated development meeting slow enterprise adoption cycles.*

- 🔵 `[2025-11]` [Medium: Bridging On-Prem B2B Delivery Gap](https://medium.com/) - Version sprawl (6-12 versions), CAB cycles, compliance revalidation, telemetry scarcity.

- 🟠 `[2025-12]` [Databricks Architecture: Control Plane / Data Plane Separation](https://www.databricks.com/) - Gold standard for banks: vendor control plane + customer VPC compute.

- 🟡 `[2025-11]` [Harness: 10x Velocity × Unchanged Customer Absorption = Inventory Buildup](https://www.harness.io/) - The core formula for on-prem AI velocity paradox.

  <details><summary>The on-prem AI velocity paradox</summary>

  - **Core formula:** 10x velocity × unchanged customer absorption = inventory buildup + support sprawl
  - On-prem customers (banks, enterprises) have: CAB approvals, limited upgrade windows, regulatory compliance
  - Typical version sprawl: **6-12 concurrent versions** in the field
  - AI can 2-3x vendor-side SDLC velocity but **customer absorption rate is unchanged**
  - Net delivery improvement is **marginal without architecture changes**
  - **Recommended architecture phases:**
    1. Agent-based updates (outbound-only from customer EKS)
    2. AWS PrivateLink
    3. Fully managed BYOC
  - **Release model:** Two-channel (LTS 12-24mo + Current quarterly), with pre-approved auto-deploy for security patches

  </details>

### Open Source Ecosystem Impact

- 🟢 `[2026-01]` [Vibe Coding Kills Open Source](https://arxiv.org/abs/2601.15494) - AI agents homogenize library selection, weaken maintainer engagement, threaten OSS sustainability.

- 🟠 `[2026-02]` [SWE-bench: Claude 1.96% → 74.2% Issue Resolution (2024→2026)](https://www.swebench.com) - Rapid capability improvement crossing usability thresholds.

- 🟢 `[2026-04]` [IBM Research @ ICSE 2026: Enterprise AI Coding Assistants](https://research.ibm.com/publications/usage-effects-and-requirements-for-ai-coding-assistants-in-the-enterprise-an-empirical-study) - Survey of 57 enterprise developers + meta-analysis of 35 existing user surveys. CodeLLMs are "becoming ubiquitous" but questions readiness for real-world enterprise use. Critical gap: enterprise-specific requirements (security, compliance, domain context) remain underserved.

- 🟢 `[2026-04]` [ICSE 2026 Mining Challenge: AI-Authored PRs in OSS](https://conf.researchr.org/track/icse-2026/icse-2026-research-track) - Mining challenge dataset of thousands of AI-authored pull requests in open-source projects, with 62 published papers analyzing long-term impact. First large-scale academic mining of AI code in the wild.

- 🟢 `[2026-02]` [What's in a Benchmark? The Case of SWE-Bench in Automated Program Repair](https://arxiv.org/abs/2602.04449) - Critical analysis of SWE-Bench methodology. Examines whether benchmark scores reflect real-world repair capability or benchmark-specific optimization.

- 🟢 `[2026-02]` [SWE-rebench V2: Language-Agnostic SWE Task Collection at Scale](https://arxiv.org/html/2602.23866) - Extends SWE-Bench beyond Python to multiple languages. Addresses single-language bias in evaluating coding agents.

- 🟢 `[2026-03]` [Scale AI: SWE-Bench Pro](https://scale.com/leaderboard/swe_bench_pro_public) - Complex, long-horizon benchmark requiring edits across multiple files and repositories. Raises the bar beyond single-file fixes.

- 🟡 `[2026-02]` [Synopsys OSSRA 2026: +30% OSS Components Per App](https://devops.com/ai-fueled-development-pushes-open-source-risk-to-extremes-report/) - AI agents expand dependency graphs. OSS in 98% of audited applications.

---

## Building Software for Agents

*The next wave: software where the primary user is an AI agent, not a human. This fundamentally changes how software is designed, priced, and delivered.*

### The Agent-Native Thesis

> *"Humans will not buy software, agents will."* — Jerry Murdock, Co-Founder of Insight Partners ($90B AUM), [20VC Podcast, Feb 2026](https://podcasts.apple.com/us/podcast/the-twenty-minute-vc-20vc-venture-capital-startup/id958230465?i=1000752063511)

- 🟠 `[2026-02]` [20VC: Jerry Murdock — Why Cursor is Dead, Systems of Record Become Valueless Databases with Agents](https://podcasts.apple.com/us/podcast/the-twenty-minute-vc-20vc-venture-capital-startup/id958230465?i=1000752063511) - Insight Partners co-founder ($90B AUM) argues agents will buy and consume software autonomously. Systems of record become valueless databases. "An AI tsunami is coming."

  <details><summary>Key claims from the podcast</summary>

  - **"Humans will not buy software, agents will"** (at 21:04) — the purchasing decision shifts from human evaluation to agent selection based on API quality, latency, and outcome delivery
  - **Systems of record (CRMs, ERPs) become "valueless databases"** — the value moves from storing data to acting on it; agents don't need dashboards
  - **"Cursor is dead"** — standalone coding tools will be absorbed into agentic platforms; the IDE as we know it is transitional
  - **End of tech private equity?** — PE bought SaaS for predictable recurring revenue; agent-native pricing (per-outcome) breaks the LBO model
  - Insight Partners portfolio includes 800+ software companies — Murdock sees this across the entire portfolio
  - **Implication for SDLC:** if your software's primary user becomes an agent, the entire build/test/deploy chain needs to optimize for API quality, documentation parsability, and outcome measurability — not UI/UX

  </details>

- 🟠 `[2026-02]` [BotBorne: AI Agents vs. Traditional SaaS — Why the Software Model Is Dying in 2026](https://www.botborne.com/blog/ai-agents-vs-saas-2026.html) - Comprehensive analysis of SaaS categories being replaced by agents. "Service as Software" inverts the model.

  <details><summary>The SaaS → Agent inversion</summary>

  **The paradox:** average company uses 130 SaaS apps, average worker switches between 13/day. Despite billions spent, actual productivity gains modest — because SaaS tools are still tools. Agents do the work.

  **SaaS categories being replaced:**
  | SaaS Category | Agent Replacement | Disruption |
  |--------------|-------------------|-----------|
  | Customer Support (Zendesk) | Sierra, Decagon, Forethought | Agents resolve issues, not just route tickets |
  | CRM ($300/seat Salesforce) | 11x, Artisan, Clay | Agents handle prospecting + CRM updates |
  | Marketing Automation (HubSpot) | Campaign agents | Single instruction replaces 47-step workflows |
  | Accounting (QuickBooks) | Digits, Puzzle | Continuous bookkeeping vs monthly close |
  | Project Management (Jira) | Orchestration agents | Break down objectives, assign, adjust timelines |
  | Recruiting (Greenhouse) | AI hiring agents | Source, screen, schedule entire pipeline |

  **New pricing models:**
  - **Per-outcome:** pay per resolved ticket, per qualified lead
  - **Per-agent:** subscribe to an AI "worker" at fraction of human cost
  - **Revenue share:** agent takes % of value created
  - **Consumption-based:** pay for compute/tokens consumed

  **What SaaS survives:** systems of record (databases agents interact with), creative tools (human taste), collaboration (human-to-human), developer tools (building the agents).

  **Incumbent dilemma:** Salesforce can't fully embrace agents without cannibalizing $300/seat revenue. Agentforce is positioned as "augmenting users, not replacing them" — classic innovator's dilemma.

  </details>

- 🔵 `[2026-02]` [Brian Christner: The Rise of Agent-to-Agent Apps](https://brianchristner.io/the-rise-of-agent-to-agent-apps/) - SaaS transforms from customer experience portals to data providers for agents. Agent-to-agent marketplaces emerging.

  <details><summary>Key insights</summary>

  - Current apps (email, CRM, etc.) are built for human consumption and **actively try to prevent bots/agents from using them**
  - Example: AgentMail — API platform giving agents their own inboxes. Two agents emailing each other to complete tasks.
  - **SaaS will transform from customer experience portals to data providers for agents** — instead of charging per user, charge agents for data access
  - **Agent-to-agent marketplaces coming:** imagine your agent with a wallet and a goal — each step in the journey requires a transaction fee
  - **Martin Fowler warning:** agents with email access create massive security surface — personal data, doctor appointments, tax authorities
  - Community guardrails needed before delegating personal lives to agents

  </details>

- 🔵 `[2025-04]` [Shopify CEO Tobi Lütke: "Prove AI can't do the job before asking for headcount"](https://x.com/tobi/status/1909251946235437514) - Shopify mandates reflexive AI usage as baseline expectation. Must demonstrate why AI can't handle work before hiring.

- 🟡 `[2026-02]` [Salesforce Q4 2026: Agentforce Drives Revenue Beat](https://markets.financialcontent.com/stocks/article/marketminute-2026-2-25-salesforce-q4-2026-earnings-agentic-ai-drives-revenue-beat-and-enterprise-transformation) - 180+ orgs replaced legacy ITSM with Agentforce. Multi-agent adoption projected +67% by 2027.

  <details><summary>Salesforce's bet</summary>

  - **Agentforce** launched late 2024, transitioning from "copilots" to autonomous agents
  - **180 organizations** replaced legacy support tools (ServiceNow, etc.) with Agentforce IT Service
  - Spring '26 release: **Agentforce Builder** — build, test, refine agents in conversational workspace
  - Multi-agent adoption projected to **surge 67% by 2027** (Salesforce connectivity report)
  - The tension: Salesforce's $300/seat model vs. agents replacing seats. Currently positioning as augmentation, not replacement.

  </details>

### Protocols & Standards

*The infrastructure layer enabling agents to consume software and talk to each other.*

- 🟡 `[2026-04]` [Atlassian × Google Cloud: Bidirectional MCP Server Integration](https://futurumgroup.com/insights/atlassian-and-google-cloud-expand-agentic-ai-partnership/) - Bidirectional MCP server integrations linking Rovo with Gemini Enterprise and Atlassian context with Google Workspace. MCP servers becoming "connective tissue" between enterprise productivity stacks, enabling cross-platform agent workflows.

- 🔵 `[2024-11]` [Anthropic: Model Context Protocol (MCP)](https://modelcontextprotocol.io/) - Open standard for connecting AI agents to data systems, tools, and services. "USB-C for AI" — one protocol instead of N integrations.

  <details><summary>How MCP works</summary>

  - **Announced by Anthropic Nov 2024** as open standard
  - Replaces "N×M integration problem" — instead of every AI tool building custom connectors to every data source, one standardized protocol
  - **Architecture:** MCP Hosts (AI apps) → MCP Clients → MCP Servers (data/tool providers)
  - Servers expose: **Resources** (data), **Tools** (actions), **Prompts** (templates)
  - Already adopted by: Cursor, Windsurf, Sourcegraph, Claude Desktop, and growing ecosystem
  - **Outreach joined MCP ecosystem Feb 2026** — connecting CRM data to AI agents across revenue workflows
  - Enables agents to discover and consume software capabilities without pre-programmed integrations
  - Academic paper: [Convergence of Schema-Guided Dialogue and MCP](https://arxiv.org/html/2602.18764) — formalizes MCP as "deterministic, auditable LLM-agent interaction"

  </details>

- 🔵 `[2025-04]` [Google: Agent2Agent (A2A) Protocol](https://google.github.io/A2A/) - Open standard for agents from different frameworks/vendors/clouds to communicate, delegate tasks, and collaborate without sharing internal state.

  <details><summary>MCP vs A2A — complementary, not competing</summary>

  - **MCP** = agent ↔ tool/data (vertical: agent consuming software)
  - **A2A** = agent ↔ agent (horizontal: agents collaborating)
  - A2A uses HTTP + JSON-RPC + Server-Sent Events
  - Agents don't share internal state, memory, or tools — only communicate through the protocol
  - **DeepLearning.AI** already offers a course on building A2A-compliant agents
  - Supported frameworks: Google ADK, LangGraph, BeeAI
  - Google Cloud dev guide: [Production-Ready AI Agents](https://cloud.google.com/blog/products/ai-machine-learning/a-devs-guide-to-production-ready-ai-agents/)
  - **Combined vision:** A2A for agent collaboration + MCP for agent-tool access = complete agent interoperability layer

  </details>

- 🟢 `[2026-02]` [OWASP Top 10 for Agentic Applications 2026](https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/) - Globally peer-reviewed framework for most critical security risks facing autonomous AI systems. 100+ industry contributors.

### Agent-Native Architecture

*How to build software that agents can consume, not just humans.*

- 🔵 `[2026-02]` [Every.to: How to Build Agent-Native — Lessons From Four Apps](https://every.to/source-code/how-to-build-agent-native-lessons-from-four-apps) - "Claude Code in a trench coat." Three principles: Parity (agent can do everything user can), Granularity (atomic tools), Composability (agent combines tools freely).

  <details><summary>Agent-native architecture principles</summary>

  - **Traditional software:** pre-written code dictates every action. Click "sort by date" → sorts by date.
  - **Agent-native:** define tools (small actions) + skills (plain English instructions). Agent decides which tools to use and how to combine them.
  - **Three principles:**
    1. **Parity:** whatever the user can do, the agent can do. Every click/form/interaction available to both.
    2. **Granularity:** tools should be atomic — small, single-purpose. Features live at the skill level (plain text).
    3. **Composability:** atomic tools + freely combinable skills = app does things nobody explicitly designed.
  - **Trade-offs:** slower (agent reasons each request), more expensive (burns tokens), less predictable (same request ≠ same result)
  - **Key insight:** simpler tools → smarter results. Claude Code is powerful because its core tool (terminal commands) can do almost anything.
  - **Safety rule:** safeguards belong in the tools, not the instructions. You can ask AI to be careful, but it might ignore you. Irreversible actions (deleting files) must be constrained at the tool level.
  - Inference costs dropping ~80% every few months — architecture becomes cheaper over time

  </details>

- 🔵 `[2025-10]` [Praveen Manvi: AI Agent-Native Development — A Practical Protocol](https://pmanvi.medium.com/beyond-copilots-building-for-the-autonomous-future-a-practical-protocol-for-agent-native-ea067a26c205) - Two-stage protocol: Stage 1 (API-first backend, Swagger as blueprint for both humans and agents), Stage 2 (thin frontend reflecting the API).

  <details><summary>The protocol</summary>

  - **Be Agentic:** expose APIs that are actionable, contextual, and well-documented
  - **Be Agent-Native:** build software as a network of agents. Expose actions, not just data.
  - **Monetize Outcomes, Not Usage:** seat-based pricing irrelevant when agents are users
  - **Vanity AI vs Value AI:**
    - Vanity: chat features bolted onto UIs — novel but not transformative
    - Value: AI embedded in critical workflows driving measurable business outcomes
  - **Stage 1:** prompt-driven design → backend generation → OpenAPI spec as single source of truth. The API contract serves as the MCP server.
  - **Stage 2:** feed Swagger spec to AI agent + persona requirements → auto-generate frontend aligned with backend
  - **Results:** prototype in hours not weeks; no frontend/backend mismatch; APIs clean and agent-ready

  </details>

- 🔵 `[2026-02]` [Futurum: Entire's Agent-Native Platform as Blueprint](https://futurumgroup.com/insights/is-entires-agent-native-platform-the-blueprint-for-software-development/) - Thomas Dohmke's Entire.io (ex-GitHub CEO). Google's Developer Knowledge API and Gemini CLI hooks externalize agent context and governance.

- 🔵 `[2026-02]` [WebProNews: The Agent-Native Revolution](https://www.webpronews.com/the-agent-native-revolution-how-ai-agents-are-rewriting-the-rules-of-software-development/) - Developer tools as vanguard of agent-native transformation. GitHub Copilot, Cursor interacting through APIs rather than simulated keystrokes.

### Agent Commerce & Pricing

*How software gets bought, priced, and paid for when agents are the buyers.*

- 🔵 `[2026-02]` [Stripe: Agentic Commerce Suite + x402 Protocol](https://crypto.news/stripe-taps-base-ai-agent-x402-payment-protocol-2026/) - AI agents can make instant USDC micropayments for APIs, data, and digital services. PaymentIntents API charges agents for API usage, MCP calls, and HTTP requests.

  <details><summary>How agent payments work</summary>

  - **Stripe's x402 protocol on Base (Coinbase L2):**
    1. Create a PaymentIntent
    2. Stripe generates unique deposit address per transaction
    3. Return address to agent, instruct to send funds
    4. Track via API/webhook/Dashboard
    5. Funds settle in default balance
  - **Use cases:** micropayments for API calls, data access, model inference, digital services
  - **Stripe's vision (Annual Letter):** three stages of agentic commerce:
    1. Agent-assisted (human approves each purchase)
    2. Agent-directed (human sets rules, agent executes)
    3. **Promptless** (agent anticipates needs, sends notification of completed purchases)
  - **Implication:** software pricing shifts from subscription → per-API-call micropayments. Every HTTP endpoint becomes a billable transaction.

  </details>

- 🟠 `[2026-02]` [eMarketer: Stripe Outlines State of Agentic Payments](https://www.emarketer.com/content/stripe-appraises-agentic-commerce-landscape-2025-annual-letter) - Final stage: "promptless agentic purchases" — AI agents anticipate orders, send notifications of completed purchases.

### Agent-to-Agent Ecosystems

*The emerging world of agents consuming other agents' services.*

- 🔵 `[2026-02]` [Martin Fowler: Agentic Email — The Danger](https://martinfowler.com/bliki/AgenticEmail.html) - Warning about agents with email access: personal data, doctor appointments, tax authorities. Guardrails needed before delegating personal lives.

- 🔵 `[2026-02]` [Brian Christner: Agent-to-Agent Marketplaces](https://brianchristner.io/the-rise-of-agent-to-agent-apps/) - Agents with wallets shopping for capabilities. Each step in a workflow = a transaction fee.

- 🟡 `[2026-02]` [Salesforce: Multi-Agent Adoption to Surge 67% by 2027](https://www.salesforce.com/news/stories/connectivity-report-announcement-2026/) - Unified architecture key to success. Enterprises racing toward multi-agent orchestration.

---

## Frameworks & Maturity Models

*Models for assessing organizational AI-SDLC maturity.*

- 🟡 `[2025-12]` [DORA AI Capabilities Model](https://services.google.com/fh/files/misc/2025_dora_ai_capabilities_model.pdf) - 7 capabilities, 10 outcomes. Value stream mapping recommended.

  <details><summary>The 7 capabilities</summary>

  1. **Clear and communicated AI stance** — ambiguity creates risk; living document from cross-functional group
  2. **Strong version control practices** — safety net for AI-accelerated change; include prompt management, agent configs
  3. **Quality internal platforms** — automated, secure pathways that allow AI benefits to scale
  4. **Working in small batches** — counteracts AI generating large, unstable changes
  5. **Healthy data ecosystems** — timeliness, accuracy, completeness amplify AI benefits
  6. **AI-accessible internal data** — moves AI from generic assistant to specialized expert
  7. **User-centric focus** — ensures AI-accelerated teams move quickly in the right direction

  **10 measured outcomes:** organizational performance, team performance, product performance, delivery throughput, delivery instability, code quality, individual effectiveness, valuable work, friction, burnout.

  </details>

- 🔵 `[2025-02]` [Dan Shapiro: 5 Levels of AI Coding](https://danshapiro.com/) - L0 (manual) → L5 (dark factory).

- 🟡 `[2021-10]` [SPACE Framework](https://queue.acm.org/detail.cfm?id=3454124) - Satisfaction, Performance, Activity, Communication, Efficiency. Essential for measuring AI impact beyond activity metrics.

---

## Emerging Consensus (May 2026)

*What the data actually says, synthesized across all sources.*

| Metric | Finding | Sources |
|--------|---------|---------|
| Individual coding speed | +10-30% | DX, CSH |
| Overall productivity | +3.6-10% | CSH, DX |
| Features shipped | **No change** | Harvard/Jellyfish |
| Delivery stability | **-7.2%** | DORA 2025 |
| PR review time | **+91%** | Faros AI |
| PR size | **+154%** | Faros AI |
| Senior dev benefit | Significant | CSH, Microsoft ACM |
| Junior dev benefit | **Near zero** | CSH, Microsoft ACM |
| Junior hiring | **Declining** | Harvard, Bloomberg |
| Onboarding time | **-50%** | DX |
| AI-generated security vulnerabilities | **+15-18%** | Opsera |
| AI PR review wait time | **4.6x longer** (without governance) | Opsera |
| AI inference cost decline (3yr) | **-92%** | Radoff/METR |
| METR autonomous task horizon | **14.5 hours** (doubling every 123 days) | METR/Radoff |
| Org with weak foundations | **2x more incidents** | DX |
| AI adoption (companies using for most coding) | **63%** | Jellyfish |
| High-adoption PR throughput vs low | **2x** (2.2 vs 1.12/week) | Jellyfish |
| Revert rate increase with AI | **Minimal** (0.61% → 0.65%) | Jellyfish |
| Can't measure AI impact | **75%** of eng professionals | Multitudes |
| AI skill transfer (adjacent roles) | **Works** (within 1% of experts) | Harvard/HBS |
| AI skill transfer (distant roles) | **Fails** (13% below experts) | Harvard/HBS |
| Experienced devs on familiar codebases | **-19% (slower)** → likely reversed | METR 2025 → METR 2026 |
| CI throughput (average) | **+59%** (top 5%: +100%, median: +4%) | CircleCI 2026 |
| AI I&O project full ROI | **28%** (20% fail outright) | Gartner Apr 2026 |
| Code volume explosion | **10x** (25K → 250K lines/month) | NYT/Cursor case study |
| SWE-bench Verified | **~100%** (up from ~60% in 2024) | Stanford HAI 2026 |
| Junior dev employment (age 22–25) | **-20%** since late 2022 | Stanford HAI 2026 |
| Entry-level hiring decline | **-67%** | Medium analysis |
| AI code fails in production (post-QA) | **43%** | Lightrun 2026 |
| Task completion speed with AI | **+55%** (4,800 devs) | GitHub + Accenture |
| Teams using agentic AI | **51%** | MIT Tech Review/Thoughtworks |
| Aim for full AI-managed SDLC (<18mo) | **41%** of eng execs | MIT Tech Review/Thoughtworks |
| AI skills readiness | **Only 19%** of engineers | Scaler India |
| Copilot 3-year ROI | **376%** | Forrester TEI via Exceeds AI |
| CEO-reported AI productivity impact | **~90% report none** | Fortune/NBER |
| Average AI usage among adopters | **1.5 hrs/week** | Fortune/NBER |
| Google AI-generated code share | **75%** (up from 50% fall 2025) | Pichai disclosure |
| Devs using AI at work | **90%** | JetBrains AI Pulse |
| Claude Code adoption growth | **6× in 3 quarters** (18% share) | JetBrains AI Pulse |
| Multi-model usage (3+ models) | **70%+** of orgs | Datadog 2026 |
| Teams shipping 19% slower despite faster devs | **Confirmed** | Wawandco/DORA |
| Cursor users coding hours vs VS Code | **65% more** (50.5h vs 30.6h) | PanDev |
| AI code fails on system context | **~70% report** debugging "almost correct" | SD Times |
| Incidents per PR (AI adoption) | **+242.7%** | DORA/Faros 2026 |
| Bugs per dev (AI adoption) | **+54%** | DORA/Faros 2026 |
| Task throughput per dev | **+33.7%** | DORA/Faros 2026 |
| Code-related tasks per team | **+210%** | DORA/Faros 2026 |
| Macro AI productivity signal | **1.9% cumulative** since ChatGPT launch | Fed Reserve St. Louis |
| Firms reporting measurable AI impact | **~10%** (90% report none) | Fortune/NBER (6,000 execs) |
| Agents solve real-world computer tasks | **66%** (up from 12% a year prior) | Stanford HAI 2026 |
| Cursor vs VS Code coding hours | **65% more** (50.5h vs 30.6h) | PanDev Metrics |
| Unsupervised AI code → rework | **>30%** of time spent fixing | Gartner via AI Infra Link |
| Platform eng. environment failures | **-40%** for elite teams | DORA 2026 |
| Meta-analysis productivity effect | **g=0.33** (moderate, significant) | arXiv meta-analysis (23 studies) |
| AI coding effect on learning | **g=0.14** (not significant) | arXiv meta-analysis (23 studies) |
| Vibe coding platform engineering quality | **<60%** (no platform passes) | SWE-WebDevBench |
| Vibe coding platform security scores | **Max 65%** vs 90% target | SWE-WebDevBench |
| LLM refactoring suggestions accepted as-is | **Majority** (169 commits) | PROMISE'26 |
| SWE-bench Verified (30-month trajectory) | **1.96% → 78.4%** | Bhati survey (May 2026) |
| OpenAI internal AI code share | **20% → 80%** in one month (Dec) | Brockman/Sequoia |
| Delivery Hero autonomous agent output | **~130 senior engineer equivalent** | Herogen case study |
| Bug-to-exploit window | **5 months → 10 hours** (2023–2026) | Black Hat Asia |
| AI productivity (context-dependent range) | **+55% to -19%** | Hostinger meta-analysis |
| Verification gap: devs *think* faster | **Measurably slower** (objective eval) | IACDM (arXiv) |
| Global GenAI adoption (working-age) | **17.8%** (Q1 2026) | Microsoft Diffusion 2026 |
| Git pushes YoY (global) | **+78%** | Microsoft Diffusion 2026 |
| Devs using/planning AI tools | **84%** | LoopStudio 2026 |
| Trust in AI output | **29%** (down 11 pts YoY) | LoopStudio 2026 |
| AI code with OWASP Top 10 vulnerabilities | **45%** | Veracode via LoopStudio |
| Leaders reporting ≥25% velocity gain | **64%** | Jellyfish 2026 |
| AI-introduced issues surviving at HEAD | **22.7%** (464K tracked) | arXiv 2603.28592 |
| GenAI POCs reaching production | **41%** | Intellias 2026 |
| Heavy GenAI users not trusting outputs | **39%** | DORA Gen-AI Report |
| AI snippet issue density vs human | **~1.7×** | TFiR Guardrails 2026 |
| AI snippets w/ security findings (no guardrails) | **48%** | TFiR Guardrails 2026 |
| BLS projected SWE growth (through 2034) | **+15%** (vs −6% "programmer") | US BLS |

**The emerging pattern:**
1. **AI makes coding faster but doesn't ship more features** — the bottleneck was never coding
2. **Seniors benefit, juniors don't** — AI is a skill amplifier, not equalizer
3. **Weak orgs get worse, strong orgs get stronger** — it's a management problem
4. **The bottleneck moved, not disappeared** — from coding to review, integration, architecture (CircleCI confirms at scale)
5. **Stability is declining** — larger batches, faster changes, same governance = more incidents
6. **Novel failure modes emerge** — parallel sessions, architectural drift, context collapse
7. **Skills pipeline at risk** — AI delegation impairs learning; preceptor models needed
8. **Meta-analysis confirms moderate gains** — g=0.33 across 23 studies; larger in labs than real-world
9. **"Vibe coding" platforms fail production readiness** — no platform exceeds 60% engineering quality; polished UIs mask broken backends
8. **Verification is the new frontier** — devs believe they're faster but objective evaluation shows otherwise (IACDM); benchmarks saturated on short tasks, senior-level work remains unsolved (Triadic Data)
9. **Agentic economics shifting** — flat-rate billing can't absorb agentic consumption (GitHub AI Credits); autonomous agents producing at industrial scale (Delivery Hero ~130-engineer equivalent)
10. **Trust is now the gate, not capability** — 39% of heavy GenAI users still don't trust outputs (DORA); 84% adoption with 29% trust (LoopStudio); guardrails replacing throughput as procurement criterion (TFiR)
11. **Macro diffusion is unprecedented** — 17.8% of working-age population using GenAI in Q1 2026; git pushes +78% YoY globally (Microsoft) — fastest-diffusing tech wave on record

---

## Timeline

A chronological view of key inflection points in the AI-SDLC transformation.

| Date | Event | Impact |
|------|-------|--------|
| 2021-06 | GitHub Copilot announced | AI pair programming enters mainstream |
| 2022-11 | ChatGPT launched | Developers start using conversational AI for coding |
| 2023-03 | GPT-4 released | Step change in code generation quality |
| 2024-Q3 | AI writes ~25% of code at Google | Enterprise adoption milestone |
| 2025-02 | Bain reports 25-30% SDLC productivity | First comprehensive enterprise measurement |
| 2025-07 | METR: experienced devs 19% slower | Challenges productivity narrative |
| 2025-12 | Karpathy: agents "basically work since December" | Agentic coding threshold crossed |
| 2025-12 | DORA 2025: AI increases instability | Stability concerns formalized |
| 2026-01 | Science: only seniors see 3.6% gain | Expertise paradox quantified |
| 2026-01 | Anthropic: AI reduces skill mastery 17% | Skill formation concerns validated |
| 2026-01 | "Vibe Coding Kills Open Source" | OSS sustainability alarm |
| 2026-02 | METR: can no longer measure without-AI baseline | Cultural tipping point |
| 2026-02 | Bloomberg: "Productivity Panic of 2026" | Industry-wide reckoning |
| 2026-02 | ThoughtWorks Retreat: 10 themes identified | Practitioner consensus forming |
| 2026-02 | Microsoft ACM: "AI Boost / AI Drag" paper | Senior boost, junior drag formalized |
| 2026-02 | Harvard: junior hiring drops at AI-adopting firms | Labor market impact quantified |
| 2026-02 | Faros AI: +91% PR review time at scale | Bottleneck shift measured |
| 2026-02 | Pragmatic Summit: Atlassian teams at zero hand-written code | AI-native org milestone |
| 2026-02 | Stripe launches x402 agent payments on Base | Agent commerce infrastructure arrives |
| 2026-02 | Jerry Murdock (Insight Partners): "Agents will buy software" | $90B VC signals SaaS paradigm shift |
| 2026-02 | Salesforce: 180 orgs replace legacy ITSM with Agentforce | Enterprise agent adoption accelerates |
| 2026-03-04 | Cursor Automations launched | Event-driven AI agents, shift to "background automation layer" |
| 2026-03-05 | OpenAI GPT-5.4 released | 1M token context window, native computer-use capabilities |
| 2026-03-06 | OpenAI Codex Security enters preview | Context-aware vulnerability scanner |
| 2026-03-11 | Gartner 2026 Predictions released | Forecasts through 2030: AI proficiency in 75% of hiring by 2027 |
| 2026-03-XX | SWE-CI benchmark published | Evaluates long-term codebase maintenance, not just isolated fixes |
| 2026-03-XX | 70% developer AI adoption milestone | Ryz Labs survey marks mainstream adoption |
| 2026-02 | Opsera: 250K devs — AI PRs wait 4.6x longer in review | Governance gap quantified at scale |
| 2026-02 | McKinsey/QuantumBlack: Spec-driven development pattern | Enterprise SDD architecture validated |
| 2026-02 | SWE-Bench Pro launched (Scale AI) | Multi-file, long-horizon benchmark raises the bar |
| 2026-02 | METR task horizons reach 14.5 hours | Week-long autonomy projected by late 2026 |
| 2026-02 | Cycode: 100% of orgs increasing AI security budgets | Security spend catches up to adoption |
| 2026-03 | METR: Measuring AI R&D Automation framework | Standards for tracking AI vs human contributions |
| 2026-03-16 | Harvard: GenAI Wall Effect — AI can't turn novices into experts | Knowledge distance determines AI benefit |
| 2026-03-17 | Jellyfish: AI doubles code output, quality holds | 700 companies, 200K engineers — high-adoption teams merge 2x PRs |
| 2026-03-24 | JetBrains Central announced | Open system for agentic software development; 90% of devs use AI |
| 2026-03-25 | Multitudes: 75% can't measure AI productivity impact | Board pressure growing, metrics still missing |
| 2026-03-27 | GitHub Copilot opt-out policy change | Defaulting users into AI training pipeline; backlash |
| 2026-04-02 | arXiv: GenAI adoption in SE — 204 respondents, 37 countries | 80% regular use; critical gap: most lack objective productivity metrics |
| 2026-03-21 | Fortune: Cursor reaches $30B valuation | 67% of Fortune 500 using Cursor, 150M lines of code daily |
| 2026-03-XX | MCP AI Agent Tools Study: 177K tools analyzed | Software dev = 67% of agent tools, 90% of downloads; action tools surge |
| 2026-04-06 | NYT: "Code Overload" — 10x code volume, 1M-line review backlog | Velocity-absorption gap becomes mainstream narrative |
| 2026-04-07 | Gartner: only 28% of AI I&O projects fully pay off | ROI reality check; 20% outright failure rate |
| 2026-04-08 | arXiv: AI assistance reduces persistence & independent performance | Cognitive dependency empirically validated |
| 2026-04-08 | CNN: SE jobs "demise greatly exaggerated" | Role evolution framing: orchestration > coding |
| 2026-04-10 | CircleCI: 28M workflows — code up, delivery stalling | DevOps bottleneck quantified at scale |
| 2026-04-13 | Kotak: Anthropic Mythos poses 3–3.5% IT services growth headwind | AI model disruption risk for outsourcing sector |
| 2026-04-14 | Stanford HAI 2026 AI Index released | Junior dev employment -20%; SWE-bench near 100%; AI adopted faster than any prior tech |
| 2026-04-15 | Lightrun 2026: 43% of AI code fails in production | "Trust wall" quantified; Amazon 6.3M lost orders traced to AI code |
| 2026-04-15 | MIT Tech Review/Thoughtworks: 51% use agentic AI | 41% aim for full AI-managed SDLC within 18 months |
| 2026-04-16 | JetBrains HAX @ ICSE 2026 | 2-year telemetry shows AI reshapes workflows beyond developers' self-perception |
| 2026-04-16 | DX Q1 2026: juniors edge Staff+ in time savings | Player-coach comeback; shadow-AI risk growing |
| 2026-04-17 | Gartner: AI-Native Dev Platforms top 2026 trend | 60% of new code AI-generated by end of 2026 |
| 2026-04-17 | Gartner: First Hype Cycle for Agentic AI | Agent dev platforms at Peak of Inflated Expectations |
| 2026-04-18 | Pragmatic Engineer survey: 3 developer archetypes | Builders, Shippers, Coasters — ~$200/mo per dev on AI tools |
| 2026-04-19 | IBM Research @ ICSE 2026: Enterprise AI Coding Assistants | Enterprise-specific requirements (security, compliance) underserved |
| 2026-04-19 | ICSE 2026 Mining Challenge | 62 papers analyzing AI-authored PRs in open source |
| 2026-04-21 | Fortune/NBER: Solow Paradox 2.0 | 90% of CEOs report no measurable AI impact on productivity |
| 2026-04-22 | DORA ROI of AI-Assisted SW Dev updated | Practical ROI calculator for AI adoption in SDLC |
| 2026-04-23 | Anthropic: Labor Market Impacts study | "Observed exposure" metric; no systematic unemployment yet |
| 2026-04-24 | Kent Beck: "Nobody Wants Agents" | Multi-agent orchestration ≠ outcome-orientation |
| 2026-04-24 | Martin Fowler: "Harness Engineering" | Deterministic harnesses > raw prompting for enterprise AI coding |
| 2026-04-24 | Datadog: State of AI Engineering 2026 | OpenAI share dropped 75%→63%; multi-model portfolios emerge |
| 2026-04-27 | Google: 75% of new code AI-generated | Pichai disclosure; up from 50% in fall 2025 |
| 2026-04-27 | JetBrains AI Pulse: 90% of devs use AI at work | Claude Code fastest mover: 6× growth, 91% CSAT |
| 2026-04-27 | Amazon mandates 3× release velocity | 2,100+ teams tracked; internal friction growing |
| 2026-04-27 | Oracle lays off ~30K, partly AI-driven | Broader tech layoff wave accelerated by AI |
| 2026-04-28 | Cloudflare: 93% R&D AI adoption + 7-agent code review | 241B tokens/month; 5,169 repos reviewed by specialized AI agents |
| 2026-04-29 | AI Velocity Paradox: faster devs, slower teams | Code churn 3.1%→5.7%; review times +91% |
| 2026-04-30 | DORA ROI Calculator + Faros telemetry: +210% tasks, +242.7% incidents | Verification tax quantified at 22K-dev scale |
| 2026-04-30 | Martin Fowler: Structured Prompt-Driven Development (SPDD) | REASONS Canvas for team-scale prompt engineering |
| 2026-04-30 | AI Dev 26 SF: Ng "100% AI code" vs Brooker "defect rate limits agents" | AI-first engineering debate goes mainstream |
| 2026-05-01 | ACM TechBrief: Vibe Coding benefits and risks | Professional society warns AI output should be "untrusted by default" |
| 2026-05-01 | CIO.com: AI governance moves from copilot approval to control plane | Enterprise governance maturation signal |
| 2026-04-18 | Pragmatic Engineer AI Survey: 3 dev archetypes | Builders/Shippers/Coasters; EM-IC role convergence |
| 2026-04-18 | "Tokenmaxxing" anti-pattern identified | Brute-force context hurts productivity; deliberate selection wins |
| 2026-04-19 | IBM @ ICSE 2026: Enterprise AI coding study | Enterprise-specific requirements (security, compliance) underserved |
| 2026-04-19 | ICSE 2026 Mining Challenge: AI-authored PRs | 62 papers analyzing AI code in open-source at scale |
| 2026-04-20 | DORA Metrics 2026: AI visibility crisis | 20+ metrics now; 30% don't trust AI code despite 90% adoption |
| 2026-04-20 | Gitar launches ($9M): validation gap startup | Industry bottleneck shifts from writing to verifying code |
| 2026-04-20 | GitHub ships Stacked PRs | Structural tooling adapts to AI-accelerated code volume |
| 2026-04-21 | Fortune/NBER: Solow's Paradox repeats for AI | 90% of firms: no measurable AI productivity impact; macro-micro gap persists |
| 2026-04-21 | Innsbruck workshop: AI is "no fairy dust" | Architecture, requirements, QA remain human; roles shift to orchestration |
| 2026-04-22 | PanDev: Cursor users log 65% more coding hours | AI IDE self-selection + flow-state effects quantified |
| 2026-04-22 | GitLab + AWS: Agentic DevSecOps via BYOM | Agent governance tooling becomes enterprise requirement |
| 2026-04-22 | Gartner: successful AI orgs invest 4x in foundations | Data quality + governance > model choice |
| 2026-05-06 | Simon Willison: vibe coding and agentic engineering converging | Even disciplined practitioners lowering review intensity |
| 2026-05-07 | Meta-analysis: AI coding productivity g=0.33, no learning effect | Most rigorous multi-study synthesis; moderate gains confirmed |
| 2026-05-07 | SWE-WebDevBench: vibe coding platforms fail production readiness | No platform >60% engineering quality; security max 65% |
| 2026-05-07 | Accountability gap in AI coding agent ToS | Responsibility consistently shifted to developers |
| 2026-05-07 | Cloudflare: agents autonomously create accounts and deploy | Agent autonomy expanding into production infrastructure |
| 2026-05-02 | Brockman: AI coding 20%→80% in one month (December) | Agentic coding velocity milestone |
| 2026-05-02 | Karpathy: "Software 3.0" — context/prompts replace code | Hasn't typed code since December |
| 2026-05-02 | Delivery Hero Herogen: autonomous agent = ~130 senior engineers | 85% PR acceptance, 100+ merges/day |
| 2026-05-02 | Black Hat Asia: bug-to-exploit window 5mo→10hr | Security urgency for AI-generated code |
| 2026-05-03 | OpenAI Symphony: issue trackers as agent control planes | PRs land 500% more; autonomous orchestration |
| 2026-05-04 | McKinsey: AI productivity paradox — sustained impact elusive | Pilot wins ≠ enterprise value capture |
| 2026-05-06 | Bhati survey: SWE-bench 1.96%→78.4% in 30 months | Most comprehensive agentic SDLC synthesis |
| 2026-05-06 | IACDM: verification-first framework | Devs *think* they're faster but measurably aren't |
| 2026-05-06 | Triadic Data paper: long-horizon SWE agents | Benchmarks saturated; senior-level work is next frontier |
| 2026-05-06 | GitHub Copilot moves to usage-based billing | Agentic consumption breaks flat-rate economics |
| 2026-05-07 | Microsoft: State of Global AI Diffusion 2026 | 17.8% working-age GenAI usage; +78% git pushes YoY globally |
| 2026-05-07 | Jellyfish 2026 State of Engineering Management | 64% of leaders see ≥25% velocity gains; top-quartile 2× PR throughput |
| 2026-05-07 | Anthropic 2026 Agentic Coding Trends Report | First systematic Anthropic field report on agentic SDLC |
| 2026-05-08 | LoopStudio: trust in AI output drops to 29% (−11 pts YoY) | 84% adoption with 29% trust — the trust gap widens |
| 2026-05-08 | Coinbase lays off 14%, CEO cites AI productivity | "AI-washing" pattern crystallizes |
| 2026-05-08 | Google pilots Gemini in SWE interviews | AI-augmented coding becomes a baseline professional skill |
| 2026-05-11 | "The Fast and Spurious" (SPACE-framework arXiv) | Speed gains offset by review burden; team-level effect washes out |
| 2026-05-11 | Beyond the Commit (ICSE-SEIP 2026) | 6 productivity dimensions; long-term skill development under-studied |
| 2026-05-12 | AI-Generated Code Debt Study (arXiv 2603.28592) | 22.7% of AI-introduced issues survive at HEAD across 464K items |
| 2026-05-12 | Deloitte 2026 Software Industry Outlook | Projects 30–35% SDLC gains; quality regressions in low-maturity orgs |
| 2026-05-13 | DORA: Impact of Generative AI in Software Development | Heavy users: more flow, less burnout — but 39% still don't trust AI |
| 2026-05-13 | Pragmatic Engineer: Fowler & Beck on Cycles of Disruption | "Genies" framing — AI pushes teams back to XP-style practice |
| 2026-05-13 | Martin Fowler: Guides & Sensors / Feedback Flywheel | Architectural primitives for reliable agents; team-wide learning loops |
| 2026-05-13 | TFiR: 2026 Year of Guardrails | Governance becomes the dominant procurement criterion |

---

## Contributing

Contributions welcome! Please read the [contributing guidelines](CONTRIBUTING.md) first.

**When adding a resource, please include:**
1. The date tag `[YYYY-MM]` for when it was published
2. An evidence rating (🟢🟡🔵🟠)
3. A one-line description of the key finding or contribution
4. Optionally, a `<details>` block with deeper analysis

**Quality bar:** We prefer resources with specific findings, data, or novel frameworks over generic "AI will change everything" pieces.

---

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the authors have waived all copyright and related or neighboring rights to this work.
