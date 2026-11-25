# Architecture (draft)

This is a living sketch of how the pieces fit. It will change as the platform is built — treat it as direction, not contract.

## The three surfaces

HansenAI presents three experiences over one shared brain:

```
                 ┌─────────────────────────────────────────┐
                 │                 User                      │
                 └───────────────┬───────────────────────────┘
                                 │
        ┌────────────────┬───────┴────────┬────────────────┐
        │                │                │                 │
   ┌────▼────┐      ┌────▼────┐      ┌────▼────┐
   │  Learn  │      │  Guide  │      │ Execute │
   │ (teach) │      │(copilot)│      │ (do)    │
   └────┬────┘      └────┬────┘      └────┬────┘
        │                │                │
        └────────────────┴───────┬────────┘
                                 │
                         ┌───────▼────────┐
                         │   Core engine   │
                         │ reasoning · tools│
                         │ memory · policy  │
                         └───────┬─────────┘
                                 │
                   ┌─────────────┴──────────────┐
                   │  Authorization & audit gate │
                   └─────────────┬──────────────┘
                                 │
                        external tools / labs
```

## Components

### `core/` — the engine
The runtime that plans a task, decides which capabilities to use, keeps context and memory, and routes everything through the policy gate. Model-backed reasoning lives here.

### `learn/` — the teaching system
Curriculum, labs, and the adaptive tutor. Tracks what a learner understands and chooses what to teach next. Content is data; the tutor is logic over it.

### `guide/` — the engagement copilot
Methodology knowledge, step suggestion, and checklists. Given a target and a goal (both authorized), it reasons about sensible next steps and flags gaps and scope risks.

### `agents/` — agent and tool definitions
Named agents with bounded tool access. Each agent declares what it's for and what it's allowed to reach. This is where new capabilities plug in.

### Authorization & audit gate
Every execute-path action passes through here. No authorization on record → the action doesn't run. Everything that does run is logged. This is deliberately not optional and not bypassable from feature code.

## Non-negotiables

- The gate sits between the engine and anything that touches the outside world.
- Agents cannot grant themselves capabilities they weren't given.
- Execution is auditable after the fact.

## Open questions

- Which model backends to support, and how to keep the platform model-agnostic.
- How labs are packaged and sandboxed.
- How learner progress is stored and kept private.

These get answered as the code lands.
