# 🗄️ The Kodex Stack

## Overview

The Kodex Stack is the core architecture of Kodex OS. It defines the four layers that move information from raw physical capture to long-term digital and physical storage. Each layer has a distinct role, and each feeds into the next.

The Stack is designed around a simple principle: **capture freely, organize intentionally, store redundantly.**

---

## Layer 0 — Raw Capture

### Field Notes — Intake Layer

Field Notes memo books are the intake layer of the entire system. This is where everything begins — observations, ideas, sketches, questions, half-formed thoughts, lists, anything. There is no filter here. Nothing is too small or too rough for this layer.

This layer is intentionally unstructured. Its job is not to organize — it is to capture. The structure comes later, in the layers above.

> 💡 Think of Field Notes as the raw feed. Everything worth keeping starts here.

**Characteristics:**
- Physical, always on hand
- No format requirements — write freely
- Multiple memo books may run concurrently (daily log, research, etc.)
- Relevant pages are scanned at end of day when content was documented

---

## Layer 1 — Knowledge Base & Digital Bridge

### LLM Wiki — Bridge Layer

The LLM Wiki is the bridge layer — it digitizes, structures, and connects the physical world of Field Notes to the digital world of Obsidian and beyond. This layer has two halves: an immutable raw capture half where scanned and transcribed Field Notes pages live, and an LLM-generated wiki half that organizes and interlinks that raw content.

The LLM reads from raw, writes to the wiki, and never modifies raw. The wiki does not have a note limit, supports true bidirectional linking, and uses an LLM to actively extract meaning from raw scans rather than just storing them as images.

> 💡 The LLM Wiki is where raw thinking becomes organized knowledge.

**Vault structure:**
```
Kodex Wiki/
├── raw/         ← Scanned & transcribed Field Notes pages (immutable)
├── wiki/        ← LLM-generated, LLM-maintained
│   ├── index.md   (catalog of all wiki pages)
│   └── log.md     (chronological record of ingests, queries, lints)
└── SCHEMA.md    ← Rules the LLM follows when maintaining the wiki
```

**Characteristics:**
- Built in Obsidian
- `raw/` is the immutable input layer — scanned and transcribed Field Notes pages, never modified by the LLM
- `wiki/` is the LLM-generated output layer — fully owned and maintained by the LLM
- Each Field Notes memo book maps 1:1 to a folder under `raw/` (e.g. `FNvo-001/` or `Rvo-001`)
- Pages are scanned at end of day and processed through an LLM for extraction, tagging, and interlinking
- `index.md` and `log.md` provide navigation and chronology — the LLM updates them on every ingest
- `SCHEMA.md` defines the rules the LLM follows when maintaining the wiki — the configuration file that makes the LLM a disciplined wiki maintainer rather than a generic chatbot
- Notes are interlinked using Obsidian's graph and backlink features
- Serves as the digital twin of the physical archive (Layer 3)

---

## Layer 2 — Project Intelligence

### Notion — Operations Layer

Notion is the operational layer of Kodex OS. It can really be any note-taking application. It could merely be another vault in Obsidian. This is where ideas and knowledge from the LLM Wiki get developed into projects, plans, and structured thinking. Notion is not a storage system — it is a thinking and planning environment.

When something captured in Field Notes has been processed and structured in the LLM Wiki, it can then graduate into a project or initiative worth developing; it moves into Notion for organization and iteration, pulling from the LLM Wiki as its knowledge base.

> 💡 Notion is the command center. The LLM Wiki feeds it intel — ideas become projects here.

**Characteristics:**
- Organizes project ideas and active initiatives
- Pulls knowledge and insights from the LLM Wiki (Layer 1)
- Not used for raw capture or long-term archival storage

---

## Layer 3 — The Archive

### Long-Term Memory — Storage Layer

When a Field Notes memo book is filled, it enters the Archive. Each book is placed in a labeled envelope with all relevant metadata documented on the cover — dates, topics, volume number, and any other pertinent identifiers. Books are then filed and organized for long-term physical storage.

By the time a book reaches the Archive, its digital counterpart in the LLM Wiki should already be complete. The physical book and the digital record together form the permanent record.

> 💡 The Archive is the final resting place. Nothing gets lost — it just gets filed.

**Characteristics:**
- Labeled envelopes with metadata on the cover
- Filed chronologically or by subject
- LLM Wiki entry should be complete before archiving
- Corresponds directly to Epoch I – Archive in Phase IV

---

## Layer 4 — Project Management (Trello)

### Task Tracking — Execution Layer

Trello is the execution layer of Kodex OS. While Notion handles project intelligence — the thinking, planning, and structuring of ideas — Trello is where those projects become action. The timeline lives in Notion; Trello manages execution.

I break my timeline, for projects, down into Phases, Epochs, Goals, Micro-Goals, and Tasks. I normally have four phases, and however many of the rest is necessary for each phase, and a pre-phase if necessary.

Each Trello board maps one-to-one with a project. Phases and Epochs are surfaced as card labels, keeping the full hierarchy visible across the entire project in a single view. Goal is never a label — it is always described in the title of each card alongside the Micro-Goal.

> 💡 Trello is the engine room. One board, one project. Phases and Epochs ride as labels. The timeline lives in Notion.

**Board structure:**
- One Trello board = one project
- Phases and Epochs are surfaced as card labels — Goal is never a label
- Each card represents one Micro-Goal, titled: *Goal # | M#: Title of Micro-Goal*
- Checklist items within each card map directly to Tasks (Task I, Task II, etc.)

**Card label system:**
- Phase label — e.g. Phase 0, Phase 1
- Epoch label — e.g. Epoch 1, Epoch 2

**Kanban columns (left → right):**

`Backlog` → `To Do` → `Doing` → `Review / Code Review` → `Testing` → `Done`

**Characteristics:**
- Runs alongside Notion
- Projects are conceived and planned in Notion; executed in Trello
- Used for active project execution, not planning or archival
- Task completion in Trello reflects progress defined in Notion

---

## The Flow

```
Layer 0: Field Notes  →  Layer 1: LLM Wiki  →  Layer 2: Notion
              ↓                                         ↕
   Layer 3: The Archive  ←→  LLM Wiki (Digital Twin)  Layer 4: Trello
```

Information flows upward from capture to organization. Field Notes feeds the LLM Wiki first — raw capture becomes structured knowledge. Notion then pulls from that knowledge base for project intelligence and planning. The LLM Wiki acts as the connective tissue throughout, bridging the physical capture layer to the digital project layer, and permanently mirroring the physical archive. Trello sits alongside Notion as the execution arm — the timeline lives in Notion, Trello manages execution.
