# LEDGER

![LEDGER, a scattered field of record fragments resolving into ten ranked bars](assets/ledger-cover.png)

**Limit · Extract · Diagnose · Guide · Evidence · Reduce**

A method for reading your own record back to yourself, honestly. Ten ranked findings: what is holding you back, and what is already working and worth protecting. The engine is open source; the record stays on your machine.

---

## Why this exists

You already have the evidence.

Somewhere on your machine there is a year of what you actually did. Not the version you would give in an interview. The real one: every question you asked at seven in the morning, every project you started and quietly dropped, every rule you wrote down for other people to follow, every time you broke it. Chat logs, commit histories, CRM records, meeting notes, task lists. Hundreds of thousands of words about a single person or a single company, written without any intention of being read as a whole.

Nobody reads it as a whole. Not you, because you were there and it feels like memory rather than data. Not your advisors, who get an hour and your own summary of the situation, which is exactly the account the record is most likely to contradict.

So the gap between what you believe about how you spend your time and what your calendar proves you did is not hidden anywhere. It is simply unread.

## What usually goes wrong when you try

Prompts that ask a model to analyse your history have been circulating for a while. Run a few and the same four problems show up.

They flatter. A model that has read a year of your work has also learned to be agreeable about it, and agreeable analysis of your own life is worse than useless, because you will believe it.

They bury the point. Three paragraphs of framing arrive before you learn what was found, and the thing you could actually do about it sits at the bottom, after the argument, where a tired reader never reaches it.

They give you twenty findings. Twenty findings feels thorough and behaves like noise. You act on two, and the two you pick are the comfortable ones.

They write the summary first. Which means the summary states a thesis and the findings are recruited to support it, instead of the summary being what survived the findings.

## What LEDGER does differently

Four decisions, and they are the whole method.

**The boundary is declared before anything is read for meaning.** Real dates, real volume, which domains are absent, and which way the source is structurally biased. A chat archive over-represents deliberation and under-represents commitment, for everyone, in the same direction, because people bring open questions to an assistant and then go decide somewhere else. Naming that bias before you read is what stops "he circles without committing" from being manufactured out of a filing artifact.

**The answer comes before its justification.** Each finding opens with one sentence saying what is true, then a short paragraph making it concrete, then what to do about it this week. The context and the sources come afterwards, where they can be checked by the reader who wants to check and skipped by the reader who does not.

**Ten findings, ranked by weight.** Weight means consequence multiplied by confidence: how much changes if this is true and you act, times how sure the evidence lets anyone be. A brilliant observation at confidence 4 ranks below a plain one at confidence 9. The rest get cut, and the count of what was cut is reported, so ten never reads as everything there was.

**The one page is written last.** From the ten that survived, never drafted first and backfilled. It carries the central tension, the strength available to meet it, the direction of travel, and the single action that would make most of the others unnecessary.

## The six steps

Each has to be finished before the next may start. Full definitions with gates: [`SKILL.md`](SKILL.md).

**Limit.** State what could actually be read and what could not, in real dates and real counts. Every later claim is capped by this. If the reach cannot be stated, the run stops here.

**Extract.** Find five to eight threads that recur across more than one period and more than one domain, before answering anything. A pattern repeated forty times inside one conversation is still one episode. What someone repeatedly did outranks what they said about themselves.

**Diagnose.** One finding per entry, in the first sentence. Specific enough to be impossible to paste into someone else's report, and falsifiable enough that some evidence could have contradicted it.

**Guide.** One or two actions, startable this week, in sentences a tired person understands. Where the finding is a strength, the action is how to protect it, because a strength with nothing attached is a compliment.

**Evidence.** Context, then the strongest case against the finding stated fairly, then the sources: dates, counts, exact quotes only where certain. Placed after the answer on purpose.

**Reduce.** Rank, keep ten, then write the one page from what survived.

## Where the weight comes from

