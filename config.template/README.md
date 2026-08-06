# LEDGER configuration · template

Copy this directory to `config/`. **Two files to fill in, one that already works.** Budget an hour, once.

The engine (`../SKILL.md`) never contains your subject, your sources or your voice, and this directory never leaves your machine. That split is the design: you can pull engine updates forever without touching any of it, and contribute engine improvements without leaking it.

- `subject.md` · who or what is being read, and which domains count. **You write this.**
- `corpus.md` · which sources may be read, where they are, what is known to be missing. **You write this.**
- `voice.md` · how the findings must read. **Ships filled in and runs as it stands**, with runnable checks for the usual machine tells. Adjust the reading level to your taste, add your own rules over time.

Pointers beat copies: if you already keep a style document or a data inventory, reference it here instead of duplicating it.

**One rule the config cannot override.** The engine forbids clinical labels, diagnosis of the subject or of people they describe, and any claim that outruns its evidence. A config may make the output blunter. It may not make it less honest.
