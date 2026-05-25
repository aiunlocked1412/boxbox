# 📦 boxbox

> by **AI UNLOCKED**

**See your codebase as a friendly, zoomable picture.**

`boxbox` is a Claude Code plugin for **non-coders who use AI to build apps**. Type `/boxbox` in any project and get a beautiful HTML diagram that explains what your app is, how it works, and what connects to what — written in plain English, not code-speak.

> "Wait, so *this* is where users log in, and *this* talks to the AI? Oh, I get it now."

---

## What you get

- 📐 **One HTML file** at `./.boxbox/diagram.html` — open it in any browser, share it with anyone.
- 🎨 **Big colorful blocks** organized top-down: pages on top → API → backend → database → outside services.
- 🖱️ **Click any block** to read a plain-English explanation of what it does.
- 🔖 **Tech-stack badges** so you know what tools your app is built with.
- 🌙 **Light & dark mode**, mobile-friendly, works offline once opened.
- 🧠 **Powered by three AI agents** (scanner, analyzer, visualizer) that work together to understand your code.

---

## Install

### Option A — From a marketplace

```
/plugin marketplace add aiunlocked1412/boxbox
/plugin install boxbox@boxbox-marketplace
```

### Option B — Local install (for testing)

Clone the repo, then in Claude Code:

```
/plugin marketplace add /path/to/boxbox
/plugin install boxbox@boxbox-marketplace
```

---

## Usage

In any project directory:

```
/boxbox
```

That's it. After about a minute you'll see:

```
Diagram ready at ./.boxbox/diagram.html
```

Open it in your browser. Click any block. Done.

### Custom output directory

```
/boxbox docs
```

Saves to `docs/diagram.html`.

---

## Who is this for

- **Vibe coders** — people building apps with Claude / ChatGPT / Cursor who want to understand what they've shipped.
- **Founders** — non-technical founders who want a picture they can show to investors, designers, or new hires.
- **Designers & PMs** — anyone working alongside engineers who wants a shared mental model of the system.
- **Anyone learning** — students looking at an open-source codebase for the first time.

If you can read English, you can read a boxbox diagram.

---

## How it works (under the hood)

The `/boxbox` command runs three subagents in sequence:

1. **`boxbox-scanner`** — walks your project, detects the tech stack, groups files into features (Login, Dashboard, Payments, etc.).
2. **`boxbox-analyzer`** — traces how those features connect: what calls what, what reads the database, which AI/API services are involved.
3. **`boxbox-visualizer`** — turns that graph into a polished, self-contained HTML diagram.

The result lives in `.boxbox/diagram.html` along with the intermediate `scan.json` and `graph.json` (you can regenerate the HTML anytime by re-running `/boxbox`).

---

## Limitations

- Works best on projects with a recognizable structure (Next.js, FastAPI, Express, Django, etc.).
- Diagram quality depends on how well your features are organized — messy code → messy diagram.
- Doesn't trace runtime behavior, only static structure.
- Best for projects under ~2000 files.

---

## Credits

Made with ❤️ by **AI UNLOCKED**

## License

MIT
