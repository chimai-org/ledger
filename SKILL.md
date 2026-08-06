---
name: ledger
version: 0.1.0
description: >
  LEDGER method (Limit · Extract · Diagnose · Guide · Evidence · Reduce). Reads a
  subject's own accumulated record and returns ten ranked findings, each written
  finding-first with a concrete action, plus a one-page summary written last.
  Works on a person or on a business. Trigger: "read my record", annual review,
  founder or team retrospective, pre-planning diagnosis. The engine carries no
  house voice and no subject of its own; it REQUIRES a configuration (see
  Interface). Never run all six moves in a single prompt.
license: MIT
---

# LEDGER · the engine

Six moves, run as separate passes with gates between them. The method governs what may be claimed and in what order it reaches the reader. It does not govern what you will find.

**This file is config-agnostic by design.** Everything specific to one subject, one company, one house voice lives in the configuration, never here. If you want to add a person's name, a company's values or a style rule to this file, it belongs in a config instead. That separation is what lets the method and any subject's specifics evolve independently.

---

## What this produces

One document. In this order:

1. **The one page.** A single-page summary. Written last, read first.
2. **Ten findings**, ranked, heaviest first.
3. **The corpus note.** What was read, what was missing.
4. **A bias check and a counter-case.**

Ten, not twenty. The cut is the method working, not the method running out.

---

## Interface: what a configuration must provide

Resolve the configuration before running move L. Look for a `config/` directory next to this file; if it is missing, copy `config.template/` to `config/` and fill it in. [`GUIDE.md`](GUIDE.md) walks through it.

| Slot | File | Contents |
|---|---|---|
| SUBJECT | `config/subject.md` | Who or what is being read: a person or an organisation. Which life or business domains count. What the reader wants this for. What is out of bounds. |
| CORPUS | `config/corpus.md` | Which sources may be read, where they are, and their known blind spots. The access limits belong here, not in the output. |
| VOICE | `config/voice.md` | How the findings must read. Banned constructions as runnable checks. **Ships pre-filled with a working default**, so an adopter who writes nothing here still gets plain, checked prose. May also point at an existing style document. |

Config files may be thin pointers to documents a team already keeps. Pointers beat copies: a copy drifts, a pointer stays true.

**Precedence rule:** where this engine and the VOICE config disagree on wording, VOICE wins. The engine owns the reasoning and the order; the config owns the language.

**Standing constraint, not negotiable by config:** no clinical labels and no clinical diagnosis of the subject or of anyone they describe, and no claim that outruns its evidence. A config may make the output blunter. It may not make it less honest.

---

## Move L · Limit

**Bound the corpus before reading it for meaning.** Write these down first, because every later claim is capped by them:

1. **Reach.** Earliest and latest material actually accessible. Real dates.
2. **Volume.** How much, in units a reader can picture. Not "extensive".
3. **Domains.** Which parts of the subject's life or business appear, which appear thinly, which are absent.
4. **Distribution.** Where the material clusters. A corpus that is 55 percent one month is not a corpus about a year.
5. **The channel's bias.** Every archive over-represents something structurally. A chat log over-represents deliberation and under-represents commitment, for everyone, in the same direction, because people bring open questions to an assistant and go decide elsewhere. A CRM over-represents what someone chose to record. Name the direction of the bias, then correct for it in every later move.

**Gate:** if you cannot state the reach in real dates, stop. Do not proceed on an assumed corpus.

**Hard rule:** claim only what was read. "I reviewed the archive" when three files were sampled is the failure this move exists to prevent.

---

## Move E · Extract

**Find the threads before answering anything.** Five to eight patterns, each supported from more than one period and more than one domain. One line each, naming where the evidence comes from.

Rules that make this real rather than decorative:

