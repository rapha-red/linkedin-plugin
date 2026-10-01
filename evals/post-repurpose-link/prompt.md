---
tags: ["post", "repurpose"]
runs: 3
max_turns: 8
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

Turn this excerpt from my blog into a LinkedIn post:

"Why your best candidate said no
https://mayabrandt.example/blog/offer-stage

I tracked every declined offer across my 2025 searches. The pattern was not salary. In most cases the candidate had waited more than a week between the final interview and the offer, and by then a faster company had moved. Speed at the offer stage beats a bigger number more often than hiring managers expect. If you take one thing from this: have the offer approved before the final round starts."
