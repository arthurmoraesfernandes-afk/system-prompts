# LIVE default system prompt — Opus 4.8 (interactive, in-repo) delta + additive surfaces

Third data point in the live-prompt corpus. Companion to:
- `C:/Users/Victor/Desktop/live-core-2026-08-01.md` — Fable 5 baseline (session b8575d3f).
- `C:/Users/Victor/Desktop/live-core-2026-08-03-opus5-delta.md` — Opus 5 delta (session 80485131).
- `C:/Users/Victor/Desktop/live-l2-2026-08-01.md` — Fable 5 L2/orchestration tool descriptions.

Transcribed VERBATIM by MAIN (Opus 4.8) from its own live context, 2026-08-03, session e66eaf02.

Harness for THIS session: Claude Code **desktop app (win32), interactive** (user watching in real time),
cwd `C:\Users\Victor\claude\Global orchestration settings scoping` (**IS a git repo**), the orchestration
kit + `main-orchestrator` persona + full user/project CLAUDE.md injected, MCP + skills + vk-* roster loaded,
advisor tool present. Sections S1…S14 mirror the two prior core docs; **S15 is new** — material present in
this prompt and in NEITHER prior doc.

**Cell this fills.** Per the MAIN-tier ruling Fable is the intended sole MAIN, but this session *started* as
Opus 4.8 (S7 line is trustworthy at session start; no `/model` switch has staled it). So this is the
**Opus-4.8 × interactive × in-repo × kit-active** cell — not the Fable-MAIN cell the kit normally runs.

**Causal caveat.** n=1 per cell, same as the prior docs. Where a section differs I can say *that* it differs,
not always *why*. Candidate drivers: (a) model variant, (b) an interactive-vs-autonomous harness toggle,
(c) cwd/env conditionality, (d) config (persona + CLAUDE.md), (e) prompt-template drift. The S9 result reads
most like (b); S7 cutoff/model lines are (a); the gitStatus block is (c); the injected CLAUDE.md is (d).
Nothing here is confirmed drift.

**Provenance note (reconciled 2026-08-03).** The first pass derived the `08-01 Fable 5` column *second-hand* —
from the Opus 5 core doc's characterization of the Fable baseline — because the Fable **core** file had not
been read (this session was handed the Fable **L2** tool-doc by mistake). That column has since been verified
first-party against `live-core-2026-08-01.md`. Net effect: most rows confirmed; S1's mode-marker speculation
withdrawn; a new model-varying S3 bullet-3 delta found; the hard-to-reverse clause confirmed full in Fable and
Opus 4.8 (Opus 5 the lone outlier); ADD-1 and ADD-8 reclassified as non-additive (both already in the Fable
core); the S4 final-message rule now quoted verbatim. Rows touched by the reconciliation are flagged inline.

---

## Summary table (this session vs the two baselines)

| § | 08-01 Fable 5 | 08-03 Opus 5 | **This session (Opus 4.8)** | Likely driver |
|---|---|---|---|---|
| S1 Identity | present (incl. "interactive agent") | present | present (incl. "interactive agent") | boilerplate — NOT a mode marker |
| S2 Security paragraph | present | identical | identical | same |
| S3 Harness | 5 bullets (bullet 3 = "system turns" wording) | 5 bullets + orphaned sentence | 5 bullets, **bullet 3 = "system-reminder tags" wording**, + glued artifact | bullet 3 model-varies |
| S4 "Communicating with the user" | full (~7 para) | ABSENT (3 fragments survive) | **ABSENT — same 3 fragments** | Opus-correlated or template |
| — hard-to-reverse clause | full (first-party) | **truncated** | full — clause intact | Opus 5 is the lone outlier |
| S5 model-identity paragraph | Fable/Mythos para | ABSENT | **ABSENT** | Fable-only injection |
| S6 Session-specific guidance | 2 bullets | 2 bullets (not transcribed) | **2 bullets — transcribed in S15/ADD-1** | config |
| S7 Environment | cutoff Jan 2026, Fable 5 ids | cutoff May 2026, Opus 5 ids | **cutoff Jan 2026, Opus 4.8 ids, git repo** | model + cwd |
| S8 Scratchpad | present | identical | identical | same |
| **S9 Context mgmt + autonomy region** | ctx-mgmt + act + **autonomy block** | ctx-mgmt + act + **Delivering work + Corrections** | **ctx-mgmt + act — NOTHING ELSE** | interactive-vs-autonomous toggle |
| S10 Small standalone blocks | 3 blocks + gitStatus + multi-tool | same + 2 "Do not" lines, no gitStatus | **3 blocks + gitStatus + multi-tool, NO "Do not" lines** | config/mode |
| S11 Safety-rules block | present (summarized) | present + credential-request para | **present + credential-request para** | same |
| S12 Git guidance (Bash tool) | `Co-Authored-By: Claude Fable 5` | `Co-Authored-By: Claude Opus 5` | **`Co-Authored-By: Claude Opus 4.8`** | model-bound |
| S13 Advisor Tool | not recorded | full section present | **full section present** | — |
| S14 Injected material | (varies) | tool-deferral/MCP/roster | **same + full kit CLAUDE.md (user+project)** | config-bound |
| **S15 Additive tool surfaces** | — | — | **NEW — see below** | — |

