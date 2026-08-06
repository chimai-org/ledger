# LEDGER · setup guide

Budget an hour for the configuration, once. The run itself takes longer and should.

---

## 1. Decide what you are reading

A person or an organisation. The moves are identical; what changes is which evidence counts and what the reader wants out of it.

**A person** works when there is a real archive of their own words and choices over at least several months. Chat logs with an assistant, a personal task system, a journal, commit history, sent mail. Less than a few months of material produces a snapshot rather than a reading, and the corpus note will have to say so.

**An organisation** is usually the stronger case, because more of it is written down and less of it is memory. Strategy documents, goal files, CRM history, meeting notes, delivery repositories, invoices. The findings tend to be sharper too, because an organisation contradicts itself in writing.

Write the answer into `config/subject.md` along with the domains that count and the domains that are deliberately out of bounds.

## 2. Point at a corpus without handing it over

The engine never asks you to upload anything. It asks you to name locations an agent already has access to.

Good sources share three properties. They were written for a purpose other than being analysed, so they are not performances. They carry timestamps, so patterns can be dated. And they record actions, not only intentions.

A practical way to prepare a large chat archive is to extract only the messages the subject wrote themselves, with timestamps, and drop the assistant's replies. In most archives that reduces the volume by an order of magnitude and removes the single biggest contaminant, which is a previous model's interpretation being read back as though it were evidence.

Write into `config/corpus.md`: where each source lives, roughly how far back it goes, and what you already know is missing from it. That last part matters more than it looks. The corpus note in the output is only as honest as this file.

**What to keep out.** Other people's private material, client-confidential content, anything under an obligation you would not want quoted back. If a source contains some of this, either exclude it or state the exclusion. An analysis that quietly reads privileged material is a liability, not a deeper reading.

## 3. Set the voice

`config/voice.md` governs wording only. If you already keep a style document, point at it rather than copying it.

The two things worth specifying even if you keep nothing else: the constructions you never want to see, and the reading level you want the actions written at. The second one is easy to under-specify and it is the one that decides whether the document gets used. A good target is that a person could read an action at the end of a long day and know what to do tomorrow morning without re-reading it.

The engine will not let a voice config make the output less honest, only blunter or softer in wording.

## 4. Run the six moves as separate passes

Not one prompt. The gates are the method.

A workable sequence with an agent:

1. **Limit.** Ask for the corpus boundary only. Real dates, real counts, domains present and absent, and the direction of the source's structural bias. Read it before continuing. If the dates look wrong, the rest will be wrong.
2. **Extract.** Ask for five to eight threads, each with the periods and domains its evidence comes from. Read these too. This is the cheapest place to catch an analysis that has decided on a story early.
3. **Diagnose and Guide**, per candidate finding. Expect more candidates than you will keep.
4. **Evidence.** Context, counter-case and sources per finding, plus the confidence line.
5. **Reduce.** Rank by weight, cut to ten, report how many were cut.
6. **The one page**, last, from the ten that survived.

Splitting the passes costs a little time and buys the two things that make the output trustworthy: you can stop a wrong reading at step 2 instead of at step 6, and the summary genuinely cannot have been written first.

## 5. Read it properly once

Set aside an hour and read it in one sitting, in order, without stopping to argue. Then go back to the top and argue.

Two things to check specifically, because they are where this genre fails:

**Does every finding trace to a thread from move E?** If one appears from nowhere and reads beautifully, that is the sound of a theory the evidence did not carry.

**Is the counter-case real?** A token concession followed by "but the pattern holds" means the finding was never tested. A genuine counter-case will sometimes cost the finding its ranking, and it should.

## 6. Do one thing

The output ends with the single action that would make most of the others unnecessary. That choice is the method's, and it is the last decision it gets to make.

Which of the ten you actually act on is yours, and the honest failure mode of a document like this is that it gets read, admired, and filed. If you do nothing within two weeks, the run produced a document rather than a change, and it is worth asking whether the ranking was wrong or whether the finding was simply one you did not want.

## 7. Run it again later, not sooner

There is no value in a monthly cadence. The material has to move before the reading can change, and a re-run against a corpus that has grown by three weeks will mostly reproduce itself with fresh phrasing, which is a good way to mistake repetition for confirmation.

Twice a year is a reasonable rhythm for a person. For an organisation, before an annual or quarterly planning session, so it lands where decisions are actually made.

When you do re-run, keep the previous output out of the agent's context. A second reading that has been shown the first one will agree with it.
