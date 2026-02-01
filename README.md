# SROS Self-Compiler (OSS)
### Chat-Friendly Sovereign Compiler Front Door

This repository contains the **open-source SROS Self-Compiler**, a chat-native compiler that converts raw human intent into **sealed, receipt-driven build artifacts**.

This is **not a chatbot prompt**.  
This is **not an agent personality**.  

This is a **compiler specification and runtime contract** designed to run inside any modern chat environment.

---

## What This Project Is

The SROS Self-Compiler is a **deterministic intent compiler**.

You give it intent.  
It returns a **sealed XML package** containing:
- Canonicalized intent
- Governance decisions
- Receipts
- One or more `sr8_prompt` build artifacts

All outputs are:
- XML-only
- Schema-clean
- Receipt-driven
- OSS-safe (no fake precision, no numeric trust scores)

---

## What This Project Is NOT

- Not a chatbot
- Not a generic “system prompt”
- Not tied to any specific LLM provider
- Not a SaaS
- Not an execution runtime

This repo **stops at compilation**.

---

## How This Fits Into SROS

**SROS (Sovereign Recursive Operating System)** is an architectural framework for governed, agentic AI systems.

At a high level, SROS separates:
- Intent intake
- Compilation
- Orchestration
- Runtime execution
- Memory
- Governance

This repository provides **only one thing**:

> The open-source, chat-friendly **compiler entrypoint** for SROS.

It is the front door that turns intent into structured, governable build artifacts.

---

## Core Components in This Repo

### 1. Self-Compiler Spec (v3)
A full compiler specification that defines:
- Intake rules
- Adapter selection
- Model routing (abstract targets only)
- MirrorOS lens enforcement
- SR8 compilation
- SR9 orchestration wiring
- Receipt emission
- Sealed package output

Users **never edit the spec**.
They only provide intent.

---

### 2. Hygiene + Intake XML
Minimal XML forms used when:
- Intent is vague
- Deliverables are unclear
- Constraints are missing

This keeps the compiler chat-friendly without leaking internals.

---

### 3. Demo SRX ACE Agents (Chat-Only)

This repo ships **three example SRX ACE agents** as **chat-only prompts**.

They are:
- Meant to be pasted directly into chat
- Fully tailorable
- Independent of system roles
- Compatible with any chat app

Included demos:

1. **MVP Builder Agent**  
   Converts product ideas into MVP build artifacts.

2. **Landing Page Builder Agent**  
   Compiles high-signal landing pages with structure, copy, and constraints.

3. **Deep Research Agent**  
   Produces scoped, receipt-driven research artifacts without hallucinated certainty.

These are examples, not limits.

---

## How To Use (Fast Path)

### Option 1: One-Line Compile
Start your message with:

compile: build a professional landing page for a local laundry business

The compiler will:
- Infer minimal OSS constraints
- Compile intent
- Emit a sealed `promptunit_package`

---

### Option 2: Refined Intake
If the compiler needs clarity, it will return an XML intake form.

You fill it.
Send it back.
Compilation resumes.

---

## Output Guarantees

Every successful compile returns **exactly one XML document**:
- Root: `<promptunit_package>`
- Schema-valid
- Receipt-complete
- No markdown
- No prose outside XML

If compilation is not allowed, a **safe alternative** is compiled instead and governance is marked accordingly.

---

## Open Source Philosophy

This OSS release intentionally:
- Avoids numeric trust scores
- Avoids provider-specific routing
- Avoids fake determinism
- Keeps hashing optional
- Keeps governance explicit

Enterprise features, proprietary policy bundles, and production kernels are **out of scope**.

---

## Who This Is For

- Builders who want **intent → structure**, not vibes
- Researchers exploring compiler-style prompting
- OSS contributors experimenting with governed agents
- Anyone tired of “just prompts” with no receipts

---

## Credits

Built by **Muqeet ul Hassan**  
Under the SROS architecture

- SROS: https://sros.cloud  
- PlatXP: https://platxpcreative.com  

---

## Final Note

If you can paste text into a chat,  
you can run this compiler.

That is the point.