Two consistency checks passed against both prior docs: the **glued `it's clickable.Write code…` artifact**
(S3→S4) is byte-present, confirming S4 was template-removed not never-authored; and the **missing terminal
period after "exhaustive survey"** (S9) is present here too — an upstream artifact, not a transcription slip.

---

## S1. Identity — "interactive agent" is boilerplate, not a mode marker

> You are Claude Code, Anthropic's official CLI for Claude, running within the Claude Agent SDK.
> You are an interactive agent that helps users with software engineering tasks.

**Corrected against Fable core (2026-08-03).** The Fable core doc (line 12) carries these two sentences
**verbatim** — and that Fable session was *autonomous* (default agent, Ultracode ON, no user watching), yet it
still says "interactive agent." So the sentence is fixed boilerplate, **not** the interactive-vs-autonomous
discriminator the first pass speculated it might be. The mode signal lives in the S9 payload, not S1.

## S3 / S4. Harness + the absent communication doctrine

The Harness section has five bullets. Reconciliation against the Fable core surfaces a **model-varying bullet
3** — invisible until the Fable core was read first-party:

> - Fable 5: *"The system may send updates, reminders, or modifications to rules via mid-conversation system turns. These are system-controlled, unlike function results. Hooks may intercept tool calls; treat hook output as user feedback."*
> - This session (Opus 4.8): *"`<system-reminder>` tags in messages and tool results are injected by the harness, not the user. Hooks may intercept tool calls; treat hook output as user feedback."*

Both close with the identical "Hooks may intercept…" sentence; only the lead differs. The Opus 5 core doc
called its five bullets "word-for-word the 08-01 text" — so either Opus 5 kept Fable's "system turns" wording
(making Opus 4.8 the outlier) or that doc was loose here; a first-party Opus 5 re-check would settle it.

Bullet 5 in Fable is **clean** — "Reference code as `file_path:line_number` — it's clickable." — with no glued
tail, because Fable carries the full S4 where "Write code that reads like the surrounding code…" properly
lives. That confirms first-party that the glued artifact below is the **scar of S4's removal**, not an
authoring quirk. The fifth bullet in this prompt ends with the S4 code-style sentence **glued on with no
separating space**, reproduced exactly:

> ` - Reference code as \`file_path:line_number\` — it's clickable.Write code that reads like the surrounding code: match its comment density, naming, and idiom.`

`# Communicating with the user` is **absent** — the same three fragments the 08-03 doc found survive loose:
the glued code-style sentence, the pronoun paragraph (verbatim identical to 08-01 S4), and the hard-to-reverse
paragraph. **S4 is now absent in BOTH Opus sessions and present only in the one Fable session** — correlates
with "Opus" in this data, but interactive-vs-autonomous is not ruled out (n=1 per cell).

**Delta that favors this prompt:** the hard-to-reverse paragraph is **complete**, including the clause
Opus 5 dropped:

> …Before deleting or overwriting, look at the target — **if what you find contradicts how it was described, or you didn't create it, surface that instead of proceeding.** Report outcomes faithfully…

