# 🗂️ Prompt Knowledge Base

A structured, version-controlled catalog of well-thought-out prompts for work and learning. Each
prompt has a clearly defined purpose, a ready-to-copy template, parameterized input variables, a
tested usage example, and an explanation of the design decisions behind it.

This repository started from a simple observation: the good prompts I write ad hoc in conversations
with AI tools disappear into chat history, and a week later I'm reinventing them from scratch.
Instead — cataloging, parameterization, and reuse.

## Why this repository exists

The goal wasn't to collect as many "interesting prompts" as possible. The goal was to build a
**system** where:

- every prompt can be reused across different situations without rewriting it from zero,
- someone other than me (a new team member, or future-me in six months) can understand a prompt
  without asking for context,
- it's visible not just *what* a prompt does, but *why* it's built the way it is.

The full explanation of the design principles is in [`docs/METODOLOGIA.md`](docs/METODOLOGIA.md)
(Polish — methodology document).

## Repository structure

```
prompt-knowledge-base/
├── README.md                          — this file (English)
├── prompts/
│   ├── praca/                         — 4 prompts for everyday work
│   ├── nauka/                         — 5 prompts for learning and research
│   ├── dokumentacja/                  — 3 prompts for writing documentation
│   └── automatyzacja/                 — 3 prompts for analyzing and building automation
├── docs/
│   ├── METODOLOGIA.md                 — prompt design principles (meta-level)
│   └── PRZYGOTOWANIE_DO_ROZMOWY.md    — personal notes, not part of the "product"
│ examples/                          — space for extra material (screenshots, longer case studies)
└──images/                              - obsidian_graph.png
```

*Note: folder and file names are kept in Polish (praca = work, nauka = learning, dokumentacja =
documentation, automatyzacja = automation) to match the original repository structure; prompt
content is also in Polish.*

## Prompt catalog

### 💼 Work
| Prompt | What it's for |
|---|---|
| [Analyzing Excel data with AI](prompts/praca/analiza-danych-excel.md) | Extracting business insights from a spreadsheet — data quality checks, cut proposals, formulas, charts |
| [Code review for a specific goal](prompts/praca/code-review.md) | Code review focused on a single dimension (security / performance / readability) instead of a generic one |
| [Meeting notes summary](prompts/praca/podsumowanie-notatek-ze-spotkania.md) | Turns messy notes into decisions, action items, and open questions — without inventing facts |
| [Drafting emails with tone control](prompts/praca/redagowanie-emaili.md) | Difficult/formal emails in a controlled, middle register — with two variants to choose from |

### 📚 Learning
| Prompt | What it's for |
|---|---|
| [Explaining a concept at 3 levels](prompts/nauka/wyjasnienie-koncepcji.md) | A new concept explained from an analogy up to expert level, with a comprehension-check question |
| [Generating flashcards (spaced repetition)](prompts/nauka/tworzenie-fiszek.md) | Source material → Anki-ready flashcards, emphasizing application questions, not just definitions |
| [Socratic tutor](prompts/nauka/tutor-sokratejski.md) | Learning through guiding questions — the model deliberately withholds the direct answer |
| [Learning plan for a goal and deadline](prompts/nauka/plan-nauki.md) | Prioritizing material with the Pareto method instead of studying everything sequentially |
| [Summarizing an article/documentation](prompts/nauka/podsumowanie-artykulu.md) | A summary focused on practical application, with explicit source limitations |

### 📄 Documentation
| Prompt | What it's for |
|---|---|
| [Technical project documentation](prompts/dokumentacja/dokumentacja-techniczna.md) | Documentation focused on "why it was built this way," not just "what the code does" |
| [README.md generator](prompts/dokumentacja/generator-readme.md) | A standardized process for writing a README for a portfolio/course project |
| [API documentation](prompts/dokumentacja/dokumentacja-api.md) | Consistent endpoint documentation ready for Postman/Swagger |

### ⚙️ Automation
| Prompt | What it's for |
|---|---|
| [Process analysis for automation](prompts/automatyzacja/analiza-procesu-do-automatyzacji.md) | A systematic assessment of which part of a repetitive process is worth automating first |
| [Instructions → working script](prompts/automatyzacja/instrukcja-na-skrypt.md) | Turning a written manual procedure into a working script, surfacing hidden assumptions |
| [Designing a prompt chain](prompts/automatyzacja/pipeline-promptow-chain.md) | Breaking a complex LLM task into stages with one output type per stage, instead of one large prompt |

## How to use this base

1. Find the prompt that matches your situation in the table above.
2. Copy the content from the **Prompt** section of that file.
3. Fill in the variables marked `{like_this}` — each file lists them under **Zmienne do
   dostosowania** (Variables to customize).
4. Check the **Wskazówki** (Tips) section — it contains notes that genuinely affect answer quality.

Each prompt is a standalone markdown file — it can easily be moved to any other tool (Notion, an
internal wiki, a different AI model) without depending on the rest of the repository.

## Principles behind the design (summary)

- **One goal per prompt** — instead of a universal "do everything," each prompt has a narrowly
  defined task.
- **Parameterized input** — variables instead of a hardcoded prompt, so it can be reused.
- **Explicit constraints wherever a hallucination would be costly** (e.g., a ban on inventing
  deadlines in a meeting summary).
- **A tested example for every prompt** — no prompt was added without a real test run.
- **Cross-linking between prompts** — the base is a graph of related tools, not a flat list.

The full, detailed explanation of each of these principles, with reasoning:
[`docs/METODOLOGIA.md`](docs/METODOLOGIA.md).

## Obsidian version

The repository doubles as a ready-to-use Obsidian vault — the `[[wikilinks]]` in each prompt's
"Powiązane prompty" (Related prompts) section automatically build a visual graph of connections.
Starting point after opening the folder as a vault:
[`Indeks - Baza Promptów.md`](Indeks%20-%20Baza%20Promptów.md).

## Status and further development

This is a living knowledge base — a new prompt gets added here whenever I notice I'm formulating
the same request to an AI tool for the third time. Planned extensions: adding real screenshots of
selected prompts in action under `examples/`, and prompts specific to the tools used in a
particular work environment.

---
*Maintained as a personal knowledge base — feel free to fork and adapt it to your own needs.*