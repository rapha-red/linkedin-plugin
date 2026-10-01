---
tags: ["plan", "review"]
runs: 3
max_turns: 10
timeout_seconds: 300
allowed_tools: [Skill, Read, Glob, Grep]
---

Here is my persona file (I have no saved one, use this):

```markdown
---
persona: maya
name: Maya Brandt
language: en
approval: per-item
pitch_before_reply: off
crm: none
timezone: America/Chicago
hours: 08:00-22:00
---
## Who
Independent B2B tech recruiter. I place backend and data engineers at Series A to C SaaS companies in the US Midwest.
## Audience
Engineering managers and CTOs at 20 to 200 person SaaS companies.
## Offer
Contingency search for senior engineers. Fair to mention once a hiring manager says they are hiring.
## Voice
- short sentences, contractions, no emoji, no hashtags
- opens with the point, closes with a plain question
- never uses: "reach out", "synergy", "rockstar"
Sample line: "Most of my searches stall at the offer, not the pipeline."
## Story bank
- 9 years recruiting, the last 4 on my own
- Placed 31 engineers in 2025, median time to offer 34 days
- Learned the hard way that a take-home over 3 hours loses the best candidates (lost 2 finalists to it in 2024)
- Names: never name clients
## Off limits
Client names, fee percentages.
```

How did last week go? Here is my log for the week, then plan next week based on it.

```
{"ts":"2026-09-21T14:00:00Z","kind":"post","to":"https://linkedin.example/feed/update/urn:li:activity:1000000000000000001/","text":"A take-home over 3 hours loses your best candidates. I lost 2 finalists to one in 2024."}
{"ts":"2026-09-21T16:10:00Z","kind":"reply","to":"https://linkedin.example/feed/update/urn:li:activity:1000000000000000001/","name":"Devin Pratt","text":"A 90-minute cap sounds right to me. Past 3 hours is where I started losing finalists."}
{"ts":"2026-09-21T17:30:00Z","kind":"reply","to":"https://linkedin.example/feed/update/urn:li:activity:1000000000000000001/","name":"Kim Laine","text":"Paying for it helps. Length still decides who finishes."}
{"ts":"2026-09-22T09:40:00Z","kind":"comment","to":"https://linkedin.example/feed/update/urn:li:activity:1000000000000000011/","name":"Omar Haddad","text":"The loop length matters less than the gap before the offer."}
{"ts":"2026-09-22T10:05:00Z","kind":"comment","to":"https://linkedin.example/feed/update/urn:li:activity:1000000000000000012/","name":"Lena Fisher","text":"Referrals dry up once a team stops growing. Then the offer stage matters even more."}
{"ts":"2026-09-23T13:00:00Z","kind":"dm","to":"https://linkedin.example/in/devin-pratt-example","name":"Devin Pratt","step":"opener","text":"Hi Devin, the 90-minute cap stuck with me. Did it change who finishes the process?"}
{"ts":"2026-09-23T13:30:00Z","kind":"dm","to":"https://linkedin.example/in/sara-lind-example","name":"Sara Lind","step":"opener","text":"Hi Sara, saw you are hiring two data engineers. How is the search going?"}
{"ts":"2026-09-24T08:15:00Z","kind":"outcome","to":"https://linkedin.example/in/devin-pratt-example","name":"Devin Pratt","outcome":"replied"}
{"ts":"2026-09-24T10:00:00Z","kind":"post","to":"https://linkedin.example/feed/update/urn:li:activity:1000000000000000002/","text":"Most of my searches stall at the offer, not the pipeline."}
{"ts":"2026-09-25T11:00:00Z","kind":"dm","to":"https://linkedin.example/in/jon-berg-example","name":"Jon Berg","step":"opener","text":"Hi Jon, your post on on-call rotations for data teams: what finally made it fair?"}
```

I have about 3 hours again next week.
