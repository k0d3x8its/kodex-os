# 🖥️ Kodex OS

> A personal operating system for capturing, organizing, and preserving knowledge — bridging the physical and digital world.

---

## What is Kodex OS?

Kodex OS is a modular personal knowledge system built around the belief that the best thinking happens on paper, but the best *organization* happens digitally. It bridges a physical capture practice with digital tools — without requiring any single tool to make the whole system work.

The system is designed to be **taken apart and reassembled**. If you don't use Obsidian, remove it. If you don't use Notion, remove it. The core of Kodex OS — Field Notes and a physical archive — stands on its own.

---

## The Kodex Stack

The Stack is the architecture of Kodex OS. It defines five layers, numbered by dependency — each layer feeds the next. Layer 0 must exist before anything else can function.

```
Layer 0: Field Notes  →  Layer 1: LLM Wiki  →  Layer 2: Notion
              ↓                                         ↕
   Layer 3: The Archive  ←→  LLM Wiki (Digital Twin)  Layer 4: Trello
```

| Layer | Name | Layer Type |
|---|---|---|
| 0 | Field Notes | Intake Layer |
| 1 | LLM Wiki | Bridge Layer |
| 2 | Notion | Operations Layer |
| 3 | The Archive | Storage Layer |
| 4 | Trello | Execution Layer |

---

### Layer 0 — Field Notes *(Intake Layer)*
The intake layer of the entire system. This is where everything begins — observations, ideas, sketches, questions, half-formed thoughts, lists, anything. There is no filter here. This layer is intentionally unstructured. Its job is not to organize — it is to capture.

