# GitHub Repo Memory Protocol Prompt

When I refer to a GitHub repository as “repo memory,” treat that repository as a durable, versioned project-memory layer.

The goal is to use GitHub as a shared long-term memory system for AI-assisted work across ChatGPT, Claude, Codex, Cursor, Copilot, and future tools.

Do not treat the repository as a raw chat archive. Treat it as a curated project knowledge base.

---

## Core behavior

When I say:

> Read repo memory first.

You should:

1. Identify the relevant GitHub repository.
2. Look for a memory protocol file at:

   ```text
   .memory/AI_MEMORY_PROTOCOL.md
   ```

3. If that file exists, read it and follow it.

4. Then read the relevant memory files, especially:

   ```text
   .memory/working-context.md
   .memory/decisions.md
   .memory/assumptions.md
   .memory/open-questions.md
   .memory/glossary.md
   .memory/conversation-log.md
   .memory/artifacts.md
   .memory/next-actions.md
   ```

5. If the repo has project-specific memory, also check:

   ```text
   .memory/projects/<project-slug>/working-context.md
   .memory/projects/<project-slug>/decisions.md
   .memory/projects/<project-slug>/assumptions.md
   .memory/projects/<project-slug>/open-questions.md
   .memory/projects/<project-slug>/glossary.md
   .memory/projects/<project-slug>/conversation-log.md
   .memory/projects/<project-slug>/artifacts.md
   .memory/projects/<project-slug>/next-actions.md
   ```

6. Use the memory as context, but do not treat it as unquestionable truth.

7. Clearly flag stale, uncertain, contradictory, or unverified memory.

---

## Standard memory structure

Prefer this structure in every repo:

```text
.memory/
  AI_MEMORY_PROTOCOL.md
  working-context.md
  decisions.md
  assumptions.md
  open-questions.md
  glossary.md
  conversation-log.md
  artifacts.md
  next-actions.md
```

For repos with multiple projects or workstreams, use:

```text
.memory/
  AI_MEMORY_PROTOCOL.md
  global-context.md

.memory/projects/<project-slug>/
  working-context.md
  decisions.md
  assumptions.md
  open-questions.md
  glossary.md
  conversation-log.md
  artifacts.md
  next-actions.md
```

---

## Meaning of each memory file

### `working-context.md`

The current best understanding of the project.

Use this for:

- current project summary
- goals
- scope
- business context
- technical context
- current architecture
- important constraints

---

### `decisions.md`

Durable decisions and rationale.

Each decision should include:

- date
- decision
- rationale
- status
- impact
- superseded status, if applicable

Example:

```md
## 2026-05-30 — Use GitHub as project memory

Decision:
Use the repository as the durable project-memory layer for AI-assisted work.

Rationale:
GitHub provides versioning, searchability, portability, and cross-tool access.

Status:
Active.

Impact:
Future AI sessions should read repo memory before making project-specific recommendations.
```

---

### `assumptions.md`

Assumptions that are useful but not fully verified.

Each assumption should include:

- assumption
- confidence
- source
- validation needed
- status

Example:

```md
## Assumption — Customer concentration

Assumption:
The project may have high dependency on one major customer.

Confidence:
Medium.

Source:
Discovery conversation.

Validation needed:
Review actual revenue data or customer contracts.

Status:
Unverified.
```

---

### `open-questions.md`

Questions that still need investigation.

Use this for:

- unresolved business questions
- technical unknowns
- validation backlog
- missing data
- stakeholder questions

---

### `glossary.md`

Terms, acronyms, domain vocabulary, and project-specific definitions.

Each entry should be concise and searchable.

Example:

```md
## HSE

Health, Safety, and Environment.

Used for safety, environmental protection, audits, training, risk assessments, and compliance.
```

---

### `conversation-log.md`

A dated, curated summary of important conversations.

Do not store full raw transcripts unless I explicitly ask.

Use this format:

```md
## 2026-05-30 — Topic title

Summary:
Brief summary of what was discussed.

Key points:
- Point 1
- Point 2
- Point 3

Decisions:
- Decision made, if any.

Open questions:
- Question 1
- Question 2.

Artifacts:
- Path or link to generated artifact, if any.
```

---

### `artifacts.md`

Index of generated or important files.

Use this for:

- presentations
- documents
- diagrams
- reports
- datasets
- notebooks
- code artifacts
- exports

Each artifact should include:

- path
- description
- date
- status
- source or context

Example:

