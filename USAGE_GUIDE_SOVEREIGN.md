# File: USAGE_GUIDE_SOVEREIGN.md

## SROS Self-Compiler (OSS) - Sovereign Usage Guide

This guide shows:
- how to run the SROS Self-Compiler in real chats
- how to use the compiled prompts included in this repo
- what to do after you receive a promptunit_package
- how to iterate without drift

This is chat-first. No tooling required.

---

## 1) Where to run this

You can run the compiler and the demo agents inside any LLM chat that supports long messages.

Common environments:
- ChatGPT
- Claude
- Gemini
- Perplexity
- Cursor / Windsurf
- Continue.dev
- OpenWebUI
- LM Studio / local UIs

Important:
- Outputs are XML-only
- Always copy the entire XML response as-is
- Do not paraphrase or summarize compiler output

---

## 2) Operating modes

### Fast compile mode
Use when you know what you want.

compile: build a 5 page website for a local cleaning business

### Refine mode
Use when intent is incomplete.

refine: I want something for my business but not sure what yet

The compiler will emit a minimal intake form.

---

## 3) Multi-domain compiles

You can compile across domains in one run.

Examples:
- Product + Engineering: deliverables=app_spec,ui_flows,api_contract
- Marketing: deliverables=landing_page,offer,copy,cta
- Research: deliverables=experiment_plan,evaluation_rubric
- Visuals: deliverables=image_prompts,style_tokens

Best practice:
- Deliverables as an explicit list
- Constraints as hard rules

---

## 4) Sovereign depth switches

You can enforce stricter behavior inline.

Example:
compile: build MVP | depth=sovereign | receipts=enforced | local_only=true

OSS v1 guarantees:
- receipt emission per stage
- constraint arbitration
- governance gating
- no fake precision
- no provider coupling

---

## 5) Using the demo agents included in this repo

This repo includes chat-only demo SRX ACE agents:
1) MVP Builder
2) Landing Page Builder
3) Deep Research Agent

How to run a demo agent:
1) Open the agent XML file
2) Paste the entire agent XML as the first message in a new chat
3) Send it
4) In the next message, give a normal instruction

Example:
Build a landing page for a fintech startup targeting SMBs.

The agent executes and returns one XML document.

---

## 6) What to do after you receive a promptunit_package

Your promptunit_package contains sr8_prompt artifacts.

### Step A - Extract the active sr8_prompt
Find the sr8 prompt embedded in CDATA:

<sr8_prompts>
  <active>
    <![CDATA[
      <sr8_prompt ...>
      ...
      </sr8_prompt>
    ]]>
  </active>
</sr8_prompts>

### Step B - Execute the sr8_prompt
Paste the sr8_prompt into a new chat and say:

Execute this sr8_prompt. Produce the requested deliverables.

Common uses:
- Generate files
- Generate docs
- Generate UI specs
- Generate research outputs

### Step C - Store as receipt
Save the full package:

/runs/YYYY-MM-DD/<release_or_placeholder>/package.xml

This becomes your replay capsule.

---

## 7) Iterating without drift

Do not rewrite the spec manually.

Instead, recompile with deltas:
compile: take the last package, keep constraints, add 2 case studies, tighten copy

The compiler preserves:
- constraints
- intent lineage
- governance posture

---

## 8) Common compile templates

Website:
compile: build a 10 page site
| deliverables=sitemap,design_tokens,copy
| constraints=stack:SvelteKit+Tailwind

App feature:
compile: add auth module
| deliverables=ui_spec,api_contract,tests
| constraints=local_only

SROS run design:
compile: design an SROS run
| deliverables=graph_spec,cli_commands,receipts_list
| constraints=no_web

---

## 9) Minimal troubleshooting

- Intake form appears unexpectedly: intent too vague, add deliverables
- XML contains wrapped links: remove [ and ]( from input and re-run
- Want JSON/YAML output: roadmap item, not in OSS v1

---

## Final note

This repo is designed so that:
- the compiler turns intent into executable prompts
- the included demo agents can be run immediately
- outputs are portable across chats and environments

Intent in. Artifacts out. Receipts preserved.
