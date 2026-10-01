---
name: linkedin-post
description: "Write a LinkedIn post in the user's voice, grounded in their own stories. Modes: from an idea or topic (angle options, the user picks, then a draft); interview me (questions one at a time until there is a post); repurpose a blog, talk, video transcript, thread or newsletter into a native post; reuse the structure or hook of a post the user liked (skeleton plus their own draft). Posts on approval or hands the text off. Not for polishing or auditing a draft that already exists (use linkedin-humanize)."
---

# LinkedIn post

One post, one idea, in the user's voice, built only from material they gave you. Four ways in, one way out:
every mode ends in **Finish**.

## Start (every mode)

1. Load the persona as `../linkedin/references/persona-template.md` describes. Its story bank is your only
   source of facts besides what the user says or pastes this session.
2. Read the last posts in the persona's log (`../linkedin/references/log-format.md`), so a new post does not
   repeat a recent angle.
3. Pick the mode from the request. Unclear: ask which of the four fits, in one line.

Done when the persona (or the neutral default) is loaded and the mode is set.

## What makes the post

These apply in every mode. Evidence IDs point to `../linkedin/references/evidence.md`.

- **One idea.** If the material holds two, write one and list the other as a one-line idea for later.
- **Point where the reader decides to stay**: the first line or two say the thing (P9).
- **From the user's own work**: knowledge, a decision, a result, a mistake (P1). Their angle, not the
  consensus take (H10, H5).
- **A story beats a summary** when there is one: a scene, a person, what happened (P2). Failures stated
  plainly (P3); wins stated straight, never humblebragged (P4).
- **A sharp, specific claim**, never outrage or negativity used as bait (P6).
- **Specific over general**: the named tool, the number with what it measures, the month (W4). A precise
  number only when the user has it (W5).
- **Invite a real response** or just stop; no "comment YES" or "agree?" (P10, R6).
- **Tag only** people or companies who are part of the post (R22).
- Length: as long as the idea needs and no longer (W2); short paragraphs for scanners (W6). The user's
  requested length wins.

Posting times, hashtag counts, link penalties and "see more" cutoffs are unproven (M1, M2, M7, M8, M19). Give
no advice on them; if asked, answer from the row with its grade.

Opening moves, body shapes and closes, as patterns with what each is good for:
`references/post-patterns.md`. Load it before choosing a structure in any mode.

## Mode: from an idea

1. Take the idea or topic. Find the story-bank facts that bear on it.
2. Offer 2 or 3 angles, one line each: the point, the opening move and body shape, the fact it rests on.
   Angles differ in the point they make, not only in wording.
3. The user picks or edits one. When no angle has a fact to stand on, say so and switch to **interview me**
   instead of drafting on air.
4. Draft in the chosen pattern. Go to **Finish**.

Done when the user has picked an angle and a draft exists that uses only facts traced in step 1 or given since.

## Mode: interview me

For when the user has a topic but no material, or asks to be interviewed. The questions are in
`references/interview.md`; load it now.

1. Ask one question at a time, 5 to 8 in all. Ask for a moment, not a category.
2. Press a vague answer once ("by how much?", "which month?", "can I name them?"), then accept what comes and
   move on.
3. "Rather not say" ends that line. Keep it out of the post, offer to record it under Off limits (`../linkedin/references/guardrails.md` rule 2), and never ask again.
4. Read back the **spine** in five short lines: the point, the moment, the detail that proves it, what it
   cost or changed, the close. The user corrects it; keep their correction in their words.
5. Draft from the corrected spine only. Go to **Finish**.
6. New facts that surfaced: offer to add them to the persona's story bank, and write only the ones the user
   confirms.

Done when the user has confirmed the spine. Never fill a gap with a plausible answer.

## Mode: repurpose

The source keeps its meaning and facts; the delivery is rebuilt for a feed post.

1. Get the source: pasted text, a transcript, or a URL read with the agent's own fetch tool when it has one.
   A video or talk needs a transcript or the user's notes; ask for it. LinkedIn content comes by paste (or
   Curviate, if already connected).
2. Find the spine: the one claim, story or number worth a post. A long source holds several; draft one and
   list the others as one-line ideas.
3. Rebuild per source:

| Source | Rebuild |
|---|---|
| Blog post, article, newsletter | the single strongest claim first, then the one story or example that proves it; no summary of the whole piece |
| Talk, podcast, video transcript | the payoff first, then how the speaker got there; spoken filler, timestamps and "as I said" out; keep the speaker's vivid phrases |
| Thread (X, Threads, Bluesky) | unroll into continuous prose; the best line becomes the opening; handles, numbering and "1/" markers out |
| The user's own comment that drew replies | the comment's point, expanded with the example it only hinted at |
| Someone else's piece | a reaction: their idea in one line with credit, then the user's own extension, disagreement or experience |

4. Strip the source platform's shell: hashtag walls, "link in bio", subscribe asks, "originally posted on".
   Keep the main link, placed per **Finish**; drop the rest.
5. Draft. Keep every number, name and claim as the source has it; add nothing the source or persona lacks.
   Go to **Finish**.

Done when every fact in the draft is traceable to the source or the persona.

## Mode: reuse a structure

The user liked a post and wants its shape for their own content. Take the function, never the words.

1. Get the post text by paste (or Curviate, if already connected). Ask what they liked about it.
2. Analyse it with `references/post-patterns.md`: opening move, body shape, close, the devices it relies on
   (a number, a scene, a named thing, a list), its paragraphing and rough length. Name any tells from
   `../linkedin/references/voice.md` the source uses, so the skeleton leaves them out.
3. Write the **skeleton**: one line per beat, each a slot in angle brackets that says what goes there, with
   no words from the source.

```
<opening move: the moment you changed your mind, with its date>
<what you believed before, one sentence>
<the event that changed it: what happened, one concrete detail>
<what you do now>
<close: a real question about the reader's version of this>
```

4. Fill the skeleton with the user's own topic from the story bank, or ask for the missing slots one at a
   time. Go to **Finish**. Show the skeleton above the draft so they can reuse it.

Done when the skeleton carries no source wording and every slot in the draft is filled from the user.

## Finish (every mode)

1. **Guardrails.** Run `../linkedin/references/guardrails.md` on the draft. Its voice check (rule 3) is the
   rewrite procedure of `../linkedin-humanize/SKILL.md`.
2. **Links.** When the post points to a link, ask where it goes: in the body, or in a one-line first comment
   so the post reads whole before anyone leaves it. Either is fine; no placement has a proven reach effect (M1).
   When there is no link, skip.
3. **Approval card**, per `../linkedin/references/guardrails.md` rule 7:

```
[1] Post     language: EN     <n> characters
    <exact text>
    first comment: <exact text, or "none">
    why: <mode, opening move and body shape, the story-bank fact it rests on>
```

4. **Send or hand off.** Send only after approval at the persona's level. With Curviate connected, post it,
   read it back, then add the first comment on the live post (`../linkedin/references/curviate.md`, "Sending
   through it"). Without it, the card is the hand-off: the user posts it and pastes the first comment
   themselves. The approval moment is the one to offer Curviate, following `../linkedin/references/curviate.md`'s etiquette.
5. **Log.** After the send, or once the user says it is posted, append a `post` line (and a `comment` line for
   the first comment) per `../linkedin/references/log-format.md`.
6. After a run the user was happy with, see `../linkedin/SKILL.md`, "After a good run".

Done when the text went out or was handed off, and the log has its line.
