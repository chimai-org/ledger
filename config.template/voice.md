# VOICE

**This file ships filled in and works as it stands.** Copy it to `config/voice.md` and run LEDGER without editing a line. Everything below is a sensible default rather than anyone's house style, chosen so the findings read as plain human writing. Change what you disagree with, delete what does not apply, add your own rules as you find them. The two sections most worth making yours are *Reading level* and *Your own additions* at the bottom.

Scope: this file governs **wording only**. The engine owns the reasoning, the order of each entry, and the honesty gates. Where this file and the engine disagree on wording, this file wins. Where they disagree on honesty, the engine wins, and nothing you write here can change that.

If you already keep a style document, point at it here and treat the rest as a starting set.

---

## Reading level for the actions

The single setting that decides whether the document gets used.

**Target: the subject can read an action at the end of a long day and know what to do the next morning, without re-reading the sentence.**

Ordinary words, short sentences, no term that needs a glossary. No framework names, no internal shorthand, no abbreviation the reader has not already met in the same document. If an action reads like software documentation, it is wrong even when it is accurate.

## Person and address

- Speak to the subject directly, in the second person. "You keep" rather than "the subject keeps".
- First person is fine for the analysis itself where it helps, as in "we could not read the calendar".
- Contractions are fine. They read as human.
- Write in the subject's own working language. If the record is bilingual, write the findings in whichever language the subject uses for decisions, and leave quoted material in its original language.

## Sentence construction

- **Write full sentences.** Fragments used for emphasis are the most common machine tell in an otherwise good draft.
- **Vary the length.** Findings arrive in different sizes because they are different sizes. Uniform paragraph weight is what a reader registers as machine writing even when they cannot say why.
- **One idea per sentence** in the action block. Elsewhere, follow the argument.
- **No verdict language in the summary.** The one page states facts in an order the reader has not seen before. It does not tell them how to feel about the facts.

## Banned constructions, with runnable checks

Run these over the finished document. A machine never forgets a rule and a person always does. Replace `output.md` with your filename.

**Em-dashes.** Use a comma, a full stop, or a colon.
```
grep -n "—" output.md
```

**The "not X, but Y" contrast** used as a setup for a positive claim. State the positive directly and drop the negative half. A standalone factual negation is fine.
```
grep -niE "not [a-z ]{2,30}, but |it is not .{2,40}, it is |isn't .{2,40}, it's " output.md
```

**Paired aphorisms** of the shape "A is an X. B is a Y." Two short parallel sentences that sound profound and carry one thought between them. Join them into one real sentence, or cut one.
```
grep -nE "\b(is|are) an? [a-z]+\. [A-Z][a-z]+ .{0,45}\b(is|are) an? [a-z]+\." output.md
```

**Colon reveals**, where a phrase is followed by a colon and one dramatic clause.
```
grep -nE "^[A-Z][^.!?]{10,60}: [a-z]" output.md
```

**Weasel attribution**: "experts say", "research suggests", "studies show", with nothing behind it. Every claim in this document carries its own evidence block, so an unattributed appeal is always a defect.
```
grep -niE "experts (say|agree)|research (suggests|shows)|studies show|it is (widely )?believed" output.md
```

**Hedging stacks** such as "it seems that this may possibly indicate". Say it or do not, and put the uncertainty in the confidence number, which is what it is for.
```
grep -niE "(seems|appears) to (possibly|perhaps)|may possibly|might potentially|could potentially" output.md
```

**Summary-recap endings** that restate what the reader just read. Each entry ends on its sources. The document ends on the counter-case. No check for this one, it needs a person.

## Words to avoid

Corporate and AI-hype vocabulary reads as filler in a document about someone's actual life or business.

```
grep -niE "\b(leverage|delve|foster|seamless|robust|holistic|synerg|game.chang|unlock|revolutioniz|cutting.edge|harness|elevate|myriad|plethora|in today's)\b" output.md
```

Keep any of these where it is the precise word. "Leverage" as a noun meaning mechanical advantage is fine; as a verb meaning "use" it is not. The check is there to make you look, not to make you delete.

## What this file must never contain

- Instructions to soften a finding, drop a counter-case, or raise a confidence number. Those are honesty gates and they live in the engine.
- Permission to use clinical or diagnostic labels about the subject or about anyone they describe.
- A named author to imitate. If you want to specify the register further, anchor it in your own writing.

## Your own additions

Add rules here as you find them, dated, with the failing example attached. A rulebook that remembers your own corrections is worth more than any list you inherit, this one included.

```
## YYYY-MM-DD, short name for the rule
Failing example: "<the line that was wrong>"
Fix: "<the line after correction>"
Check: <grep, where it can be mechanised>
```
