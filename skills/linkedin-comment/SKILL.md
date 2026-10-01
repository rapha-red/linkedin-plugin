---
name: linkedin-comment
description: "Comment on someone else's LinkedIn post, reshare a post with commentary, or find posts worth commenting on. Use when the user pastes a post or its URL and wants a comment or a repost with their take, or asks where to comment today. Drafts 1 to 3 variants plus a reaction in the persona's voice and checks the log so no post gets a second comment. Not for answering comments on the user's own post or replies to their comments (use linkedin-reply)."
---

# Comment

A comment is a turn in someone else's conversation. It earns its place by adding one thing the post and the
comments above it do not have (C1). Three modes: **draft**, **reshare**, **find**. Find ends in draft.

## Before any mode

1. **Persona.** Load it per `../linkedin/references/persona-template.md` ("Where it lives"). Done when you
   know the persona (or that none exists and the neutral defaults apply) and have read its Voice, Story bank,
   Off limits and Offer sections.
2. **Log.** Read the persona's log per `../linkedin/references/log-format.md` ("Reading"); a log with no
   comment history gets seeded first ("Seeding"). Done when you know, for every candidate post: whether this
   persona or another of the user's personas already commented on it, and which authors this persona commented
   on today.

## Draft

For a post the user pasted, linked or picked in find.

1. **Context.** Read the whole post and its top comments (`../linkedin/references/guardrails.md` rule 1); with
   only a URL and no Curviate, ask for a paste and offer the fetch once (`../linkedin/references/curviate.md`).
   Done when you have the post text and the top comments, or the user said there are none.
2. **Stop checks.** Stop and tell the user when: the log shows a comment on this post already (offer a reply
   in that thread via `linkedin-reply` instead), or another persona of the user is already in this thread (two
   of one person's accounts in one thread reads as a pod, R6, R13). A second angle on a post you already
   commented on becomes a reaction, not a second comment. When the persona already commented on this author today,
   say so and suggest a reaction or waiting a day (one author a day, see `references/choosing-posts.md`).
3. **Pick the angle.** Name the one thing the post and its comments are missing, then choose the angle type
   that delivers it. Done when you can say the addition in one line and it traces to the persona's story bank,
   the post itself, or something the user said this session (guardrails rule 2). When the persona has nothing
   real to add, say so and suggest a reaction only.

   | Angle | Use when | Shape |
   |---|---|---|
   | Missing piece | the post is right but leaves out a condition, cost or step the persona has seen | name the piece, then the case where it decides the outcome |
   | Answer their question | the post ends on a real question | answer first in one sentence, then one concrete example |
   | Example from experience | the persona has a number, case or result on this exact topic | the specific thing, what it measured, what it changed (W4) |
   | Counter with concession | the persona disagrees with part of it | grant the point that holds in their terms, then the narrow disagreement and its reason, hedged as the persona's view (C3) |
   | Sharper question | the post leaves its hardest part open | one question about what the author actually said, that the persona wants answered (C2) |

4. **Write 1 to 3 variants**, each a different angle when more than one fits, each 2 to 4 sentences: count
   them before the card. Shape per `../linkedin/references/voice.md` ("Per-surface shape", Comment): a reply in
   a conversation, first person, opening on their claim with the persona's take. Close on a take or a real
   question. Address the author by first name only when the persona does. A run of five or more words from the
   persona's recent comments in the log gets rewritten. Within one batch, each story-bank fact or anecdote is
   used at most once, and variants of one post use different material.
5. **Own offer.** By default the comment leaves out the persona's offer and affiliations (persona "Offer"). A
   mention fits when the persona's "when it is fair to mention" allows it, the thread is about the problem or
   the category of tools the offer belongs to, and the offer genuinely answers what is being discussed. Then
   one plain sentence, no link, disclosed as the persona's own or as an affiliation ("I built X", "I work with
   X"). Undisclosed praise of an affiliated offer is what R16 and the persona's credibility both rule out.
6. **Reaction.** Pick one reaction that fits the post: Insightful for an idea the persona learned from,
   Support for a hard moment, Celebrate for news or a win, Love for something personal and warm, Funny only for
   intended humour, Like otherwise. A reaction alone is the right call when there is nothing to add.
7. **Guardrails.** Run `../linkedin/references/guardrails.md` over every variant (it runs `../linkedin/references/voice.md`). Done
   when every variant passes every rule and the language matches the post (rule 4).
8. **Approval card.** One card per rule 7, the variants numbered, each with its angle and a "why" line, the
   reaction on its own line. The user picks a variant or edits.
9. **Send or hand off.** With Curviate connected, react, then comment, one write at a time (guardrails rule 8,
   `../linkedin/references/curviate.md` "Sending through it"). Otherwise the card is the hand-off. On
   `autopilot` (preconditions in `../linkedin/references/curviate.md` "Autopilot"), say once per session before
   the first unattended comment that LinkedIn prohibits automated commenting and hides such comments (R10),
   the riskiest use of autopilot; then continue as the persona chose.
10. **Log.** After the send or the user's "posted", append a `comment` line (`to`: post URL, `name`: the
    post's author, `text`: the exact comment) and a `reaction` line. Done when both lines are written.

## Reshare

For "repost this", "share this with my network", "reshare with my take".

1. Read the post (draft step 1) and check the log for an earlier reshare of it.
2. Ask whether the user wants commentary. A plain repost is a valid choice; skip to step 4.
3. Draft the commentary: one to three sentences on why this is worth the reader's time, carrying the
   persona's own angle or experience (H10), never a summary of the post. The author is tagged only when the
   persona wants them notified (R22). Run guardrails.
4. Approval card with the post URL and the commentary (or "plain repost").
5. Hand-off: the user uses LinkedIn's "Repost" (with or without thoughts). When LinkedIn shows no repost option,
   the author turned resharing off; tell the user. Send through Curviate only if its CLI lists a repost command
   (`curviate post --help`).
6. Log a `post` line with `note: "reshare of <post URL>"` and the commentary as `text`.

## Find

For "where should I comment today", "find posts on X", or a list of candidate posts.

1. **Gather candidates.** Outside the persona's `hours`, say first that approved comments wait for the next
   window while the posts age, and offer to search then instead. With Curviate connected (reads per
   `../linkedin/references/curviate.md`): `search posts --verbose` on phrases the persona's audience actually
   uses (practitioner wording, not bare platform terms) and `feed home`, dropping items without text.
   Otherwise ask the user to paste candidates (URL plus text), and offer Curviate once. Done when you have at
   least a handful of candidates or the user's full list.
2. **Qualify.** Apply `references/choosing-posts.md` (read budget included) to each candidate, reading about 10
   comments on each one that survives the first cuts. Done when every candidate is marked keep or skip with a
   reason.
3. **Shortlist.** Show a table: author, post (first line), age, comment count, audience fit, suggested angle,
   and the skip reasons as counts ("9 found: 3 kept, 2 lead magnets, 1 job post, 2 already commented, 1 same
   author as yesterday"). The user picks; when they already asked for drafts, take the top 2 or 3 keepers.
4. **Draft** each picked post with the Draft mode, one comment per post, the cards below the table.

## After a good run

Follow `../linkedin/SKILL.md` "After a good run".
