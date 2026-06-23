# Copywriting: strip the AI tells out of prose

Words in a design are material, not decoration (the SKILL.md says this). This
file is the deeper craft: how to write or fix prose, microcopy, headlines, and
body so it reads as written by a person, not generated. It applies anywhere a
human reads text on the page, and equally to standalone writing (essays, posts,
emails) when the skill is invoked for copy alone.

The single highest-frequency tell is the em-dash, banned in shipped copy with no
exceptions (see `anti-slop.md`). Everything below is the rest of the catalogue.

## Core rules

1. **Cut filler.** Remove throat-clearing openers ("Here's the thing:", "It
   turns out"), emphasis crutches ("Let that sink in", "Make no mistake"), and
   all adverbs. The full ban-list is in `copy-banlist.md`.

2. **Break formulaic structures.** No binary contrasts ("not X, it's Y"), no
   negative listing ("not a A, not a B, but a C"), no dramatic fragmentation
   ("Speed. That's it."), no rhetorical setups ("What if I told you"). State the
   point directly. Patterns and fixes in `copy-banlist.md`.

3. **Use active voice with a human subject.** Every sentence has a person doing
   something. No passive constructions that hide the actor. No inanimate object
   performing a human verb ("the complaint becomes a fix", "the decision
   emerges") - name who did it, or use "you" to put the reader in the seat.

4. **Be specific.** No vague declaratives ("The reasons are structural", "The
   implications are significant") - name the specific thing. No lazy extremes
   ("every", "always", "never", "everyone") doing vague work where a real number
   or example belongs.

5. **Put the reader in the room.** "You" beats "People". Specifics beat
   abstractions. No narrator-from-a-distance voice ("Nobody designed this",
   "People tend to").

6. **Vary rhythm.** Mix sentence lengths. Two items usually beat three. End
   paragraphs differently instead of always landing on a punchy one-liner. No
   em-dashes, ever.

7. **Trust the reader.** State facts directly. Skip softening, justification,
   permission-granting ("And that's okay"), and hand-holding.

8. **Cut quotables.** If a line sounds engineered to be a pull-quote, rewrite it
   as a plain functional sentence. Boring beats clever-wrong.

## Interface-copy rules (when the prose lives inside a UI)

These extend the core rules for product surfaces, carried over from the SKILL.md
writing section:

- **Name things by what the user controls**, never by how the system is built. A
  person manages notifications, not webhook config.
- **An action keeps its name through the whole flow.** The button that says
  "Publish" produces a toast that says "Published". One label per intent across
  nav, hero, and footer ("Get started" / "Try free" / "Sign up" are the same
  button - pick one).
- **Failure and emptiness are direction, not mood.** Errors say what went wrong
  and how to fix it, in the interface's voice, never apologising or staying
  vague. An empty screen is an invitation to act.
- **Sentence case, plain verbs, no filler.** Tone matched to brand and audience.
  Each element does one job: a label labels, an example demonstrates.

## Quick checks (run before delivering any prose)

- Any adverbs (-ly, "really", "just", "actually", "simply")? Kill them.
- Any passive voice? Find the actor, put them at the front.
- Inanimate thing doing a human verb ("the data tells us")? Name the person.
- Sentence starts with a Wh- word (What/When/Why/How)? Restructure to lead with
  the subject or the specific thing.
- Any "here's what/this/that" throat-clearing? Cut to the point.
- Any "not X, it's Y" contrast? State Y directly, drop the negation.
- Three consecutive sentences the same length? Break one.
- Paragraph ends on a punchy one-liner? Vary it.
- Em-dash anywhere? Remove it (comma, period, parentheses, or two sentences).
- Vague declarative ("The stakes are high")? Name the specific stake.
- Narrator-from-a-distance ("This is why...")? Put the reader in the scene.
- Meta-joiner ("The rest of this essay...", "As we'll see")? Delete it. Let the
  text move.
- Fake-precise number ("92%", "4.1x") not from real or labelled-mock data? Cut
  the false precision (see `anti-slop.md`).
- Generic name or brand (John Doe, Acme, Nexus)? Replace with specific,
  realistic, locale-appropriate invented names that sound real.

## Scoring (use when asked to rate or when iterating)

Rate 1-10 on each dimension, then revise the weakest first:

| Dimension | Question |
|-----------|----------|
| Directness | Statements, or announcements about statements? |
| Rhythm | Varied sentence lengths, or metronomic? |
| Trust | Respects the reader's intelligence? |
| Authenticity | Sounds like a person wrote it? |
| Density | Anything left that could be cut? |

Below 35/50: revise before delivering.

See `copy-banlist.md` for the exhaustive phrase and structure tables, and
`copy-examples.md` for before/after rewrites.
