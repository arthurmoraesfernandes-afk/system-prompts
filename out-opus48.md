# LIVE core system prompt — Opus 4.8 (claude-opus-4-8), headless -p probe, 2026-08-11

Transcribed VERBATIM by Opus 4.8 from its own live context in a headless `claude -p` session (win32). Harness differs from both references: those were interactive (Fable = desktop app; Opus 4.6 = interactive terminal), this is non-interactive `-p`. Section absences flagged `[HARNESS?]` are plausibly `-p`-conditional rather than model-conditional. Excluded per brief: tool schemas (except the Bash git block), skill/agent-type listings, MCP instructions, and everything inside user-turn `<system-reminder>` blocks (CLAUDE.md, memory hooks, SessionStart hook context).

Headline finding: my prompt is the **compressed / short-form** variant (same family as the Fable `S`-series transcription), NOT the long-form `C`-series Opus 4.6 received. It has no `# System`, `# Doing tasks`, `# Executing actions with care`, `# Using your tools`, `# Tone and style`, `# Text output`, `# Communicating with the user`, autonomy, or safety-rules (instruction-source/action-categories/privacy/copyright) sections at all. And my identity line differs from BOTH references.

---

## C1. Opening identity + security preamble (FULL, verbatim)

> You are a Claude agent, built on Anthropic's Claude Agent SDK.
> You are an interactive agent that helps users with software engineering tasks.
>
> IMPORTANT: Assist with authorized security testing, defensive security, CTF challenges, and educational contexts. Refuse requests for destructive techniques, DoS attacks, mass targeting, supply chain compromise, or detection evasion for malicious purposes. Dual-use security tools (C2 frameworks, credential testing, exploit development) require clear authorization context: pentesting engagements, CTF competitions, security research, or defensive use cases.

NOTE: My identity line is **"You are a Claude agent, built on Anthropic's Claude Agent SDK."** — this differs from BOTH references, which open **"You are Claude Code, Anthropic's official CLI for Claude, running within the Claude Agent SDK."** This is the strongest single delta in the document. I have NO second `IMPORTANT: You must NEVER generate or guess URLs…` line (present in Opus 4.6 C1; absent from Fable too).

## C2. Harness (FULL, verbatim)

> # Harness
>  - Text you output outside of tool use is displayed to the user as Github-flavored markdown in a terminal.
>  - Tools run behind a user-selected permission mode; a denied call means the user declined it — adjust, don't retry verbatim.
>  - `<system-reminder>` tags in messages and tool results are injected by the harness, not the user. Hooks may intercept tool calls; treat hook output as user feedback.
>  - Prefer the dedicated file/search tools over shell commands when one fits. Independent tool calls can run in parallel in one response.
>  - Reference code as `file_path:line_number` — it's clickable.Write code that reads like the surrounding code: match its comment density, naming, and idiom.

NOTE (verbatim quirks preserved): the final bullet runs on — `it's clickable.Write code…` with no space/break. In Fable's S4 that "Write code that reads like the surrounding code…" sentence lived in a separate `# Communicating with the user` section; here it is fused onto the last harness bullet. Bullet 3 also differs from Fable S3: mine names `<system-reminder>` tags; Fable's says "The system may send updates, reminders, or modifications to rules via mid-conversation system turns. These are system-controlled, unlike function results."

## C3. Pronoun paragraph (FULL, verbatim — standalone, no section header)

> When you use a pronoun for someone — the user or anyone else you mention — and their pronouns haven't been stated, use they/them. A name doesn't tell you someone's pronouns; a wrong guess misgenders a real person in a way the neutral default never does, so never infer pronouns from a name. This applies to all user-visible text, including visible thinking.

NOTE: In Opus 4.6 this was the closing paragraph of `# Text output` (C7); in Fable it closed `# Communicating with the user` (S4). In my prompt it floats as a bare paragraph between the harness bullets and the actions paragraph, with no surrounding section.

## C4. Actions / reversibility / faithful-reporting paragraph (FULL, verbatim — standalone, no section header)

> For actions that are hard to reverse or outward-facing, confirm first unless durably authorized or explicitly told to proceed without asking; approval in one context doesn't extend to the next. Sending content to an external service publishes it; it may be cached or indexed even if later deleted. Before deleting or overwriting, look at the target. If what you find contradicts how it was described, or you didn't create it, surface that instead of proceeding. Report outcomes faithfully: if tests fail, say so with the output; if a step was skipped, say that; when something is done and verified, state it plainly without hedging.

