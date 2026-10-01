# Persona file

A persona is one voice the user writes in on LinkedIn: themselves, a second account they run, a founder they
ghostwrite for. `setup` creates and edits these files; every drafting skill reads one before writing.

## Where it lives

`~/.linkedin-plugin/personas/<slug>.md`, one file per persona, with its log next to it
(`<slug>.log.jsonl`, see `log-format.md`) and, if the user keeps plans, `<slug>.plans.md` (written by
`linkedin-plan`). Outside any repo and outside the plugin, so updates never touch it.

- Persona files are the `*.md` files in that folder except `*.plans.md`. One persona file: use it without asking.
- Several: use the one the user names; otherwise ask once per session which one.
- None: offer `setup` once, then continue with the neutral defaults in `voice.md`.
- Apps without a local filesystem (claude.ai on the web): the persona is kept as a Project knowledge file or
  pasted at the start of the chat, and the log is off. Say so when it applies.

## Template

Write the file in this shape. Keep the user's own words wherever they gave them.

```markdown
---
persona: <slug>
name: <display name>
updated: <YYYY-MM-DD>
language: <default language, e.g. en>
approval: per-item            # per-item | batch | autopilot
pitch_before_reply: off       # off (default) | on
crm: none                     # none | <name of the CRM they use>
timezone: <IANA zone, e.g. Europe/Berlin>
hours: 08:00-22:00            # when sends may go out
samples: <n posts, n comments, n DMs kept; pasted | fetched>
---

## Who
Role, company, what they do, for whom, in their words. One short paragraph.

## Audience
Who they want to reach on LinkedIn and why. Titles, industries, situations.

## Offer
What they sell or want (clients, hires, a job, reputation), and when it is fair to mention it.
Affiliations: products or companies the persona is affiliated with (employer, own product, client). Any mention
discloses the affiliation.

## Voice
How they actually write, taken from the samples:
- sentence length and rhythm
- formality, du/Sie or equivalent, contractions
- how they open and close
- humour, if any, and of what kind
- words and phrases they use often (keep)
- words and phrases they never use (ban)
- formatting habits (emoji, line breaks, hashtags, lists)
Two or three short verbatim sample lines that sound most like them.

## Story bank
Facts they are happy to use, each one line:
- Timeline: roles, companies, years
- Results with numbers, with what the number measures
- Things they built, shipped, changed
- Turning points, mistakes, what they learned
- Positions they hold, including unpopular ones
- Names: may use / never use / ask first

## Off limits
Topics, names, clients and numbers never to use. Anything they declined to share.

## Pacing and preferences
Anything they said about how often they post, comment or message, days they are offline, topics to lead with.
```

## Rules for filling it

- `linkedin-setup` owns the file. Other skills may append a fact to the story bank or off-limits list only after
  the user confirms it, and say that they did.
- Only what the user said or what their samples show. Leave a section as `(empty)` rather than guessing.
- The voice section is descriptive (how they write), not aspirational (how they would like to write). If they
  want a change, note it as a preference.
- No personal data beyond what is needed to write as them: no home address, family details they did not offer,
  health, or anything about other people beyond names they cleared.
