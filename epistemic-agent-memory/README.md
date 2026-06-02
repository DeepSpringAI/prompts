# Epistemic Agent Memory (EAM)

Structured, versioned, confidence-aware, and time-aware project memory in a Git repo using a local-first `memory/` tree (canonical docs, YAML claims, sessions, retrievals).

| File | Use |
|------|-----|
| [EAM_ASSISTANT.md](EAM_ASSISTANT.md) | Full assistant prompt — paste into AGENTS.md, Cursor rules, custom GPT, or Codex system instructions |
| [custom-instructions-short.md](custom-instructions-short.md) | Short version for ChatGPT **Custom Instructions** |

## Share links (public repo)

After this repository is public on GitHub, share the rendered or raw URLs, for example:

```text
https://github.com/DeepSpringAI/prompts/blob/main/epistemic-agent-memory/EAM_ASSISTANT.md
https://raw.githubusercontent.com/DeepSpringAI/prompts/main/epistemic-agent-memory/EAM_ASSISTANT.md
https://github.com/DeepSpringAI/prompts/blob/main/epistemic-agent-memory/custom-instructions-short.md
```

## Bootstrap in a target repo

```bash
epmem init
```

Or create the `memory/` tree manually (see [EAM_ASSISTANT.md](EAM_ASSISTANT.md#repo-bootstrap)).

## Related

- [github-repo-memory/](../github-repo-memory/) — curated `.memory/` markdown protocol (complementary; EAM adds atomic YAML claims and temporal epistemics)
