# The persona log

`~/.linkedin-plugin/personas/<slug>.log.jsonl`: one JSON object per line, append-only, local. It is how the
skills remember what already happened: who was messaged when, who said no, which posts were commented on.

## Writing

Append one line after every send or hand-off (the moment the user says they posted it, or the
LinkedIn connection in `curviate.md` confirms it).
Never rewrite or delete earlier lines; a correction is a new line.

```json
{"ts":"2026-09-30T09:12:00Z","kind":"dm","to":"https://www.linkedin.com/in/<id>","member_id":"<ACoAA...>","name":"<first last>","thread":"<conversation id or url>","step":"opener","text":"<exact text sent>","approval":"per-item","via":"manual"}
```

| Field | Values |
|---|---|
| `ts` | ISO 8601 UTC |
| `kind` | `post`, `comment`, `reply`, `dm`, `connect`, `reaction`, `outcome`, `suppress` |
| `to` | the person's profile URL, as a vanity URL (`/in/<slug>`) or a member-id URL (`/in/ACoAA...`, the form inbox threads carry); the post URL for `post`/`comment`/`reply`; for `reaction`, the post URL, or the comment URL when the reaction is on a comment |
| `member_id` | optional: the person's member id (`ACoAA...`) when known, so either form of `to` matches |
| `name` | display name, for the user's convenience |
| `thread` | conversation or post id when known |
| `step` | for `dm`: `opener`, `followup-1`, `followup-2`, `followup-3`, `reply`, `offer` |
| `text` | the exact text sent |
| `approval` | `per-item`, `batch`, `autopilot` |
| `via` | `manual` (user pasted it), `curviate`, or `import` (the user's earlier activity, see Seeding) |
| `outcome` | for `kind: outcome`: `replied`, `positive`, `referral`, `later`, `no`, `hostile`, `opt-out`, `meeting` |
| `until` | for `kind: suppress`: ISO date, or `permanent` |
| `note` | free text, one line |

Log business context only: what was sent and what happened. No private details about the person.

## Reading

Before drafting to or about a person or post, read the log for that `to`. A person matches on either form: the
vanity URL, the member-id URL or `member_id`. When only one form is known and Curviate is connected, resolve the
other with `curviate profile <url, slug or member id>` (its result carries both `id` and `public_identifier`)
and write `member_id` on the next line you log.

- A `suppress` line whose `until` is in the future (or `permanent`): do not contact. Tell the user and stop.
- The user's own last `dm` to this person is from today and still unanswered: wait until tomorrow
  (`conversations.md`, "Follow-ups"). A reply in a live conversation is never held back by this.
- The `followup-<n>` lines since their last reply: the cap is in `conversations.md` ("Follow-ups").
- A `comment` on this post already: one comment per post. Offer a reply in the thread instead. Match posts by
  the activity number in the URL, since one post has several URL forms.
- The last `outcome`: sets which rung of `conversations.md` you are on.
- Other personas' logs for the same person: when another persona of the user contacted them in the last 90 days
  (practice), stop the send and tell the user.

## Seeding

A new log knows nothing the user did before it. When a persona's log has no `comment` lines and Curviate is
connected, read the user's own recent comments once (`comment user me`, or reuse comments setup already
pulled) and append one line per comment: `ts` its `date`, `kind` `comment`, `to` its `parent_post.share_url`,
`name` the post's author, `text` the comment, `via` `import`. The one-comment-per-post and same-author checks
then see them. Another persona's log that is still empty leaves the cross-persona check blind: say so once.

## CRM

If the persona names a CRM and that CRM's tools are connected in this session, offer (once) to mirror each
logged touch there as a note or activity on the person. The local log stays the source the skills read.