First-party now: the clause is **full in Fable core (line 46) and full here (Opus 4.8)**, and truncated only in
the Opus 5 transcription — so Opus 5 is the lone outlier (a real Opus-5 template quirk, or a slip in that doc;
worth a re-check). Either way the kit cannot assume the live prompt carries the inspect-before-destroy
escalation uniformly — the persona should state it standalone.

## S5. Model-identity paragraph — ABSENT (as in Opus 5)

No Fable/Mythos-style identity paragraph. The only model self-description is the S7 Environment line. This is
the second Opus session with no such paragraph → supports the theory that the Fable/Mythos paragraph is a
**Fable-tier-specific injection**, not a universal slot.

## S7. Environment block — verbatim (non-secret lines)

```
# Environment
You have been invoked in the following environment:
 - Primary working directory: C:\Users\Victor\claude\Global orchestration settings scoping
 - Is a git repository: true
 - Platform: win32
 - Shell: PowerShell (primary); Bash tool also available for POSIX scripts — each takes its own syntax.
 - OS Version: Windows 10 Pro 10.0.19045
 - You are powered by the model named Opus 4.8. The exact model ID is claude-opus-4-8.
 - Assistant knowledge cutoff is January 2026.
 - The most recent Claude models are the Claude 5 family and Haiku 4.5. Model IDs — Fable 5: 'claude-fable-5', Opus 5: 'claude-opus-5', Sonnet 5: 'claude-sonnet-5', Haiku 4.5: 'claude-haiku-4-5-20251001'. When building AI applications, default to the latest and most capable Claude models.
 - Claude Code is available as a CLI in the terminal, desktop app (Mac/Windows), web app (claude.ai/code), and IDE extensions (VS Code, JetBrains).
 - Fast mode for Claude Code uses Claude Opus with faster output (it does not downgrade to a smaller model). It can be toggled with /fast and is available on Opus 5/4.8/4.7.
```

