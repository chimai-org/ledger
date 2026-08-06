# CORPUS

Which sources may be read, where they live, and what you already know is missing from them. Thirty minutes, once.

**Nothing is uploaded.** You are naming locations an agent already has access to on your own machine or in systems you already use. The engine reads them in place.

**The output's honesty is capped by this file.** The corpus note in the finished document reports what was read and what was missing, and it can only report what you wrote here. A gap you do not name becomes a claim the analysis makes too confidently.

---

## Where to look

Most people underestimate how much record they already have. Work through this list and take the four or five richest sources rather than everything.

| Source | Where it usually lives | What it is good for |
|---|---|---|
| **Assistant chat history** | Claude Code: `~/.claude/projects/<project>/*.jsonl`. ChatGPT: Settings, Data controls, Export. Most tools have an export. | The richest single source for a person. Timestamped, unperformed, and it records the questions you asked before you knew the answer. |
| **A working folder or vault** | Your projects directory, an Obsidian vault, a Notion export, a Drive folder | Structure over time. Which folders grew, which were abandoned, what got renamed and when. |
| **A repository** | `git log --format='%ad %s' --date=short` in any repo you work in | What was actually built and when, as opposed to what was planned. |
| **CRM** | Attio, HubSpot, Pipedrive, a spreadsheet | Deals, sources, stages, and the gap between what was forecast and what closed. |
| **Sent mail** | Your mail client's sent folder, filtered by date | How you actually talk to people, and what you promised. |
| **Task system** | Notion, Todoist, Linear, Jira, a markdown file | Intentions, and the shape of what never got done. |
| **Calendar** | An `.ics` export | The single best correction to a chat archive, because it records where time actually went. |
| **Meeting notes and transcripts** | Wherever your notetaker files them | Decisions made verbally, which is where most of them are made. |
| **Finance** | Invoices, an accounting export, a revenue spreadsheet | The least deniable source in the set. Numbers do not perform. |
| **Notes and journals** | Apple Notes, a journal app, a physical notebook you have photographed | Health, mood, relationships, the domains that are otherwise absent. |

**A practical trick for a large chat archive.** Extract only the messages the subject wrote themselves, with timestamps, and drop the assistant's replies. In most archives that cuts the volume by an order of magnitude and removes the biggest contaminant, which is a previous model's interpretation being read back as if it were evidence.

**What makes a good source.** It was written for a purpose other than being analysed, so it is not a performance. It carries timestamps, so patterns can be dated. And it records what was done, not only what was intended.

---

## Sources

<!-- One block per source. Four or five good ones beat fifteen thin ones. -->

### <source name>

- **Where:** <path, repository, export file, database>
- **Covers:** <earliest and latest, as real dates. Check, do not estimate.>
- **Volume:** <messages, files, records, commits: a number a reader can picture>
- **What it records:** <actions, intentions, or both? written by whom?>
- **Known blind spot:** <what this source structurally cannot show>

<!-- Worked example, delete or replace:

### Assistant chat history

- **Where:** ~/.claude/projects/my-work/*.jsonl, extracted to user-messages.txt
- **Covers:** 2026-01-14 to 2026-08-06
- **Volume:** ~1,900 messages I typed myself, 340 sessions
- **What it records:** how I think through problems, in the moment, before deciding
- **Known blind spot:** almost nothing about what I did after the conversation ended

### Invoices

- **Where:** finance/invoices/2026/
- **Covers:** 2026-01 to 2026-07
- **Volume:** 41 invoices
- **What it records:** what clients actually paid for, and when they paid
- **Known blind spot:** nothing about work that never became an invoice

-->

## Known gaps

<!-- What is missing from the whole set, not from one source. This is the section
     people skip and then regret.

     Ask yourself:
       Where do my decisions actually get made? Is that place in the list above?
       What happens in conversations, calls or meetings that leaves no trace?
       Which months have no material, and why?
       Which domain from subject.md has no source covering it at all?

     Examples:
       "Every sales conversation happens on the phone and is not recorded anywhere."
       "March and April are empty; I was on parental leave."
       "Nothing about health is written down anywhere in this set."
       "The co-founder's side of every decision is missing; only my half is here." -->

## Structural bias

<!-- Which way does this collection lean, for anyone, regardless of subject? Name
     the direction. The engine corrects against it in every move, and a bias you
     do not name becomes a finding about you rather than about the source.

     The common ones:
       A chat archive over-represents deliberation and under-represents commitment,
       because people bring open questions to an assistant and go and decide
       somewhere else. Absence of a recorded decision is therefore weak evidence
       of avoidance.
       A CRM over-represents what someone chose to record, and quiet relationships
       vanish.
       A commit log over-represents work that produced files, and makes thinking,
       reviewing and talking look like idleness.
       A calendar over-represents scheduled work and misses everything reactive.
       Sent mail over-represents your outward voice and hides what you decided alone. -->

## Excluded on purpose

<!-- Sources deliberately left out, and why. State the exclusion rather than
     quietly leaving it out, because the corpus note should be able to say that
     something was withheld.

     Usual cases:
       Client-confidential material under NDA.
       Other people's private correspondence.
       A shared inbox where colleagues did not consent to being read.
       Anything you would not want quoted back to you in a document.

     An analysis that quietly reads privileged material is a liability rather than
     a deeper reading. -->
