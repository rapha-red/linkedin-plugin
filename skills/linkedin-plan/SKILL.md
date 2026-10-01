---
name: linkedin-plan
description: "Plan a LinkedIn week, review the last one, or run a team's advocacy program. Use for \"what should I post this week\" (weekly plan of posts, comments, DMs and inbox time), \"how did last week go\" (review from the log), or getting a team or company's employees posting (team mode). Not for drafting the posts themselves (use linkedin-post)."
---

# LinkedIn plan

A plan decides what the user spends their LinkedIn time on this week: which posts, whose conversations to join,
which messages to answer. It is built from the persona's story bank and the log, sized to the time the user has.

Evidence stance for every plan: there is no causal evidence on how posting frequency, days, times, hashtags or
formats change reach (G1; M2, M7, M8, M9, M21). Plans set a rhythm the user can keep and choose formats by what
the material needs. When the user asks for a best time or a magic number, say that plainly and cite the IDs. A suggested
day or time rests on when the user can stay to answer comments (G3), never on when the audience is online.

## Weekly plan

1. **Read.** Load the persona (`../linkedin/references/persona-template.md`) and the last four weeks of the log
   (`../linkedin/references/log-format.md`): posts made, comments made, open conversations, follow-ups due,
   suppressions. With no log (claude.ai web or a new persona), ask what they posted recently.

2. **Ask what is missing**, one question at a time, only what the persona and log do not answer:
   - the one goal for this week (for example: start conversations with a type of buyer, find candidates, be known
     for a topic);
   - how much time they have for LinkedIn this week, in hours;
   - anything happening (a launch, an event, travel, a result they can talk about).
   Done when goal, hours and events are known.

3. **Pillars.** Derive two to four themes from the persona's Audience, Offer and story bank, each tied to
   what the audience wants to learn from this person (P1). Reuse last week's pillars unless the goal changed.

4. **Posts.** Pick a number the hours allow and the user says they can keep up for more than a week. For each:
   - pillar and one-line angle, drawn from a named story bank entry or a source the user gave (P1, P2); an angle
     with no material behind it becomes a question to the user, listed under "Needed from you";
   - format chosen by the material (text for an argument, an image or document when there is something to show,
     a poll only for a real question), never for assumed reach (M9);
   - what the post asks of the reader, if anything: a real question about the topic, never a comment prompt (P10);
   - the day, placed where the user has time to answer comments that day (G3: reply because the conversation is
     the point).
   Check the log: no angle repeats a recent post. Spread the week across pillars, and put the offer in a post
   only when there is real news or proof, as often as the persona's Offer section says is fair.

5. **Comments.** Name whose posts to join: people the audience follows, peers, and people in the audience itself,
   by name where the user knows them, otherwise by description and search terms. Size it by the hours left
   after posts; every comment needs a real addition (C1), so a few good ones beat a quota. LinkedIn may limit and
   hide excessive commenting (R9), and automated comments are not allowed (R10). Finding the posts:
   `linkedin-comment` (find mode). One comment per post per persona; the log shows what was already done.

6. **Conversations.** Block time for the inbox (`linkedin-inbox`), list follow-ups due this week from the log per
   `../linkedin/references/conversations.md` § Follow-ups, and name last week's posts whose engagers are worth a
   message (`linkedin-dm`, warm leads).

7. **Sample lines.** If the plan shows a hook or example line, it is a draft: run
   `../linkedin/references/guardrails.md` on it.

8. **Show the plan** in the shape below and adjust on feedback. Offer to append it to
   `~/.linkedin-plugin/personas/<slug>.plans.md` so next week's review can compare plan and log. Done when the
   user accepted the plan and every post angle names its source or sits under "Needed from you".

```
Week of <date>, persona <slug>, goal: <goal>, time: <hours>

Posts
Day   Pillar      Format   Angle (source)                          Asks the reader
...

Comments: <whose posts, how to find them, how many the time allows>
Conversations: inbox <when>; follow-ups due: <names, step>; warm leads from: <post>
Needed from you: <questions>
```

## Review of last week

1. Read the log for the period (default: the last seven days) and the saved plan for that week if there is one.
2. Count, per kind: posts, comments, replies, DMs by step (opener, follow-up, offer), and outcomes (replied,
   positive, meeting, referral, no, opt-out). Compare with the plan: what was planned and not done.
3. Ask whether they want reach in the review. If yes, they paste the numbers from LinkedIn's post analytics
   (impressions, reactions, comments per post); the log does not hold them.
4. Report what got replies: which openers, comments and posts led to answers or outcomes, with the count behind
   each. With a handful of items, say it is too few to conclude and treat it as a lead to test, never a rule.
5. Recommend: what to repeat, what to drop, follow-ups due, threads to revisit (`linkedin-reply`), a comment that
   drew a real discussion and could become a post (`linkedin-post`). Done when every logged item of the period is
   counted and every recommendation names the items it rests on. Offer to plan the next week.

## Team mode

For a company or team that wants several people posting as themselves (employee advocacy). Steps and rules:
`references/team.md`. Each person's own posts then use the weekly plan above with their own persona.

## After a good run

See `../linkedin/SKILL.md` § After a good run.