- **Independent recurrence.** A pattern repeated forty times inside one conversation is one episode. Weight patterns that recur without a shared cause.
- **Behaviour over statement.** What the subject repeatedly *did* outranks what they said about themselves, and both outrank what a previous summary concluded about them.
- **Distinguish the kinds.** A stable trait, a temporary state, a one-off, a stated aspiration, an idea explored once, an action taken repeatedly, and a transcription artifact are seven different things. Mixing them is how a portrait becomes fiction.
- **Curiosity is not conduct.** Asking about a thing is not evidence of doing it.
- **Absence is weak evidence.** A decision that never appears in the record was probably made elsewhere. Before concluding avoidance, require positive evidence: the topic returns in the same open form after enough time has passed that action was possible, or the subject says it is still unresolved.

**Gate:** every finding in move D must trace to this list. A finding that is not on it means you reached for a theory the evidence does not carry. Go back or drop it.

---

## Move D · Diagnose

**One finding per entry, stated in the first sentence.**

The first sentence names what is true. Not what will be discussed, not why it matters, not a preamble that earns the point. The point.

Then at most one short paragraph, roughly 120 words, that makes the finding concrete: what it looks like in practice, what it appears to cost or enable, where it appears to be heading. Plain sentences a tired reader understands at the end of a long day.

**What a finding must be:**

- **Specific.** Names actual behaviour, actual decisions, actual dates. "You are ambitious" is not a finding.
- **Non-obvious.** If the subject would have written it themselves, it is a summary, not a reading.
- **Falsifiable.** A finding that no evidence could contradict is a horoscope.
- **Theirs.** It should be impossible to paste into someone else's report.

**What a finding must not be:** flattery, manufactured harshness, a clinical label, or a restatement of the subject's own self-description.

---

## Move G · Guide

**What to do, immediately after the finding and before any explanation.** This is the payload. Everything else in the entry exists to earn it.

Requirements:

- **One or two actions, not a list.** High leverage beats complete.
- **Startable this week**, with what the subject already has.
- **Written for a person.** Short plain sentences, ordinary words, no framework names, no jargon, no instruction that requires a glossary. If it reads like software documentation, rewrite it.
- **Name the likely dodge**, but only when the dodge is specific to *this* finding. A generic "you might resist this" is filler. Do not repeat the same predicted resistance across entries.
- **Give an observable sign.** One thing the subject could notice within weeks that would show the change is real. Prefer a sign that is countable or binary over one that requires judgment.

**Where the finding is a strength:** the action is how to protect it and lean into it, with the same specificity. A strength with no action attached is a compliment.

**Gate:** if the action could be given to a stranger without changing a word, it is too generic. Rewrite it against the evidence.

---

## Move E · Evidence

**The grounding goes after the answer, not before it.** The reader who accepts the finding has already got what they came for. The reader who does not can check.

Each entry closes with, in this order:

1. **Context.** Roughly 100 words. Where this sits in the subject's wider picture, and what else it touches. Not a re-argument of the finding.
2. **Counter-case.** The strongest thing that cuts against the finding, stated fairly rather than as a token concession. If there genuinely is none, say so; if there is one and it is strong, the confidence number must reflect it.
3. **Sources.** The specific evidence. Dates, counts, quoted phrases where they are certain, named decisions and artifacts. A list, not prose.

**Quotation rule:** quote only what you are certain is verbatim. Otherwise paraphrase and say you are paraphrasing. An invented quote destroys the credibility of every real one in the document.

**Confidence line.** Each entry opens with one line, before the finding, so the reader knows what weight to give it:

`Confidence 8/10 · Evidence broad · Basis: recurs across four periods and three domains, one real counterexample.`

- **9–10** repeated, specific and consistent across periods and domains, little meaningful counterevidence
- **7–8** a clear recurring pattern, several independent examples, some ambiguity or narrower coverage
- **4–6** plausible and partly supported, but limited, mixed or concentrated in one period
- **1–3** speculative, sparse, or not answerable from what was available

Commit to the number before writing the entry. If drafting changes your assessment, change the number, not the argument.

---

## Move R · Reduce

Two cuts, same verb.

**First cut: the ten.** Sweep wide, ship narrow. Work the candidate classes below, then rank and keep ten. Rank by **weight**, which is consequence multiplied by confidence: how much changes for the subject if this is true and they act on it, times how sure the evidence lets you be. Heaviest first. A brilliant observation at confidence 4 loses to a plain one at confidence 9.

