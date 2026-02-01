# File: AGENT_EXAMPLES.md

## Agent Examples - Chat-Only Demos

These are **chat-only** demo agents. Paste the full agent XML as the **first message** in a new chat, then give a normal instruction.

Included demo agents (in `agents/demo/`):
1) MVP Builder
2) Landing Page Builder
3) Deep Research Agent

---

## 1) MVP Builder (chat-only)

### How to run
1) Paste: `agents/demo/SRX.ACE.Demo.MVPBuilder.OSS.v1.xml`
2) Then send:

Example instruction:
Build an MVP spec for a local services marketplace. Include:
- feature list
- user flows
- data model
- API contract
- acceptance tests

### Best prompt pattern
Ask for explicit deliverables:
- app_spec
- ui_flows
- data_model
- api_contract
- tests

Add constraints if needed:
- local_only=true
- stack=SvelteKit+Tailwind
- no_web=true

---

## 2) Landing Page Builder (chat-only)

### How to run
1) Paste: `agents/demo/SRX.ACE.Demo.LandingPageBuilder.OSS.v1.xml`
2) Then send:

Example instruction:
Create a landing page for a B2B AI automation service targeting accounting firms.
Deliverables:
- page structure
- headline variants
- full copy
- CTA system
- FAQ section
- SEO meta

Constraints:
- clean, trustworthy, minimal motion
- no fake metrics or case-study claims

---

## 3) Deep Research Agent (chat-only)

### How to run
1) Paste: `agents/demo/SRX.ACE.Demo.DeepResearchAgent.OSS.v1.xml`
2) Then send:

Example instruction:
Research the competitive landscape for “AI call agent” platforms.
Deliverables:
- competitor map
- key differentiators
- pricing signals (if available)
- feature matrix
- recommended positioning
Constraints:
- if a fact is uncertain, label it as uncertain
- do not invent numbers

---

## Using the compiler + examples together

### Pattern A: compile then execute
1) Run the compiler:
compile: build a landing page for a plumbing business in Texas
| deliverables=landing_page,copy,seo_meta,faq
| constraints=clean_localbiz_style,no_fake_claims

2) Copy the returned `promptunit_package`.

3) Extract the active `sr8_prompt` and run it in a new chat:
Execute this sr8_prompt. Produce the deliverables.

### Pattern B: refine then compile
1) Run:
refine: I need something for my business but not sure what.

2) Fill the intake form and send it back.

3) Receive the `promptunit_package`.

---

## Where to find runnable flows
The `examples/` folder contains ready-to-copy chat flows:
- `01-fast-compile.txt`
- `02-refine-then-compile.txt`
- `03-multidomain-sros-run.txt`
- `04-multimodal-adapters.txt`
- `05-governance-gate-required.txt`
