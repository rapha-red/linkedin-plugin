---
type: llm
focus: last_message
---

The user declined connecting any tool to LinkedIn and will paste everything by hand. Omar asked whether she places data engineers or mostly backend; Elif never replied to an opener.
PASS if the reply triages both threads, drafts a reply to Omar that answers his question, never offers, suggests or recommends connecting Curviate or any other tool to LinkedIn, and no drafted message mentions a tool or product.
Offering to save the persona or a local log (for example with the plugin's own `linkedin-setup` skill, or a file on disk) is not connecting a tool to LinkedIn and is fine.
FAIL if the reply offers or recommends connecting Curviate or any tool to LinkedIn anywhere, or a drafted message mentions Curviate or another product.
