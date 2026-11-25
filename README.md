# HansenAI

**An AI platform for cybersecurity that teaches you, guides you, and does the work with you.**

Most security tooling assumes you already know what you're doing. Most security learning material assumes you'll never touch a real target. HansenAI closes that gap: it meets you where you are, explains the *why* behind every move, and then — on systems you're authorized to touch — helps you actually carry the work out.

Three things, one platform:

- **Teach** — Structured, hands-on learning. Not video courses you half-watch, but labs, walkthroughs, and an AI tutor that adapts to what you already understand and fills the holes you don't know you have.
- **Guide** — A copilot for real engagements. You describe the target and the goal; it reasons through methodology, suggests the next sensible step, flags what you're missing, and keeps you inside scope.
- **Execute** — For the parts that are safe to automate, it runs them: reconnaissance, parsing, triage, report drafting. You stay the operator; it handles the toil.

---

## Why this exists

Security work has a steep, lonely learning curve. The good knowledge is scattered across write-ups, man pages, Discord servers, and the heads of people who don't have time to mentor you. Meanwhile the tools are powerful but dumb — they do exactly what you tell them and nothing to help you understand the result.

An AI that genuinely knows this domain can be the mentor, the second pair of eyes, and the tireless assistant at the same time. That's the whole idea.

## Who it's for

- People learning offensive and defensive security who want to go faster without skipping the fundamentals.
- Practitioners who want a knowledgeable copilot on authorized engagements and CTFs.
- Blue teams and defenders who want help triaging, understanding, and documenting what they're seeing.
- Educators who want a lab environment that explains itself.

## Authorized use only

This is the line that doesn't move. HansenAI is built for **authorized security testing, defensive work, education, and CTF/research** settings. Every execution-capable feature is scoped, logged, and gated behind an explicit statement of authorization. It will help you learn how attacks work so you can stop them — it will not help you attack systems you have no right to touch.

If you can't point to permission, the platform assumes you don't have it.

## Project shape

HansenAI is **open core**. The platform, the teaching engine, the guidance framework, and the core tooling are open source. Some hosted and enterprise capabilities will live in separate, non-open tiers so the project can fund its own development. The split is spelled out as it lands — nothing that's open today gets quietly pulled.

```
hansenai/
├── core/        the execution engine — the runtime that plans, runs, and reports on tasks
├── learn/       the teaching system — curriculum, labs, and the adaptive tutor
├── guide/       the engagement copilot — methodology, step suggestion, scope enforcement
├── agents/      AI agent definitions and the tools they're allowed to reach for
├── docs/        vision, architecture, and roadmap
└── examples/    worked end-to-end scenarios
```

## Status

Early. This repository is the foundation — the structure, the principles, and the direction. Features land from here. Watch the [roadmap](docs/roadmap.md) for what's next.

## License

Open-source components are licensed under [Apache 2.0](LICENSE). See [SECURITY.md](SECURITY.md) for responsible-use and vulnerability-reporting expectations.

---

*Named HansenAI. Built to make good security skills less rare.*