**Tools:** [Field Notes memo books](https://fieldnotesbrand.com), pen, archival ink (optional)
**Modular:** This is the only non-optional layer. Everything else depends on it.

---

### Layer 1 — LLM Wiki / Obsidian *(Bridge Layer)*
The bridge between physical and digital. This layer has two halves: an immutable **raw capture** half where scanned and transcribed Field Notes pages live, and an LLM-generated **wiki** half that organizes and interlinks that raw content. The LLM reads from `raw/`, writes to `wiki/`, and never modifies raw.

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
- `raw/` is the immutable input layer — scanned and transcribed Field Notes pages, never modified by the LLM
- `wiki/` is the LLM-generated output layer — fully owned and maintained by the LLM
- Each Field Notes memo book maps 1:1 to a folder under `raw/` (e.g. `field-notes-vol-001/`)
- `index.md` and `log.md` provide navigation and chronology — the LLM updates them on every ingest
- `SCHEMA.md` defines the rules the LLM follows when maintaining the wiki
- Notes are interlinked using Obsidian's graph and backlink features
- Serves as the digital twin of the physical archive (Layer 3)

**Tools:** [Obsidian](https://obsidian.md), LLM (e.g. Claude)
**Optional:** If removed, the system operates in the physical layer only. Phases still function — the LLM Wiki steps are simply skipped.

---

### Layer 2 — Notion *(Operations Layer)*
The operational layer. When knowledge from the LLM Wiki matures into a project or initiative worth developing, it moves into Notion for organization, planning, and iteration. Notion is not a storage system — it is a thinking and planning environment that pulls from the LLM Wiki as its knowledge base. This could also be another Obsidian vault or any note-taking application of your choice.

**Tools:** [Notion](https://notion.so) (or equivalent)
**Optional:** Can be replaced with any project management or note-taking tool, or removed entirely.

---

### Layer 3 — The Archive *(Storage Layer)*
When a Field Notes memo book is filled, it enters the Archive. Each book is placed in a labeled envelope with metadata documented on the cover — dates, topics, volume number, and any other pertinent identifiers. By the time a book reaches the Archive, its LLM Wiki entry (if used) should already be complete. The physical book and digital record together form the permanent record.

**Materials:** Envelopes, archival pen for labeling
**Optional:** The Archive is the natural conclusion of a filled memo book. It can be as simple as a labeled box.

---

### Layer 4 — Trello *(Execution Layer)*
The execution layer. While Notion handles project intelligence — the thinking, planning, and structuring of ideas — Trello is where those projects become action. The timeline lives in Notion; Trello manages execution.

Each Trello board maps one-to-one with a project. Phases and Epochs are surfaced as card labels, keeping the full hierarchy visible in a single view.

**Board structure:**
- One board = one project
- Phases and Epochs are surfaced as card labels — Goal is never a label
- Each card represents one Micro-Goal, titled: `Goal # | M#: Title of Micro-Goal`
- Checklist items within each card map directly to Tasks (Task I, Task II, etc.)

**Kanban columns (left → right):**
`Backlog → To Do → Doing → Review → Testing → Done`

**Tools:** [Trello](https://trello.com)
**Optional:** Can be replaced with any task tracking tool, or removed if Notion handles execution.

---

## The Phases

Kodex OS moves through four phases. These are fluid — not every piece of captured information will move through all of them.

| Phase | Name | Description |
|---|---|---|
| Prep | Build | Gather materials, set up your memo books |
| I | Observe & Document | Capture everything in Field Notes |
| II | Data Extraction | Review and extract what's worth pursuing further |
| III | Analysis & Processing | Analyze, filter, and route information |
| IV | Archiving | File completed memo books; close digital records |

### Prep Phase — Build
Gather your materials and set up your memo books. Assign each book a role (daily log, research, etc.) and configure your tools before you start capturing.

### Phase I — Observe & Document
The core of the system. Carry your Field Notes memo book and write down what you observe, think, and encounter. No format requirements. This is Layer 0 in practice.

### Phase II — Data Extraction
After documenting, review what you've captured. Decide what's worth pursuing further. Transfer relevant content from your general memo book into a dedicated Field Notes notebook for that subject.

> **LLM Wiki (optional):** This is the natural point to open a dedicated Wiki entry for the subject being extracted — running digitally in parallel with the physical notebook. If not using the LLM Wiki, this phase operates entirely in Layer 0 and nothing changes.

### Phase III — Analysis & Processing
Analyze what you've extracted. Filter for relevance. Decide where it goes — does it stay on your person, get archived, or is it done? The core question: *Am I done? Is it ready to archive?*

> **LLM Wiki (optional):** This phase also includes reviewing and refining the corresponding Wiki entry — confirming notes are accurate, tagged correctly, and cross-linked. The core question is the same regardless of your stack.

### Phase IV — Archiving
When a memo book is filled, archive it. Fill out the envelope cover with all relevant metadata and file it. If using the LLM Wiki, the digital record should be complete before the physical book is archived.

---

## Setup Guide

### What You Actually Need (Minimum)
- [ ] Field Notes memo books (at least 2 — one general, one research)
- [ ] A pen
- [ ] Envelopes for archiving
- [ ] Archival ink (optional but recommended for longevity)

### Adding the LLM Wiki — Layer 1 (Optional)
1. Install [Obsidian](https://obsidian.md) and create a new vault called `Kodex Wiki`
2. Create the two top-level directories: `raw/` and `wiki/`
3. Inside `raw/`, create a folder for your active memo book (e.g. `field-notes-vol-001/`)
4. Inside `wiki/`, create empty `index.md` and `log.md` files — the LLM will populate them
5. Create a `SCHEMA.md` at the vault root that defines how the LLM should maintain the wiki *(see `/templates/schema.md`)*
6. At the end of each day you've written something, scan the relevant pages of your active memo book and drop them into the appropriate `raw/` subfolder
7. Pass the scans to an LLM (e.g. Claude) — it transcribes into `raw/`, then writes structured pages into `wiki/` and updates `index.md` and `log.md`
8. Review the wiki entries; the LLM owns the wiki, you own the review

### Adding Notion — Layer 2 (Optional)
1. Create a Notion account at [notion.so](https://notion.so)
2. Use the Kodex OS workspace as your command center
3. Develop ideas and knowledge from the LLM Wiki into projects and active initiatives here

### Adding the Physical Archive — Layer 3
1. When a memo book is full, gather an envelope
2. On the cover, document: dates covered, volume number, primary topics, any relevant identifiers
3. File chronologically or by subject
4. If using the LLM Wiki, confirm the digital record is complete before sealing

### Adding Trello — Layer 4 (Optional)
1. Create a [Trello](https://trello.com) account
2. Create one board per project
3. Set up card labels for Phases and Epochs
4. Use the Kanban column structure: `Backlog → To Do → Doing → Review → Testing → Done`
5. Each card = one Micro-Goal; checklist items = Tasks

---

## Modularity

Kodex OS is designed so any layer except Layer 0 can be removed without breaking the rest.

| Removed Layer | Impact |
|---|---|
| LLM Wiki — Layer 1 | No digital bridge. Physical archive stands alone. Scanning workflow dropped. Notion loses its knowledge base feed. |
| Notion — Layer 2 | No project organization layer. Ideas stay in the LLM Wiki or Field Notes. |
| Trello — Layer 4 | No dedicated execution layer. Task tracking moves into Notion or is dropped. |
| Layers 1, 2, & 4 | Pure analog system. Field Notes → Physical Archive. Fully self-contained. |

---

## Versioning & Changelog

This system evolves. See `CHANGELOG.md` for a full history of updates to Kodex OS.

---

## Repository Structure

```
kodex-os/
│
├── README.md                        ← You are here
├── CHANGELOG.md                     ← Version history
│
├── stack/
│   ├── layer-0-field-notes.md
│   ├── layer-1-llm-wiki.md
│   ├── layer-2-notion.md
│   ├── layer-3-archive.md
│   └── layer-4-trello.md
│
├── phases/
│   ├── prep-phase-build.md
│   ├── phase-1-observe-document.md
│   ├── phase-2-data-extraction.md
│   ├── phase-3-analysis-processing.md
│   └── phase-4-archiving.md
│
└── templates/
    ├── llm-wiki-note.md
    └── schema.md
```

---

## Philosophy

> *Capture freely. Organize intentionally. Store redundantly.*

Kodex OS does not prescribe what you write or think. It only asks that you write it down, decide what matters, and keep what's worth keeping.

---

*Kodex OS is a living document. It changes as the system changes.*