Deltas: **cutoff January 2026** (matches Fable 5; earlier than Opus 5's May 2026 — Opus 4.8 < Opus 5) and the
model-name/ID line (`Opus 4.8` / `claude-opus-4-8`). The recent-models list, CC-availability line, and
Fast-mode line are byte-identical to both prior docs — **including the `Shell: PowerShell (primary)` claim**
that Arthur's CLAUDE.md overrides to Git-Bash-primary. Note the Environment line itself now names the dual
shell surface: "**Bash tool also available**" (see S15/ADD-8).

## S9. Context management — a THIRD, barer payload for the autonomy slot

Identical opening to both prior docs:

```
# Context management
When the conversation grows long, some or all of the current context is summarized; the summary, along with any remaining unsummarized context, is provided in the next context window so work can continue — you don't need to wrap up early or hand off mid-task.

When you have enough information to act, act. Do not re-derive facts already established in the conversation, re-litigate a decision the user has already made, or narrate options you will not pursue. If you are weighing a choice, give a recommendation, not an exhaustive survey
```

Then it goes **straight to the markdown-link block**. The entire post-`act` payload is absent:

- No autonomy block ("You are operating autonomously. The user is not watching in real time…") — 08-01's fill.
- No `# Delivering work`, no `# Corrections` — 08-03's fill.

**This is the finding of the document.** The S9 region resolves to three different payloads across three sessions:

| Session | S9-region payload |
|---|---|
| 08-01 Fable 5 | ctx-mgmt + act + **autonomy block** (autonomous-mode text) |
| 08-03 Opus 5 | ctx-mgmt + act + **Delivering work + Corrections + two "Do not" lines** (collaborative + fan-out-suppression) |
| **This (Opus 4.8, interactive)** | ctx-mgmt + act + **nothing** (barest) |

08-03's provenance work anchored the `Do not call the AgentTool` / `Do not use workflows or deep-research`
lines "between `# Corrections` and the markdown-link block." This prompt has **no `# Corrections` block**, so
that anchor doesn't exist and **those two guardrail lines are absent** (confirmed in S10). Conclusion:
**Delivering work + Corrections + the AgentTool/workflow-suppression lines are one template payload**, and an
interactive session — where "the user is not watching in real time" would be *false* — gets a different, barer
fill. This is the strongest evidence yet that the S9-region driver is the **interactive-vs-autonomous toggle**,
not the model.

## S10. Small standalone blocks

Present, verbatim, in order: the markdown-file-link block, the ```bash fenced-command block, the
terminal-dialog-slash-commands block, `<browser_surfaces>`, and the
`If you intend to call multiple tools…` line. **Present:** the `gitStatus:` snapshot (cwd is a git repo).
**Absent:** the two `Do not call the AgentTool` / `Do not use workflows or deep-research` lines — see S9.

## S11. Safety-rules block — full, matches the 08-03 transcription

Same opening and subsections (Instruction source boundary · Action categories · Privacy · Copyright · worked
purchase example). The credential-request paragraph 08-03 recorded is present verbatim here too:

> If a dedicated credential-request tool is available, Claude may use it to ask the user's password manager to handle sign-in, payment, or address details… Claude never sees the actual values…

## S12. Git guidance (inside the Bash tool) — Opus 4.8 trailer

Byte-identical to both prior docs except the trailer: `Co-Authored-By: Claude Opus 4.8 <noreply@anthropic.com>`.
The conflict flagged in both prior docs **persists across all three variants**: "Commit or push only when the
user asks. If on the default branch, branch first." still contradicts Arthur's 2026-07-23 commit posture and
the persona's sole-committer doctrine, and is not neutralized by name in the prompt. **Confirmed stable prompt
text.** (There is also a PR-body trailer the prior docs didn't record — see S15/ADD-8.)

## S13. `# Advisor Tool` — present, matches 08-03

Full `# Advisor Tool` section present, plus the shorter duplicate inside the `advisor` tool's own description.
Same CLAUDE.md tension 08-03 noted: the section says "call at least once before committing to an approach and
once before declaring done"; CLAUDE.md says MAIN consults the advisor *sparingly*. CLAUDE.md wins; tension is
real and unnamed by the persona.

## S14. Injected material (config-dependent, listed not transcribed)

As 08-03's S14, plus — significantly — **the full user + project CLAUDE.md is injected** as a SessionStart
system-reminder (`claudeMd`), governing behavior and overriding several prompt tensions above. Also present:
tool-deferral roster, MCP server instructions (claude-context-monitor, claude-in-chrome, computer-use,
Windows-MCP), the vk-* agent-types roster, the skills catalogue, the memctl SessionStart/UserPromptSubmit
memory outlines, and `workflow size guideline is configured for this session: large` inside the Workflow tool.

---

## S15. ADDITIVE material — present in this prompt, in NEITHER prior core/L2 doc

Everything below is in my live context and was not transcribed by the 08-01, 08-03, or L2 docs. Verbatim
excerpts are quoted; larger tool descriptions are summarized with kit-relevant excerpts and flagged
"present, not fully transcribed."

### ADD-1. `# Session-specific guidance` — RECLASSIFIED (not additive; = Fable core S6)

**Correction (2026-08-03):** listed as additive in the first pass only because the Opus 5 doc didn't transcribe
it. First-party against the Fable core shows these two bullets are **identical to Fable S6 (lines 55–56)** —
shared, not unique to this session. Retained for the kit-relevant extract:

> ` - When the user types \`/<skill-name>\`, invoke it via Skill. Only use skills listed in the user-invocable skills section — don't guess.`
> ` - If the user asks about "ultrareview" or how to run it, explain that /code-review ultra launches a multi-agent cloud review of the current branch (or /code-review ultra <PR#> for a GitHub PR); /ultrareview is a deprecated alias for the same command. It is user-triggered and billed; you cannot launch it yourself, so do not attempt to via Bash or otherwise. It needs a git repository (offer to "git init" if not in one); the no-arg form bundles the local branch and does not need a GitHub remote.`

**Kit relevance (still valid):** documents `/code-review ultra` (aka the deprecated `/ultrareview`) as a
**billed, user-triggered cloud multi-agent review that MAIN CANNOT self-launch** — a hard boundary for the
kit's review doctrine. First-party-confirmed present in both Fable and Opus 4.8 (same kit config).

### ADD-2. `AskUserQuestion` tool — native decision-fork elicitation + plan-mode interplay

Not described in either doc. Structured multiple-choice questions (1–4 questions, 2–4 options each,
`multiSelect`, an automatic "Other"). Key verbatim guidance:

> Plan mode note: To switch into plan mode, use EnterPlanMode (not this tool). Once in plan mode, use this tool to clarify requirements or choose between approaches BEFORE finalizing your plan. Do NOT use this tool to ask "Is my plan ready?", "Should I proceed?", or otherwise reference "the plan" in questions — the user cannot see the plan until you call ExitPlanMode for approval.

> Reserve this for decisions where the user's answer changes what you do next — not for choices with a conventional default or facts you can verify in the codebase yourself.

**Kit relevance:** this is the **native surface for surfacing an owner decision-fork** (the kit currently does
this in freeform chat). It also reveals `EnterPlanMode` / `ExitPlanMode` (plan-mode lifecycle) — deferred
tools neither prior doc named.

### ADD-3. `mcp__ccd_session__*` — native session/task primitives (NONE in either doc)

Four tools, all additive:

- **`spawn_task`** — "Flag an out-of-scope issue for a separate background task… dead code, stale docs, missing
  coverage, a confirmed TODO, or a security issue spotted in passing. Don't flag vague code-smell observations,
  trivial fixes you can do inline, or low-confidence hunches. A chip appears for the user; one click spins it
  off into its own session. Your current turn continues uninterrupted." Returns a `task_id`.
- **`dismiss_task`** — withdraw a chip the user hasn't acted on.
- **`mark_chapter`** — "Mark the start of a new chapter in this session… The user sees a divider in the
  transcript and a floating table of contents… A typical session has 3–8 chapters."
- **`read_widget_context`** — read the current state of an embedded interactive widget.

**Kit relevance (high):** `spawn_task` is a **native out-of-scope-work spawning surface** that parallels the
kit's `BACKLOG.md` mechanism and the `mcp__ccd_session__spawn_task` chip is genuinely a "defer to a new
session" primitive distinct from dispatching a vk-* seat. `mark_chapter` is a native session-structuring aid
the kit could adopt for long orchestration sessions. Worth an explicit kit decision: adopt, ignore, or wrap.

### ADD-4. `ReportFindings` — native code-review findings schema (not in either doc)

> Report code-review findings as a typed list so the host UI can render them. Use this only when the active
> code-review instructions tell you to report findings with this tool… call it once with the verified findings
> ranked most-severe first (empty array if nothing survived verification)…

Each finding carries: `file`, `line`, `summary`, `failure_scenario` (concrete inputs/state → wrong
output/crash), `category` (kebab-case slug), `short_summary` (≤60 chars), `verdict` (`CONFIRMED` | `PLAUSIBLE`),
and `outcome` (`fixed` | `skipped` | `no_change_needed`, set only when re-reporting after fixes). Top-level
`level` (`low`…`max`) records the effort the review ran at.

**Kit relevance (high):** this is the **native shape for review output** — directly comparable to what
`vk-reviewer` / `vk-judge` emit and to the kit's review-rung reporting. The `CONFIRMED`/`PLAUSIBLE` verdict +
`failure_scenario` requirement mirror the kit's adversarial-verify doctrine; aligning vk-* review schemas to
this shape would make findings host-renderable.

### ADD-5. `SendUserFile` — deliverable-surfacing tool (not in either doc)

> Send files to the user. Use this when the file *is* the deliverable — a generated diagram, a report, a
> screenshot, a built artifact… `status`: `proactive` when you're initiating (user away), `normal` when
> replying. `display`: `render` (inline side panel) vs `attach` (download card only).

**Kit relevance:** the sanctioned way to surface an artifact deliverable, consistent with CLAUDE.md's "never
paste into chat an artifact that already exists on disk." The kit's MAIN-output-economy rule and this tool are
complementary — point at the file via `SendUserFile`, don't inline it.

### ADD-6. `Artifact` — publish HTML/Markdown to claude.ai (not in either doc)

Renders a file to a default-private, shareable web page; supports `action:"list"` to enumerate prior
artifacts, in-place update by URL, runtime `capabilities`, a required emoji `favicon`, strict same-host CSP
(everything inlined), theme-awareness. Carries its own safety block:

> **Never publish**: pages that impersonate a real person or organization… fabricated records, receipts, or
> reviews presented as genuine; forms or flows that collect credentials or payment details under false
> pretenses; or content targeting a private individual.

**Kit relevance (low–moderate):** a publish/deliverable surface with an impersonation/fabrication guardrail;
mostly relevant if the kit ever produces shareable dashboards. Present, not fully transcribed.

### ADD-7. `mcp__visualize__show_widget` / `read_me` — inline SVG/HTML visualizations (not in either doc)

Renders SVG or HTML widgets inline in the chat response (diagrams, charts, mockups, dashboards). `read_me`
must be called once before the first `show_widget`. **Kit relevance (low):** a rendering surface; present,
not fully transcribed.

### ADD-8. Dual-shell tooling + PR trailer — RECLASSIFIED (mostly in Fable core, not additive)

**Correction (2026-08-03):** the first pass called the dual-shell surface and PR-body trailer additive. The
Fable core doc actually records **both** — the dual-shell line "Bash tool also available for POSIX scripts"
(Fable S7, line 66) and the PR-body trailer "🤖 Generated with [Claude Code]" plus the `gh`-CLI /
interactive-flags Git section (Fable S12, lines 138–144). So this is **not additive**. What remains genuinely
un-transcribed is only the *full PowerShell-7 tool description block* (encoding, `2>$null`, no inline
`VAR=x cmd`, here-string rules, native-exe call operator) — low kit value.

**Kit relevance (still valid, downgraded):** the point stands that a **dedicated Git-Bash tool exists as a
peer** to PowerShell despite the "PowerShell (primary)" Environment line — so the kit's bash-first doctrine is
supported by the tool inventory, not fighting it. But this was already visible in the Fable core; it is not a
new finding.

### ADD-9. Native orchestration primitives sitting in the deferred-tool roster (not in either core doc)

The L2 doc covered Workflow, Agent, ScheduleWakeup, Skill, ToolSearch. My deferred-tool roster additionally
surfaces these **orchestration-relevant native tools** (schemas load on demand via ToolSearch):

- **`EnterWorktree` / `ExitWorktree`** — a **native worktree lane**, distinct from `vk-wright`'s
  `isolation:"worktree"`. The kit should decide whether MAIN ever uses this directly vs always via the writer seat.
- **`Monitor`** — wait-on-a-condition (the tool ScheduleWakeup's description tells you to use instead of
  foreground `sleep`).
- **`TaskCreate` / `TaskGet` / `TaskList` / `TaskOutput` / `TaskStop` / `TaskUpdate`** — the **native task
  ledger** (the "task tools" the periodic session reminder nudges toward). Parallel to the kit's own tracking.
- **`SendMessage`** — continue a previously spawned agent by id/name with its context intact (the L2 W2 doc
  flagged this as a first-class continuation pattern; it's a real deferred tool here).
- **`CronCreate` / `CronDelete` / `CronList`** — native cron/scheduled cloud agents (the `/schedule` skill's
  backing; note the `<<autonomous-loop>>` vs ScheduleWakeup's `<<autonomous-loop-dynamic>>` sentinel split).
- **`PushNotification`**, **`RemoteTrigger`**, **`EnterPlanMode` / `ExitPlanMode`**, **`DesignSync`**,
  **`NotebookEdit`**, **`WebFetch` / `WebSearch`**, MCP-resource readers.

**Kit relevance (high):** several of these (`EnterWorktree`, `Monitor`, `Task*`, `SendMessage`, `Cron*`) are
native equivalents of mechanisms the kit implements in doctrine. A dedicated audit — "native primitive vs kit
mechanism, adopt/wrap/ignore per each" — is warranted; they were invisible in the prior two docs.

### ADD-10. In-app Browser tool suite (`mcp__Claude_Browser__*`) — not in either doc

The `<browser_surfaces>` block (S10) names the in-app Browser, but the full tool suite is additive:
`navigate`, `computer` (click/type/screenshot), `read_page` (a11y tree with `ref_N` handles), `find`,
`form_input`, `get_page_text`, `javascript_tool` (debug/inspect only — "Do NOT use this to implement UI
changes"), `preview_start`/`preview_stop`/`preview_list`/`preview_logs` (dev-server lane via
`.claude/launch.json`), console/network readers, tab management. **Kit relevance (low):** a browsing/preview
surface; present, not fully transcribed.

---

## Actionable takeaways for the kit (updated with the additive findings)

1. **The S9 slot has three payloads; interactive MAIN gets the barest.** Design the kit assuming MAIN
   (interactive) receives *no* autonomy text, *no* Delivering/Corrections, and **no AgentTool/workflow
   suppression lines** — while background/default-agent seats likely DO receive the suppression payload. The
   persona's neutralization of `Do not call the AgentTool` is belt-and-suspenders for interactive MAIN but
   still required for any background MAIN. (Confirms and sharpens the 08-03 S10 flag.)
2. **Inspect-before-destroy is not model-monotonic.** Intact in Opus 4.8, truncated in Opus 5. The persona
   must carry the clause standalone rather than relying on the live prompt. (Confirms 08-03 takeaway.)
3. **S4 communication doctrine absent in both Opus sessions — now quotable first-party.** The Fable core
   carries it in full (S4, lines 29–46). The load-bearing rule to port into the persona, verbatim from Fable:
   *"Everything the user needs from this turn — answers, summaries, findings, conclusions, deliverables — must
   be in the final text message of your turn, with no tool calls after it."* Plus "Lead with the outcome" and
   "readable > concise." CLAUDE.md covers lead-with-verdict and terseness but **not** the final-message rule —
   losing it silently degrades every fan-out synthesis. (Confirms 08-03 takeaway #2.)
4. **Git-commit conflict confirmed across all three variants** — stable prompt text; neutralize by name.
   Track the additive PR-body trailer (ADD-8) alongside it.
5. **Methodology constraint.** Only a cell's occupant can transcribe its own prompt; a dispatched vk-* seat
   sees a *different* prompt. The live-prompt corpus needs one capture per (model × mode) cell, authored by
   MAIN in that cell — this observation cannot be fanned out. (This doc was written MAIN-direct for exactly
   that reason.)
6. **NEW — native primitives to adjudicate (ADD-3, ADD-4, ADD-9).** `spawn_task`/`mark_chapter`,
   `ReportFindings`, and the deferred `EnterWorktree`/`Monitor`/`Task*`/`SendMessage`/`Cron*` tools are native
   equivalents of kit mechanisms, invisible in the prior docs. Run an "adopt / wrap / ignore" pass:
   - align `vk-reviewer`/`vk-judge` output to the `ReportFindings` schema (host-renderable, CONFIRMED/PLAUSIBLE
     + failure_scenario already match kit doctrine);
   - decide whether MAIN uses native `EnterWorktree`/`Task*` directly or keeps everything in kit doctrine;
   - note `spawn_task` as a native BACKLOG-adjacent "defer to new session" surface.
7. **NEW — `/code-review ultra` boundary (ADD-1).** The prompt states MAIN cannot self-launch the billed cloud
   review; the kit's review doctrine should reference it as a user-triggered escalation, not a dispatchable seat.
8. **Dual-shell tooling supports bash-first (ADD-8) — not new, but confirmed.** A dedicated Git-Bash tool
   exists as a peer to PowerShell despite the "PowerShell (primary)" Environment line; the kit's bash-first
   doctrine is backed by the tool inventory. (Already present in the Fable core — reclassified from "NEW.")
9. **Reconciliation record (2026-08-03).** This doc's Fable column was upgraded from second-hand (via the
   Opus 5 doc) to first-party against `live-core-2026-08-01.md`. Net changes: S3 gained a model-varying
   bullet-3 finding; the hard-to-reverse clause is confirmed full in both Fable and Opus 4.8 (Opus 5 the lone
   outlier); ADD-1 and ADD-8 were reclassified as non-additive (both present in the Fable core); S1's
   "interactive agent" mode-marker speculation was withdrawn (Fable's autonomous session carries the same
   sentence). A fourth cell — `live-core-2026-08-03-sonnet5-delta.md` — exists on disk and is not yet folded in.
