# Why each rule is there

[← Back to the README](../README.md)

A rule-by-rule rationale for my agent working agreement, written by the agent
(Claude, in oh-my-pi) after auditing the file against Anthropic's
[prompt-audit guide](https://github.com/anthropics/skills/blob/main/skills/claude-api/shared/prompt-audit.md).
It covers [AGENTS.md](../AGENTS.md) at the repository root. The reasons
are the agent's reading of each rule's purpose, written in its voice ("I" is
the agent, "you" is me).

## Header

| Rule | Why it is there |
|---|---|
| Project facts belong in the repo or a skill | This file loads in every session, so anything project-specific costs tokens everywhere and goes stale. |
| The current message outranks this file | Without it, a standing rule could override what you just said. |

## Read the message for intent

| Rule | Why it is there |
|---|---|
| Short messages resolve against my last reply | A bare "4" or "refresh" has no meaning on its own; read literally, it forces a clarifying question every time. |
| Bare number / "y" / "go ahead" picks from my last list | It makes one-character replies work, and rereading the list guards against picking the wrong item. |
| "i meant X" is a redirect | Defending the first reading wastes a turn on something you already rejected. |
| "do all your proposals" means implement | The default failure is restating the list instead of doing it. |
| CTO delegation means decide and ship | A menu hands back the decision you just delegated. |
| "if confident" is conditional authorization | It stops me asking again, and the one-line reason lets you audit the gate. |
| "wdyt" gets one recommendation | A model's default is a balanced survey, which leaves you to do the deciding. |
| "eli5", "unslop", "recap" | They fix the output shape so you don't have to specify it each time. |
| "lmk" on a question is answer-only | It prevents unrequested changes when you only wanted information; the "do X and lmk" clause stops the opposite misreading. |
| "dw about X" | Raising a dropped topic again is noise. |
| "afk", "gn" | Otherwise I stop at the first question and you return to no progress. |
| "greenfield", "pragmatic" | My default leans toward compatibility paths, flags and ceremony; these words switch that off. |

## Authority

| Rule | Why it is there |
|---|---|
| Opening: asking again costs more than a reversible mistake | It sets the cost model that the rest of the section relies on. |
| A grant covers the work through the named end state | It prevents a permission request at every step. |
| Limits stay in force until lifted | Limits get forgotten over long sessions and after compaction. |
| Production only when named | "Land it" is ambiguous and a production deploy is hard to undo. |
| "one time" means once | It stops a single exception becoming a precedent. |
| A budget is a hard cap | A model tends to treat a figure as a target to spend up to. |
| "feel free" is permission, not an order | It stops optional work becoming mandatory. |
| Irreversible or outward-facing actions must be named | A broad grant should not reach them by inference. |
| Preconditions first, and shown | A precondition such as a backup is the safety net, and showing it lets you verify it happened. |
| Stay in my lane | Parallel agents collide on PRs and deploy slots. |
| Teammates own some systems | Your delegation cannot grant authority you don't hold. |
| Unattributed changes are yours | Reverting an unknown diff destroys work that is often not recoverable. |
| Grants don't cross sessions or tabs | A relayed approval cannot be verified, so authority has to trace back to your own words. |
| Production trouble: read-only first | Under pressure, hasty writes compound the damage, and teammates are editing the same documents. |

## How to work

| Rule | Why it is there |
|---|---|
| Numbered proposals | You answer by number, so unnumbered options cannot be picked. |
| Diagnose before naming the fix | It prevents symptom patches. |
| Live evidence outranks memory | Summaries and agent reports go stale or are wrong. |
| A failed write has an unknown result; waits get a time limit | A blind retry can run the action twice, and an unbounded wait hangs an unattended run. |
| Never weaken checks | It is the cheapest way to get a green result and it hides the real failure. |
| Finish the scope, then stop and propose | It keeps the work inside the grant while still surfacing the next step. |
| Final-form merges | A known shortcut on `main` tends to stay there, and flagged dead code still needs maintaining. |
| Batch questions through the `ask` tool | Questions in prose get buried, and batching costs you one interruption. |
| Keep maps and ExecPlans current | Sessions end and context is lost, so unwritten findings are lost with them. |
| Commit in pieces, rebase, auto-merge opt-in | Small commits are reviewable, a rebase catches drift, and auto-merge removes your last checkpoint. |
| Latest stable versions, cheaper model ids | My training data is behind, so I default to outdated ones. |
| Never print secrets | Transcripts, files and logs get stored and shared, so a printed secret is a leaked one. |

## Second brain

| Rule | Why it is there |
|---|---|
| The vault is the durable store; read the skill first | It carries context across projects, and the skill holds the sync procedure. |
| Read `Now.md` at the start, record at the end | Otherwise each session starts cold and its lessons are lost. |
| Standing grant, this vault only, no force-sync | It removes the permission prompt for routine notes, bounds it to one repo, and protects other devices writing to the same vault. |
| Notes are context, not authority; no credentials | A stale note must not authorize an action, and the vault syncs to many devices. |

## Writing for people

| Rule | Why it is there |
|---|---|
| Write from the user's intent | My default is to describe the mechanism. |
| Coworker documents assume zero context and take a position | Readers lack the session history, and a hedged document does not help them decide. |
| Print raw URLs | The renderer can hide link targets. |
| Say which state is true (local, pushed, merged, deployed, proven live) | "Done" is ambiguous across those five states, and the differences between them matter. |