Candidate classes to sweep (not a template to fill, and not all will earn a place):

| | |
|---|---|
| The blind spot with the most leverage | The contradiction that explains the most |
| Motion mistaken for progress | The thing already known but not acted on |
| The most expensive habit | What is quietly compounding in their favour |
| The likely regret on this trajectory | The gap between how they read and what they are |
| Complexity that outgrew its purpose | The bet the pattern of choices is making |
| What is being solved that needs accepting | The strength that needs protecting, not fixing |

**Cutting rules:** no two entries may make the same argument in different words. When two findings share a root, merge them and rank the merged one higher. Say plainly in the corpus note how many candidates were cut, so the ten do not read as everything there was.

**Second cut: the one page.** Written last, from the finished ten, never drafted first and backfilled. One page. If it runs to two, it is not finished.

The page carries: the central tension, the strength available to meet it, the direction of travel, and the one action that makes most of the others unnecessary. That last item is chosen from the ten, never newly invented here.

**How the page lands.** The effect comes from accuracy, not from adjectives. A reader should feel the weight because the facts are undeniable and arranged in an order they had never put them in, not because the prose told them to feel something. Dates, counts, their own words. No verdict language. No drama vocabulary. The most unemotional register you can manage, applied to material that is anything but.

**Gate:** if the one page contains a claim that is not in the ten, delete it.

---

## The two standing checks

Run both before the document is finished, and include them at the end.

**Bias check.** Scan the findings and your own reasoning for the failure modes that make an analysis like this worthless: confirmation bias, where each new piece of evidence gets recruited into a theory chosen early; over-reading recency because the recent material is denser; treating a plausible narrative as a proven one; and inheriting a previous analysis's conclusions as if they were data. Where one applies, say so and say how it should discount the finding.

**Counter-case.** Argue the whole document down, in the sharpest voice you can manage, as someone with no stake in it being right. If the sceptic's reading survives contact with the evidence, the findings above are not finished.

Both belong in the output. A reading that cannot state how it might be wrong should not be trusted with a reading of someone's life or company.

---

## Anti-patterns

The failure modes this method is built against, each observed in real runs of the genre:

- **Preamble before payload.** Three paragraphs of context before the reader learns what was found. The order in D → G → E exists to make this structurally impossible.
- **Volume as rigour.** Twenty findings signals thoroughness and delivers dilution. The reader acts on two. Ranking to ten is the product.
- **One theory in twelve costumes.** The same master conclusion restated per entry, which reads as coherence and is actually a corpus that produced one insight.
- **Machine cadence.** Uniform paragraph weight, every point landing with the same force, sentence pairs of the shape "X is a mood. Y is a control." Findings arrive in different sizes because they are different sizes.
- **Pathologising.** Clinical vocabulary applied to observable behaviour. Describe the dynamic and its cost; the label adds nothing and claims standing you do not have. This method diagnoses a situation, never a person.
- **Confident thinness.** Prose smoothing over a gap where evidence should be. When the corpus cannot answer something, that sentence is the finding.
- **Cruelty read as courage.** Harshness manufactured to seem unflinching. The uncomfortable finding is worth having only when it is well supported.

---

## Provenance

The genre this belongs to is not new, and this method makes no novelty claim. Prompts that ask a model to read a user's accumulated history and report patterns back have circulated widely since long-context models became common. The direct predecessor here is [kropdx/reflection-engine](https://github.com/kropdx/reflection-engine), run end to end in August 2026. Its output was genuinely useful and structurally frustrating in four ways: too many findings, the action buried under the argument, the summary written first, and no ranking. Those four complaints are the design brief for this engine. That repository states no licence, so nothing from it is reproduced here.

What is ours is the contract: the boundary declared before reading, the answer before its justification, ranking to ten, and the summary written last from what survived. The standing bias and counter-case checks come from the operating rules of the team that built this, where they predate the method.

## Changelog

**0.1.0** · first release. Six moves, ten-finding contract, finding-first entry order, summary-last.
