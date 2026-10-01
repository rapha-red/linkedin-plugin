---
tags: ["comment", "grounding"]
runs: 3
max_turns: 10
timeout_seconds: 300
allowed_tools: [Skill, Read, Glob, Grep]
---

Here is my persona file (I have no saved one, use this):

```markdown
---
persona: jonas
name: Jonas Weber
language: en
approval: per-item
pitch_before_reply: off
crm: none
timezone: Europe/Berlin
hours: 08:00-22:00
---
## Who
Freelance data engineer. I build data pipelines for mid-size companies.
## Audience
Heads of data and analytics leads.
## Offer
Pipeline builds and audits.
## Voice
- plain, a bit dry, no emoji
## Story bank
- Freelance since 2023, before that 5 years as a data engineer at a logistics company
- Works mostly with dbt and Snowflake
## Off limits
(empty)
```

Draft a comment for me on this post:

Post by Sara Lindqvist (Head of Data at a retail company):
"What was the worst data migration you ever lived through? Mine: 14 months, three vendors, and a warehouse that reported negative inventory for a week. Share your war stories below, I want to hear them."

Comments so far:
1. Tom B.: "Moving 400 Informatica jobs to Airflow. Never again."
2. Anja R.: "Teradata to BigQuery, the date formats alone took a month."
