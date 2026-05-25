---
description: Generate a beautiful zoomable HTML diagram of this codebase, designed for non-coders
argument-hint: "[output-dir] (default: .boxbox)"
---

# /boxbox — Visualize this system

You are running the **boxbox** plugin. Your job: produce a beautiful, beginner-friendly HTML diagram that explains what this codebase does, written for someone who does **not** know programming (e.g. a vibe-coder, a designer, a founder using AI to build their app).

## Audience reminder

The reader is **not a programmer**. They want to answer questions like:
- "What are the main parts of my app?"
- "Where do users log in?"
- "What connects to the database?"
- "Which AI/API is this app talking to?"

Avoid jargon. Say *"This page lets users sign up"* instead of *"AuthController handles POST /register"*.

## Workflow (delegate to subagents in sequence)

Run these three subagents one after another. Each one's output feeds the next.

### Step 1 — Scan

Use the Agent tool with `subagent_type: "boxbox-scanner"` to discover what's in the codebase.

Prompt the scanner with:
> Scan the current working directory and produce a JSON inventory of: detected tech stack, top-level features (login, dashboard, checkout, etc.), and a file→feature mapping. Output only valid JSON matching the schema in your instructions. Working directory: $(pwd).

Save its JSON output to `.boxbox/scan.json` (create the directory if needed).

### Step 2 — Analyze

Use the Agent tool with `subagent_type: "boxbox-analyzer"`. Feed it `.boxbox/scan.json`.

Prompt the analyzer with:
> Read .boxbox/scan.json. For each feature, trace its connections: what calls what, what reads/writes which database, which external APIs (Stripe, OpenAI, Auth0, etc.) it talks to. Produce the boxbox graph JSON (nodes + edges + plain-English descriptions) per your schema. Write to .boxbox/graph.json.

### Step 3 — Visualize

Use the Agent tool with `subagent_type: "boxbox-visualizer"`. Feed it `.boxbox/graph.json`.

Prompt the visualizer with:
> Read .boxbox/graph.json. Generate a self-contained, beautiful, zoomable HTML file at $ARGUMENTS/diagram.html (default .boxbox/diagram.html). Follow your design rules: layered top-down, big colorful blocks, click-for-explanation side panel, tech-stack badges, two zoom levels (System view ↔ Feature drill-down). Must work offline once opened (inline CSS/JS, only CDN allowed is Cytoscape.js + dagre via jsDelivr).

## Final output to user

After all three agents finish, tell the user in **one short paragraph**:

1. Where the file is (`./.boxbox/diagram.html`)
2. How many features and connections were found
3. One sentence inviting them to open it in a browser

Do **not** dump JSON or technical detail. Keep it warm and non-technical.

## Arguments

`$ARGUMENTS` — optional output directory (default `.boxbox`). If empty, use `.boxbox`.
