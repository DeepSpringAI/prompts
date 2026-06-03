# Research Interviewer

Generic research interviewer with **SMART SETUP** and **Captured:** evidence lines during voice interviews so post-interview compilation still has interviewee facts when audio is not transcribed.

| File | Use |
|------|-----|
| [RESEARCH_INTERVIEWER.md](RESEARCH_INTERVIEWER.md) | Full prompt — fill the **Inputs** block or leave fields blank for inference |
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
- Ask only for unresolved **required** fields (or pick among listed research question candidates).
- Compile setup (with inference confidence).
- Repository discovery and pre-interview planning.
- **Ready.** Say `Start the interview process` to begin the live interview.

## Interview language

Live interview runs in the configured language (default English). Internal summaries and repo packs are always compiled in English.

## Follow-up access protocol

When answers reference internal systems, the interviewer confirms **how** follow-up detail (connectivity, access path, credential workflow) may be obtained—e.g. email follow-up—and captures consent in a `Captured:` line. No secrets on the call.

## Voice evidence capture

After each answer, the assistant restates facts as:

`Captured: <statement>. Status: interviewee-stated / unverified.`

Post-interview compilation must use these lines when the transcript shows `[Audio response not available as text]`. Rough estimates are kept (not replaced with TBD).

## Live end and compile

- **Live end:** “Thank you. The interview is complete. You may click End.”
- **Compile:** e.g. `Generate internal interview summary and repo memory pack using the captured evidence lines`

## PI/MDC Session 1

Pre-loaded engagement context (AMD, CIGNA MA, denial worklists). No SMART setup; on load say only *Say 'Start the interview process' when you want to begin.* Evidence capture is **selective** (skip vague answers). No question cap — end when the research question is answered.

## Share links (public repo)

```text
https://github.com/DeepSpringAI/prompts/blob/main/research-interviewer/RESEARCH_INTERVIEWER.md
https://raw.githubusercontent.com/DeepSpringAI/prompts/main/research-interviewer/RESEARCH_INTERVIEWER.md
https://github.com/DeepSpringAI/prompts/blob/main/research-interviewer/PI_MDC_BILLING_APPEAL_SESSION_1.md
https://raw.githubusercontent.com/DeepSpringAI/prompts/main/research-interviewer/PI_MDC_BILLING_APPEAL_SESSION_1.md
```