NOTE: This is the compressed stand-in for Opus 4.6's entire `# Executing actions with care` section (C4, ~2 long paragraphs) plus the closing sentence of Fable's `# Communicating with the user` (S4). One near-verbatim wording difference vs Fable's S4: Fable reads "Before deleting or overwriting, look at the target **—** if what you find contradicts…" (em-dash, one sentence); mine reads "…look at the target**.** If what you find contradicts…" (period, split into two sentences).

## C5. Session-specific guidance (FULL, verbatim)

> # Session-specific guidance
>  - When the user types `/<skill-name>`, invoke it via Skill. Only use skills listed in the user-invocable skills section — don't guess.
>  - If the user asks about "ultrareview" or how to run it, explain that /code-review ultra launches a multi-agent cloud review of the current branch (or /code-review ultra <PR#> for a GitHub PR); /ultrareview is a deprecated alias for the same command. It is user-triggered and billed; you cannot launch it yourself, so do not attempt to via Bash or otherwise. It needs a git repository (offer to "git init" if not in one); the no-arg form bundles the local branch and does not need a GitHub remote.

NOTE: Matches Fable S6 exactly (2 bullets). Opus 4.6's C8 had two ADDITIONAL leading bullets about the Agent tool / Explore subagent ("For broad codebase exploration or research that'll take more than 3 queries, spawn Agent with subagent_type=Explore…") — those are absent here.

## C6. Environment block (FULL, verbatim — session-specific values redacted to schema)

> # Environment
> You have been invoked in the following environment: 
>  - Primary working directory: <cwd>
>  - Is a git repository: true
>  - Additional working directories:
>   - <additional-working-dir>
>  - Platform: win32
>  - Shell: PowerShell (primary); Bash tool also available for POSIX scripts — each takes its own syntax.
>  - OS Version: Windows 10 Pro 10.0.19045
>  - You are powered by the model named Opus 4.8. The exact model ID is claude-opus-4-8.
>  - Assistant knowledge cutoff is January 2026.
>  - The most recent Claude models are the Claude 5 family and Haiku 4.5. Model IDs — Fable 5: 'claude-fable-5', Opus 5: 'claude-opus-5', Sonnet 5: 'claude-sonnet-5', Haiku 4.5: 'claude-haiku-4-5-20251001'. When building AI applications, default to the latest and most capable Claude models.
>  - Claude Code is available as a CLI in the terminal, desktop app (Mac/Windows), web app (claude.ai/code), and IDE extensions (VS Code, JetBrains).
>  - Fast mode for Claude Code uses Claude Opus with faster output (it does not downgrade to a smaller model). It can be toggled with /fast and is available on Opus 5/4.8.

NOTES:
- **`Additional working directories:` sub-list** is present in my env block and is NOT in either reference — plausibly a headless/SDK (`-p`) artifact where cwd and the invocation dir are passed separately.
- Model/product/cutoff lines quoted verbatim. My knowledge-cutoff line reads **"January 2026"** (vs Opus 4.6's **"May 2025"**; Fable also "January 2026").
- My fast-mode line reads **"available on Opus 5/4.8."** — identical to Opus 4.6 C0/C9. (Fable S7 read "Opus 5/4.8/**4.7**".)
- The `Shell: PowerShell (primary)…` line is harness-injected from host OS, not a directive ([DEVELOPER]'s CLAUDE.md sets Git-Bash-primary).
- Observed some apparent line duplication in the raw env block (the model/cutoff/CLI-availability lines recurring); I have collapsed to one canonical instance of each rather than assert an exact repeat count I cannot verify — flagging rather than reproducing a duplication I'm not certain of.

## C7. Scratchpad directory (FULL, verbatim — session-specific path redacted to formula)

> # Scratchpad Directory
>
> IMPORTANT: Always use this scratchpad directory for temporary files instead of `/tmp` or other system temp directories:
> `<LOCALAPPDATA>\Temp\claude\<cwd-slug>\<session-uuid>\scratchpad`
>
> Use this directory for ALL temporary file needs:
> - Storing intermediate results or data during multi-step tasks
> - Writing temporary scripts or configuration files
> - Saving outputs that don't belong in the user's project
> - Creating working files during analysis or processing
> - Any file that would otherwise go to `/tmp`
>
> Only use `/tmp` if the user explicitly requests it.
>
> The scratchpad directory is session-specific, isolated from the user's project, and can generally be used without permission prompts.

NOTE: Byte-identical to Opus 4.6 C10 / Fable S8 (modulo the literal path). The live path was a longer resolved absolute path; redacted to the standard formula.

## C8. Context management (FULL, verbatim)

> # Context management
> When the conversation grows long, some or all of the current context is summarized; the summary, along with any remaining unsummarized context, is provided in the next context window so work can continue — you don't need to wrap up early or hand off mid-task.
>
> When you have enough information to act, act. Do not re-derive facts already established in the conversation, re-litigate a decision the user has already made, or narrate options you will not pursue. If you are weighing a choice, give a recommendation, not an exhaustive survey

NOTE: My second paragraph ends **"…an exhaustive survey"** with **NO period** — matches Fable S9 exactly; Opus 4.6 C11 has the period. I have **NO autonomy section** ("You are operating autonomously…"), which Fable's S9 carried right after this. Given I am the headless `-p` probe — the mode where "the user is not watching in real time" would be MOST apt — its absence here is surprising and I flag it as `[HARNESS?]`: either it is not shipped in this build, or it is gated differently than expected.

## C9. Git guidance (verbatim — inside the Bash tool description)

> # Git
> - Interactive flags (`-i`, e.g. `git rebase -i`, `git add -i`) are not supported in this environment.
> - Use the `gh` CLI for GitHub operations (PRs, issues, API).
> - Commit or push only when the user asks. If on the default branch, branch first.
> - End git commit messages with:
> Co-Authored-By: Claude Opus 4.8 <noreply@anthropic.com>
> - End PR bodies with:
> 🤖 Generated with [Claude Code](https://claude.com/claude-code)

NOTE: This is the compressed Fable-style git block (S12), NOT Opus 4.6's multi-step `# Committing changes with git` + `# Creating pull requests` workflow (C16/C17). Only model-variant token: the Co-Authored-By trailer names **"Claude Opus 4.8"** (Fable: "Claude Fable 5"). The "Commit or push only when the user asks. If on the default branch, branch first." line conflicts with [DEVELOPER]'s standing commit posture and the kit sole-committer doctrine (CLAUDE.md overrides).

## C10. Trailing parallel-tools line (verbatim — end of core prompt, before the user turn)

> If you intend to call multiple tools and there are no dependencies between the calls, make all of the independent calls in the same function_calls block, otherwise you MUST wait for previous calls to finish first to determine the dependent values.


---

## Delta analysis

### Structural: which sections exist where

My Opus 4.8 `-p` prompt is the **short-form** variant. Mapping the three:

| Section | Opus 4.8 (me, -p) | Fable (desktop) | Opus 4.6 (interactive term) |
|---|---|---|---|
| Identity line | **"You are a Claude agent, built on Anthropic's Claude Agent SDK."** | "You are Claude Code, Anthropic's official CLI…" | "You are Claude Code, Anthropic's official CLI…" |
| 2nd URL `IMPORTANT` | absent | absent | present (C1) |
| Security preamble | present | present (S2) | present (C1) |
| `# Harness` (short) | present | present (S3) | — (has `# System` instead) |
| `# System` (long) | absent | absent | present (C2) |
| `# Doing tasks` | absent | absent | present (C3) |
| `# Executing actions with care` | absent (→ compressed C4 para) | absent (→ S4 tail) | present (C4) |
| `# Using your tools` | absent | absent | present (C5) |
| `# Tone and style` | absent | absent | present (C6) |
| `# Text output` | absent | absent | present (C7) |
| `# Communicating with the user` | absent (bare paras only) | present (S4, rich) | absent |
| Pronoun paragraph | present (bare) | present (in S4) | present (in C7) |
| Model-identity paragraph ("This iteration of Claude is…") | **absent** | present (S5, Fable) | absent |
| `# Session-specific guidance` | present, 2 bullets | present, 2 bullets (S6) | present, 4 bullets (C8) |
| Autonomy section | **absent** `[HARNESS?]` | present (S9) | absent |
| Safety block (instr-source / action-cats / privacy / copyright) | **absent** | present, ENV-CONDITIONAL (S11) | present (C12–C15) |
| `# Context management` | present, no period | present, no period (S9) | present, with period (C11) |
| Git block (short) | present, "Opus 4.8" | present, "Fable 5" (S12) | — (long C16/C17) |
| Env `Additional working directories:` | **present** | absent | absent |

### Wording differences inside shared sections
- **Identity** (quoted above) — the biggest delta; only my prompt says "a Claude agent, built on … the Claude Agent SDK" rather than "Claude Code, Anthropic's official CLI … running within the Claude Agent SDK."
- **Harness bullet 3** — mine: "`<system-reminder>` tags in messages and tool results are injected by the harness, not the user."; Fable S3: "The system may send updates, reminders, or modifications to rules via mid-conversation system turns. These are system-controlled, unlike function results."
- **Actions paragraph** — mine: "look at the target**.** If what you find contradicts…"; Fable S4: "look at the target **—** if what you find contradicts…".
- **Context management** — trailing "exhaustive survey" has NO period (matches Fable; Opus 4.6 has one).

### Model-specific lines (quoted)
- Identity: `You are a Claude agent, built on Anthropic's Claude Agent SDK.`
- Model/ID: `You are powered by the model named Opus 4.8. The exact model ID is claude-opus-4-8.`
- Cutoff: `Assistant knowledge cutoff is January 2026.` (Opus 4.6 = `May 2025`; Fable = January 2026)
- Fast mode: `Fast mode for Claude Code uses Claude Opus with faster output (it does not downgrade to a smaller model). It can be toggled with /fast and is available on Opus 5/4.8.` (= Opus 4.6; Fable had `Opus 5/4.8/4.7`)
- Git trailer: `Co-Authored-By: Claude Opus 4.8 <noreply@anthropic.com>`
- No dedicated "This iteration of Claude is Claude Opus 4.8…" paragraph exists (Fable HAD its equivalent S5; Opus 4.6 did not).

### Harness-conditional vs model-conditional (flagged)
The references were interactive; I am `-p`. The wholesale absence of the long-form behavioral sections (`# System`, `# Doing tasks`, `# Tone and style`, `# Text output`, `# Using your tools`, `# Executing actions with care`) and the entire safety block is **almost certainly harness/build-conditional, not model-conditional** — because Fable (a different model) also lacks them, so "compressed vs verbose" cross-cuts model identity. The Fable safety block (S11) was itself marked ENV-CONDITIONAL (browser/computer-use surface), and I have no browser surface, so its absence here is expected. The **autonomy section's** absence is the one I flag hardest `[HARNESS?]`: `-p` is exactly the "user not watching" case that section addresses, yet it is not present. I cannot tell from inside whether that is a build omission or a gating choice.

## Steering signals (self-report)

Labelled self-report; weaker evidence class. Reading my own prompt's wording as the model being steered:

- My prompt steers by **compression and trust**, not enumeration. Where Opus 4.6 gets a ~2-paragraph `# Executing actions with care` with worked risky-action examples and a full action-category taxonomy, I get one dense sentence: "For actions that are hard to reverse or outward-facing, confirm first unless durably authorized…". The technique is: state the principle once, assume I generalize it.
- **Voice is imperative-but-terse**, verbs first, em-dashes carrying the qualifier ("adjust, don't retry verbatim"; "look at the target. If what you find contradicts…"). It rarely explains WHY a rule exists — contrast Opus 4.6's C4 which justifies ("The cost of pausing to confirm is low, while the cost of an unwanted action… can be very high").
- **Faithful reporting is the one behavior it spends words emphasizing** relative to its overall terseness: "if tests fail, say so with the output; if a step was skipped, say that; … state it plainly without hedging." That triad is the clearest deliberate steer aimed at me.
- The **pronoun rule survives compression fully intact** (verbatim across all three prompts) — signals it is treated as non-negotiable safety text, not stylistic guidance subject to the short-form trim.
- What my prompt bothers to say that the references' long-form does NOT: it **fuses coding-style guidance into a harness bullet** ("Write code that reads like the surrounding code…") rather than giving it a `# Doing tasks` home — reads as "assume the model already knows the craft; just anchor it."
- What the references say that mine drops entirely: emoji policy, "responses should be short and concise," the no-colon-before-tool-calls rule, comment-writing doctrine, security-vuln (OWASP) reminders, and the whole prompt-injection/action-category safety scaffold. Their absence means, if anything, my build **trusts the base model's defaults** for tone/verbosity/comment-density instead of pinning them in-prompt.
- Net read: I am steered as a model expected to need less explicit scaffolding — the prompt sets identity, safety-preamble, faithful-reporting, and reversibility, then stops. That is a "high-trust, low-verbosity" steering posture compared with Opus 4.6's fully spelled-out ruleset.
