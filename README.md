# UX LLM Wiki

Simple workspace to run UX research with an LLM, based on Andrej Karpathy's LLM Wiki pattern.

## Start here (most important)

1. Put one source file in `raw/` (for example `raw/objective.md`).
2. ask your LLM, I recommend to use Claude Code or Cursor:

```text
make wiki
```

3. Review output and approve.

## How it works

- Put source notes in `raw/`
- Ask the LLM to analyze them
- Save synthesized knowledge in `wiki/`

## Main folders

- `raw/`: all your ux research goes here, the LLM will never touch the files inside this folder
- `wiki/`: summaries, themes, linked pages, and research log. This will be handled by the LLM.

## Quick workflow

1. Add a source file in `raw/`
2. Ask the LLM to ingest it
3. Approve the summary
4. Save/update pages in `wiki/`
5. Repeat for the next source

## Prompts to use with the LLM

### Ingest one file

```text
Read `raw/<file>.md`.
Extract key insights, assumptions, open questions, and UX actions.
Propose which wiki pages to create or update.
Wait for my approval before writing.
```

### Analyze competitors

```text
Analyze `raw/competitors.md`.
Return strengths, weaknesses, UX patterns to copy, and patterns to avoid.
End with 5 concrete recommendations.
```

### Synthesize user interviews

```text
Read all files in `raw/user-interviews/`.
Cluster findings into themes, goals, and pain points.
Return top 5 user problems with source-backed evidence.
```

### Update personas

```text
Use `raw/user-personas.md` and interview evidence.
Refine personas with goals, pain points, decision triggers, and UX implications.
Mark assumptions that are not evidence-backed.
```

### Audit the wiki

```text
Audit `wiki/` for contradictions, orphan pages, missing links, and outdated claims.
Return a prioritized fix list.
```

## Mini prompt template

```text
Task: <ingest | synthesize | audit | answer>
Scope: <files/folders>
Output: <bullets | table | wiki page draft>
Rules: cite sources, mark assumptions, no invented facts
```

## Quality check

Before accepting output, verify:

- claims are source-backed
- assumptions are clearly labeled
- recommendations are concrete
- next research steps are explicit