```md
## Business model presentation

Path:
`presentations/business-model/index.html`

Description:
Reveal.js presentation explaining the project’s business model and operating process.

Status:
Current working version.

Created:
2026-05-30.
```

---

### `next-actions.md`

Pending tasks, owners, and status.

Use this format:

```md
## Action item title

Owner:
TBD.

Status:
Open.

Due:
TBD.

Context:
Why this action matters.
```

---

## Memory update behavior

When I say:

> Remember this.

or:

> Remember this in the repo.

You should:

1. Convert the conversation into concise, curated memory.
2. Decide which memory file should be updated.
3. Do not store raw chat text by default.
4. Preserve date, source, and context.
5. Mark confidence where appropriate.
6. Ask only if the target repo or project is unclear.
7. If repository write access is available and I ask you to commit, update the relevant files and commit them.

---

## Commit behavior

When I say:

> Commit memory.

or:

> Summarize today’s memory and commit it.

You should:

1. Review the current conversation.
2. Extract durable information:

   - facts
   - decisions
   - assumptions
   - open questions
   - glossary terms
   - next actions
   - artifact references

3. Update the appropriate memory files.
4. Commit the changes to the repository.
5. Use a clear commit message.

Recommended commit messages:

```text
Update project memory
Add AI memory protocol
Update working context
Add conversation memory summary
Update decisions and open questions
Add glossary entries
```

After committing, report:

```text
Updated files:
- path/to/file.md
- path/to/other-file.md

Commit:
<commit-sha>
```

---

## Retrieval behavior

When answering project-specific questions, prefer this order:

1. Current conversation context
2. Repo memory files
3. Repo source files / docs / code
4. Uploaded files
5. Public web sources, when current or external information is needed

If repo memory conflicts with source files or newer evidence:

- explain the conflict
- identify the likely current source of truth
- suggest a memory update

---

## Memory quality rules

Memory entries should be:

- concise
- dated
- source-aware
- searchable
- easy for another AI to understand
- free of unnecessary transcript noise

Prefer this:

```md
## 2026-05-30 — Repository memory standard

Decision:
Use `.memory/` as the standard location for AI project memory.

Rationale:
A consistent location makes it easy for different AI tools to discover and use memory.

Status:
Active.
```

Avoid this:

```md
The user said many informal things and then the assistant explained a lot of options...
```

---

## Security and privacy rules

Never commit:

- passwords
- API keys
- access tokens
- private keys
- raw credentials
- full personal data
- confidential customer records
- raw financial exports
- regulated data
- sensitive legal material unless explicitly approved
- full private transcripts unless explicitly approved

If something sensitive is important, store a safe summary and point to the approved secure location.

Example:

```md
Sensitive customer revenue data exists in the approved finance system.
Do not commit raw export files to this repo.
```

---

## Conflict and supersession rules

If memory conflicts with new information:

1. Do not silently overwrite history.
2. Add a superseding note.
3. Keep the old decision if it explains historical context.
4. Mark the current source of truth clearly.

Example:

```md
Status:
Superseded on 2026-06-02 by finance export review.

Current source of truth:
`reports/finance/revenue-summary-2026-06.md`
```

---

## Standard commands I may use

When I say any of the following, follow the memory protocol:

### Start / retrieval

```text
Read repo memory first.
```

```text
Use the repo memory before answering.
```

```text
Brief yourself from repo memory.
```

```text
Load project memory.
```

### Memory update

```text
Remember this.
```

```text
Remember this in the repo.
```

```text
Update working context.
```

```text
Add this as a decision.
```

```text
Add this as an assumption.
```

```text
Add this to the glossary.
```

```text
Add this to open questions.
```

```text
Add this as a next action.
```

```text
Add this artifact to memory.
```

### End of session

```text
Summarize today’s memory.
```

```text
Summarize today’s memory and commit it.
```

```text
Commit memory.
```

```text
Prepare a memory handoff.
```

```text
Prepare a memory handoff for another AI.
```

---

## Default behavior when uncertain

If the repository is unclear, ask which repo to use.

If the project/workstream is unclear, ask which project slug to use.

If the information may be sensitive, do not commit it immediately. Ask whether to store a safe summary instead.

If a file does not exist, create it using the standard memory structure.

If memory exists but is stale, use it carefully and say what needs validation.

---

## My preferred convention

Use this default memory location unless I specify otherwise:

```text
.memory/
```

For multi-project repos, use:

```text
.memory/projects/<project-slug>/
```

Use Markdown files for memory unless there is a clear reason to use another format.

Keep memory curated, practical, and useful for future AI sessions.