The hard part of a document like this is not finding something uncomfortable. Anything will feel uncomfortable if you write it sharply enough, and a model will happily generate discomfort on request.

The hard part is being right, and then getting out of the way.

A finding lands when it is a fact the reader cannot argue with, arranged next to another fact they had never put beside it. A rule someone wrote down in April, and the number of times the log shows them breaking it since. The channel every deal actually closed through, next to the channel that got the year's engineering. Two sentences from their own strategy document that cannot both be true.

None of that needs adjectives. The method bans verdict language and drama vocabulary in the summary for exactly this reason. Dates, counts, their own words, in an order nobody has arranged before. That is where the effect comes from, and it is the reason accuracy is not a constraint on the impact but the source of it.

## The honest price

The output will sometimes be wrong, and it is built to tell you where. Every finding carries a confidence number committed to before the entry is written, the strongest counter-case stated fairly rather than as a token, and a standing bias check on the analysis itself. A reading that cannot say how it might be wrong should not be trusted with a reading of your life or your company.

It also cuts things you wanted. Ten means ten, and something you would have found interesting will lose to something you will find useful.

And it does not go looking for pathology. There are no clinical labels in the output, about you or about anyone you mention, and a question you once asked is never treated as proof of a thing you did. Curiosity is not conduct. That constraint is in the engine and no configuration can switch it off.

## What is in this repository

| File | What it is |
|---|---|
| [`SKILL.md`](SKILL.md) | The engine. Six moves as an agent-executable skill (Claude, Codex and compatible runtimes), versioned, with a changelog. Carries no subject and no house voice. |
| [`config.template/`](config.template/) | The three files you fill in once: your subject, your corpus, your voice. Copy to `config/`. |
| [`GUIDE.md`](GUIDE.md) | The setup walkthrough, including how to point it at a corpus without handing anything over, and how to run the moves as separate passes. |

**How the split works:** the engine never contains your subject, your sources or your voice, and your `config/` never leaves your machine. You can pull engine updates forever without touching any of it, and contribute engine improvements without leaking it. Where the engine and your voice config disagree on wording, your config wins. Where they disagree on honesty, the engine wins.

**Person or company.** The same six moves read a founder or a business. What changes is the SUBJECT config: which domains count, and what the reader wants it for. A company's record is usually the better corpus, because more of it is written down.

## Running it

Point your agent at `SKILL.md` with your `config/` next to it. The skill instructs the agent to run the six moves as separate passes with gates between them, never as a single prompt. The corpus stays where it is.

The one thing that stays manual, and should: deciding which of the ten findings you are actually going to act on. The method ranks them. It does not get a vote.

---

## Provenance

This method makes no novelty claim. Prompts that read a user's history and report patterns back have circulated widely since long-context models became common.

The specific prompt that prompted this one was [kropdx/reflection-engine](https://github.com/kropdx/reflection-engine), which we ran end to end against our own archive in August 2026. Credit where it is due: the output changed three decisions for us the same day. It was also structurally frustrating in four ways, and those four complaints are the entire design brief here. Twenty-two findings where a reader acts on two. The action buried under the argument. The summary written first, with the evidence recruited to it afterwards. And no ranking, so the reader does the triage the method should have done.

That repository states no licence, so nothing from it has been copied: no text, no phrasing, and none of its questions. Its fixed question list is replaced here by a sweep of finding classes followed by a ranking, which is a different mechanism rather than a reworded one.

What is ours is the contract. The boundary declared before reading, the answer before its justification, the ranking to ten, the summary written last from what survived, and the two standing checks. Those checks predate the method; they come from the operating rules of the team that built it, where a bias scan and an adversarial counter-case are required before any significant analysis ships.

Built by [chim.ai](https://chim.ai), Vienna. Companion method for the writing layer: [SHAPE](https://github.com/chimai-org/shape).

## License

MIT. See [`LICENSE`](LICENSE).
