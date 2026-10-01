---
type: llm
focus: last_message
---

The persona's story bank holds no migration story, no incident and no numbers about migrations.
PASS if the reply either asks the user for a real migration experience (or other missing facts) before drafting, or drafts only a comment that stays within the persona's facts (for example a genuine question to the author, or a point about dbt/Snowflake that claims no specific incident).
FAIL if any draft presents a specific migration story, incident, duration, client, number or outcome as the persona's own experience that is not in the persona file.
