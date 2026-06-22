# Tim Simpson — Skills Profile

## Name / Handle
Tim Simpson · [@TimSimpsonJr](https://github.com/TimSimpsonJr)

---

## Contact Information
- **Email:** tim@timsimpsonjr.com
- **LinkedIn:** https://linkedin.com/in/timsimpsonjr

---

## Core Identity
Creative director and process designer, about 15 years: photojournalism, motion graphics, documentary editing and color, web and graphic design, data-visualization and mapping, UX, and operations.

AI and design-first. I'm new to software, but I ship production tooling by directing agents (Claude Code and Codex).

The judgment I bring is process-architecture and tradeoffs, earned over a long design career; agentic development is how I move fast on the code.

---

## What You're Good At
- Creative direction and process design (the deep expertise): visual media, UX, and workflow design over about 15 years.
- Directing agentic development: I own the architecture and tradeoff calls and run agents through implementation, holding the design line while they write the code.
- Making agentic output trustworthy: adversarial cross-model review gates, deterministic checks built to be structurally uncorrelated with the generator, and handoff discipline. Trust comes from the architecture, so I don't have to take the model's word for it.
- Maps and geospatial: a throughline across my work, from data-visualization cartography animated in motion graphics for documentary, to interactive web maps with address-to-representative district matching (DeflockSC, open-civics, Call Y'all), to GIS proximity analysis. The medium changes; the spatial-storytelling instinct carries across.
- Authoring Claude Code plugins and skills: several public and shipped (see Projects).
- OSINT and civic-tech: FOIA, public records, surveillance accountability, and local tooling.
- Operations and automation: my day job is customer success at a payments platform, where I build greenfield internal tooling.

---

## How You Use AI Right Now
- Daily driver: Claude Code for implementation, run from an orchestration session that hands the actual work to subagents and long-running workflows instead of coding inline.
- Superpowers as the discipline core, with my own cross-model-review plugin layered on top. That plugin is what lets the long-running, autonomous workflows run mostly unattended: Codex reviews at the design, plan, and implementation gates, and its consensus mode keeps a run moving on anything that doesn't need a design call, surfacing only the decisions that do.
- My own skills library on top of Superpowers: copydesk, handoff, research, narrative-reframe.
- A lot of hands-on experimentation with image generators, which is really the visual-media side of my background finding a new outlet.
- Deterministic, generator-decorrelated CI/CD gates, so the checks catch what the model can't catch in itself.
- Structured session handoff docs, plus background-task chips that spin off fresh sessions for follow-on work, so nothing falls through a context reset.
- A local-and-frontier mix: on-device models (NVIDIA Parakeet and NeMo in Recap, Ollama in the research tools) alongside frontier models for the heavy lifting.

---

## Current or Recent Projects
- **Fieldwork**, an investigative plugin suite for Claude Code (public). It lets one person carry an investigation from a raw question to a finished, sourced, publishable piece, with no per-search API costs and no sensitive records leaving their machine. Four plugins cover the pipeline:
  - **Researcher**: multi-hop web research that builds a durable, cross-linked knowledge base rather than a one-off report. Every source is tiered by credibility, every finding scored for confidence, and thin or shaky topics get sent back for another pass; the results file as permanent, interlinked notes that compound across runs. It forensically preserves each source it fetches, a hashed local copy with a Wayback Machine fallback for pages already gone, so the material behind a citation can't quietly change or vanish. It runs on Claude Code's own subagents and can run fully locally, with no API key or per-search billing. → [repo](https://github.com/TimSimpsonJr/researcher)
  - **Magpie**: turns a raw FOIA release or data dump into findings you can publish and defend. Every headline number has to pass a check before it counts, every claim ties back to the exact page it came from, evidence is hashed and timestamped so its provenance holds up, and third-party PII gets swept before anything goes out. It all runs locally, so sensitive records stay on your machine. → [repo](https://github.com/TimSimpsonJr/magpie)
  - **Librarian**: the shared output layer for both. Everything Researcher and Magpie produce lands as clean, tagged, cross-linked notes (Obsidian-aware, portable without it), and every claim keeps its sources attached, so weeks later you can still trace where a fact came from. → [repo](https://github.com/TimSimpsonJr/librarian)
  - **Copydesk** (49 stars): handles the writing. It drafts in your own voice, learned from samples of your past writing using a formalized extraction method, so the result reads closer to how you'd write it than a raw draft would. Before you ever see a draft, parallel review gates catch most of the AI tells (banned phrases, em-dash tics, ChatGPT cadence) that would otherwise brand the work as machine-made and cost you a reader's trust. → [repo](https://github.com/TimSimpsonJr/copydesk)

  The long-term goal is a full investigative-documentary production suite, with video-editing and motion-design integrations (in progress). → [suite](https://github.com/TimSimpsonJr/fieldwork-plugins)
- **cross-model-review** (public). A structured adversarial reviewer for agentic development. It pulls a second model (OpenAI's Codex) in to scrutinize the work at fixed checkpoints across the planning and development cycle, design, plan, and implementation, so nothing advances on one model's say-so. It catches the failure modes that are invisible to the model that produced the code. An autonomous mode runs it unsupervised on work that doesn't involve design decisions, and reserves my judgment for the calls that actually need it. → [repo](https://github.com/TimSimpsonJr/cross-model-review)
- **open-civics** (public). A drop-in data layer that lets any app match a US resident to their elected representatives. Two npm packages (verified contact data and district boundaries), kept current by automated weekly scraping and validation, so you're not querying stale contact info. It reaches all the way down to the local level, county and municipal officials, which has had no free source since Google shut down the representatives half of its Civic Information API. South Carolina is fully covered today (170 state legislators, every county and municipality), and I'm getting it ready to scale to all 50 states. → [repo](https://github.com/TimSimpsonJr/open-civics)
- **DeflockSC** (public, live at deflocksc.org). A surveillance-accountability site whose centerpiece is a "contact your reps" tool. A resident types in their address; using the open-civics data layer, the site finds their exact state and local representatives and hands them a pre-written letter tailored to that specific official, pulling in relevant local stories and calls to action matched to the official's district and level of government, state versus local (85 templates spanning all 46 SC counties). That last mile is where most civic engagement dies: people don't act because finding the right official and working out what to say is too much friction. This removes both, so a vague intention becomes a sent message in under a minute. I'm extending the same engine into **Call Y'all** (in progress), a civic-engagement platform that applies this district-matched, pre-written-letter approach to issues well beyond surveillance. DeflockSC also maps known ALPR camera locations and tracks relevant statehouse bills, and it's built to be forked and localized to other states. → [repo](https://github.com/TimSimpsonJr/deflocksc-website)
- **Operations-enablement infrastructure** (private, day job). At a payments platform, I'm building internal tooling on top of a shared "company brain," a growing, structured knowledge base of how the business actually runs, and putting that knowledge to work for the team through agents, so answers and actions that used to mean pulling someone off their work no longer do. Recap (below) is one of the input points that feeds the brain.
- **Recap** (private). A local-first meeting tool. It records meetings, transcribes them (NVIDIA Parakeet) and works out who said what (NeMo Sortformer) entirely on-device, then has Claude turn the transcript into structured notes in Obsidian. Only the LLM call ever leaves the machine. What that buys you: every meeting becomes searchable, structured institutional memory instead of a recording nobody rewatches, and sensitive internal conversations never touch a third-party transcription service. It also feeds the company brain above.

---

## What You Want to Build Here
AI and design-first, and already shipping, but early in software, and I haven't had real feedback yet on the hard parts: scale, adversarial input, security. A team doing serious agentic architecture is the feedback surface I want, and the cert is part of why I'm here. The problem I most want to push on: how to put durable, personalized taste into agentic systems, getting an agent to reliably carry a specific person's judgment and aesthetic instead of generic competence. It's already the throughline in my work (Copydesk tries to extract and hold one person's writing voice), and I think it's where the interesting frontier sits.

What I'd bring is a human-centered, design-first lens shaped by 15 years across photojournalism, documentary, motion design, UX, and operations. I start from how a person actually moves through a system and design the architecture backward from there, and that holds whether the medium is an interface, an agent workflow, or an API. On top of that, discipline around making agentic output trustworthy (adversarial review gates, deterministic catch systems, handoff hygiene), and a reusable plugin and skills library. What I want back is people who'll pressure-test the design judgment and break me in on the domains I haven't hit yet.

---

## Superpower
I treat process and architecture as design problems, the same human-centered instinct whether the medium is a newsroom workflow, an interface, or a software system. For example, a field-editing workflow I designed streamlined a newsroom, taking turnaround from 12 to 24 hours down to about 10 minutes, and it became standard practice at major outlets. Designing that workflow and designing an agent pipeline are similar problems; software is just the latest place I've pointed the instinct.
