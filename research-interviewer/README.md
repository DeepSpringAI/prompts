# Research Interviewer

Generic research interviewer with **SMART SETUP**, pre-interview setup gate, and **silent** evidence capture during ChatGPT voice (no spoken `Captured:` lines). Post-interview summary emits all `Captured:` lines from the transcript and internal log.

| File | Use |
|------|-----|
| [RESEARCH_INTERVIEWER_CHATGPT.md](RESEARCH_INTERVIEWER_CHATGPT.md) | **Operator runbook** (GitHub **+**, one repo, Zoom/Meet + mobile capture) + paste prompt below `---` |
| [RESEARCH_INTERVIEWER.md](RESEARCH_INTERVIEWER.md) | Canonical spec (edit here; keep ChatGPT file in sync) |
| [PI_MDC_BILLING_APPEAL_SESSION_1.md](PI_MDC_BILLING_APPEAL_SESSION_1.md) | PI/MDC billing appeals — Session 1; pre-loaded context, no question limit, selective `Captured:` lines |
| [custom-instructions-short.md](custom-instructions-short.md) | Short version for ChatGPT **Custom Instructions** |

## Inputs block

Fill in bracket fields in the prompt, or leave blank to infer:

| Field | Required | Default / inference |
|-------|----------|---------------------|
| Interview language | No | **English**; live interview in this language; internal artifacts in English |
| Repository | No | Connected repo; or `skip repository` |
| Company / engagement | **Yes** | From repo README, investigations, memory |
| Interviewee role | **Yes** | From interview guides / investigations |
| Research question | **Yes** | From investigations, guides, memory (ask if ambiguous) |
| Max questions | No | Default **10** when blank at inference or unspecified |
| Known context | No | From repo discovery, or `none` |

## Setup flow

- Infer from explicit inputs → repo → conversation (see full prompt).
- Complete **Pre-interview setup gate** (required variables, repository resolution, discovery, internal question plan).
- Do **not** say Ready until the gate is complete.
- **Ready.** Say `Start the interview process` to begin the live interview.

## Interview language

Live interview runs in the configured language (default English). Internal summaries and repo packs are always compiled in English.

## Follow-up access protocol

When answers reference internal systems, the interviewer confirms **how** follow-up detail (connectivity, access path, credential workflow) may be obtained—e.g. email follow-up—and captures consent in a `Captured:` line. No secrets on the call.

## Voice evidence capture (ChatGPT)

During the **live** interview (especially voice mode): **do not** speak or output `Captured:` lines—use a brief acknowledgment and the next question only. Maintain an **internal evidence log** silently.

After the interview, run internal summary; the assistant **emits** all `Captured:` lines then. Post-interview compilation uses those lines and the transcript when audio is not transcribed. Rough estimates are kept (not replaced with TBD).

## ChatGPT operator workflow

See **[RESEARCH_INTERVIEWER_CHATGPT.md](RESEARCH_INTERVIEWER_CHATGPT.md)** for the full runbook. Summary:

1. ChatGPT **+** → **GitHub** → dropdown: disconnect wrong repos, connect **exactly one** engagement repo.
2. Paste [RESEARCH_INTERVIEWER.md](RESEARCH_INTERVIEWER.md) (or the prompt section in the ChatGPT file); infer Inputs from the connected repo; clarify if needed; wait for **Ready**.
3. Run the human interview on **Zoom / Teams / Meet** with **separate capture** (meeting recording and/or **mobile ChatGPT voice** on a second device)—interviewee audio often does not persist in the desktop ChatGPT thread.
4. Desktop ChatGPT: `Start the interview process` → live Q&A → `Generate internal interview summary and repo memory pack`.
5. Merge ChatGPT summary with the **external transcript** → one report → commit to GitHub.

## Live end and compile

- **Live end:** “Thank you. The interview is complete. You may click End.”
- **Compile:** e.g. `Generate internal interview summary and repo memory pack`
- **Deliverable:** combine compile output with independent transcript; add to the connected repo

## PI/MDC Session 1

Pre-loaded engagement context (AMD, CIGNA MA, denial worklists). No SMART setup; on load say only *Say 'Start the interview process' when you want to begin.* Evidence capture is **selective** (skip vague answers). No question cap — end when the research question is answered.

## Share links (public repo)

```text
https://github.com/DeepSpringAI/prompts/blob/main/research-interviewer/RESEARCH_INTERVIEWER_CHATGPT.md
https://raw.githubusercontent.com/DeepSpringAI/prompts/main/research-interviewer/RESEARCH_INTERVIEWER_CHATGPT.md
https://github.com/DeepSpringAI/prompts/blob/main/research-interviewer/RESEARCH_INTERVIEWER.md
https://raw.githubusercontent.com/DeepSpringAI/prompts/main/research-interviewer/RESEARCH_INTERVIEWER.md
https://github.com/DeepSpringAI/prompts/blob/main/research-interviewer/PI_MDC_BILLING_APPEAL_SESSION_1.md
https://raw.githubusercontent.com/DeepSpringAI/prompts/main/research-interviewer/PI_MDC_BILLING_APPEAL_SESSION_1.md
```
