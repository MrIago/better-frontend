# Output discipline: ship the whole thing, no placeholders

Design and copy work both fail the same quiet way: the model truncates. It
emits `// rest of code here`, builds three of eight sections, or describes what
the code would do instead of writing it. Pull this in for any large build,
multi-file output, or full-page generation where the risk is shipping a
skeleton.

## The rule

Treat every task as production-critical. A partial output is a broken output.
If the user asks for a full file, deliver the full file. If they ask for 8
sections, deliver 8. Optimise for completeness, not brevity.

## Banned output patterns (hard failures)

- **In code:** `// ...`, `// rest of code`, `// implement here`, `// TODO`,
  `/* ... */`, `// similar to above`, `// continue pattern`, `// add more as
  needed`, a bare `...` standing in for omitted code.
- **In prose:** "Let me know if you want me to continue", "I can provide more if
  needed", "for brevity", "the rest follows the same pattern", "similarly for the
  remaining", "and so on" replacing real content, "I'll leave that as an
  exercise".
- **Structural shortcuts:** a skeleton when a full implementation was asked for;
  showing the first and last section and skipping the middle; one example plus a
  description of the rest; describing code instead of writing it.

## Process

1. **Scope.** Count the distinct deliverables (files, sections, components,
   answers). Lock that number.
2. **Build.** Generate every deliverable completely.
3. **Cross-check.** Re-read the original request, compare your deliverable count
   to the locked scope, add anything missing before responding.

## Long outputs near the limit

Do not compress remaining sections to fit, do not skip to a conclusion. Write at
full quality to a clean breakpoint (end of a function, file, or section), then:

```
[PAUSED - X of Y complete. Send "continue" to resume from: next section name]
```

On "continue", resume exactly where you stopped. No recap, no repetition.

## Why this happens (so the rule sticks)

Truncation is a trained behaviour, not a capability or memory failure. Knowing
the mechanism is what lets you override it instead of drifting back:

- **Brevity bias from alignment.** RLHF and compute economics reward short,
  confident summaries over full multi-step work. The model has a learned
  preference to stop early.
- **Placeholder propagation from training data.** Stack Overflow, tutorials, and
  docs are full of `# implement here` and "similarly for the rest". The model
  treats truncation-with-a-comment as a legitimate professional answer.
- **Stopping pressure + error avoidance.** Autoregressive models learn to
  conclude; longer outputs raise the surface area for mistakes, so the model
  truncates to play safe.
- **Output-budget pre-compression.** When the model estimates the full answer
  exceeds its output cap, it pre-emptively summarises rather than risk an abrupt
  cutoff. Chunk the work instead (outline → each component in full → assembly).

Empirically, no frontier model natively satisfies both length and all sub-part
instructions without this kind of explicit binding. The fix is to lock scope,
forbid the placeholder patterns, and chunk rather than compress.
