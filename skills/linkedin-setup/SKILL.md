---
name: linkedin-setup
description: "Create, edit or switch the persona every linkedin-* skill writes as (voice, story bank, approval level, `pitch_before_reply`, CRM, language). Use for first-time setup or \"learn my voice\" (quick setup), \"interview me\" to fill the story bank, changing approval level or another setting, refreshing the voice from newer posts, or adding and switching personas. Not for turning an interview into a post (use linkedin-post)."
---

# LinkedIn setup

Builds and maintains `~/.linkedin-plugin/personas/<slug>.md`. The file's shape, location and filling rules are in
`../linkedin/references/persona-template.md`; read it first and follow it exactly. This skill decides what goes in.

## Before any mode

1. List the persona files: `~/.linkedin-plugin/personas/*.md` except `*.plans.md`. No persona: run Quick setup. One: the mode works on it. Several: ask which.
2. **No filesystem** (claude.ai on the web, or any app without file access): run the mode as normal, then give the
   whole file as one Markdown block and tell the user to add it to their Project knowledge (or paste it at the
   start of a chat). Say that the log is off in this app.
3. **Show before saving.** Every mode ends by showing the new file, or for an edit only the changed lines as
   before and after, and saving on an explicit yes. Set `updated:` to today.

Throughout: one question per message, the user's own words kept verbatim where they are vivid, and nothing
written that the user did not say or their samples do not show. A section with nothing in it stays `(empty)`.

## Quick setup

About ten minutes; leaves a usable persona with a first-pass voice.

1. **Essentials.** Ask, one at a time, only what is not yet known: whose account this is (sets the slug and
   `name`), what they do and for whom, who they want to reach on LinkedIn, what they want from it (clients, hires,
   a job, reputation), when it is fair to mention that, their affiliations, their default language. Wording:
   `references/interview.md` § Essentials. Done when Who, Audience and Offer each hold one real answer.
2. **Samples.** Ask for 5 to 10 texts they wrote themselves, mixed across surfaces where possible (posts,
   comments, DMs). This is a Curviate moment (`../linkedin/references/curviate.md`, "setup samples"). Pulling
   runs only after the user says yes to a list of exactly what will be read (recent posts, comments, DMs, how
   many) and to seeding the log from the comments (`../linkedin/references/log-format.md` "Seeding"). From DMs,
   keep only the user's own lines. List the samples (first line each) and let the user strike any they did not
   write or do not consider their voice; a text drafted by an assistant or a colleague counts only if the user
   says it is their voice.
3. **Fingerprint.** Fill the Voice section from the samples, dimension by dimension as the template lists them.
   Record a habit only when it shows in at least two samples. Copy two or three short lines that sound most like
   them. Where their samples repeat a word from the tell list in `../linkedin/references/voice.md`, ask whether
   to keep it and record the answer under keep or ban. Where their samples use em dashes, tell them drafts will
   still use commas, colons or parentheses (a hard rule in `../linkedin/references/voice.md`).
4. **Settings.** Ask their timezone, then state the defaults (per-item approval, `pitch_before_reply: off` so no pitch before a reply, no CRM, sends only 08:00
   to 22:00 in that timezone) in one message and ask whether
   to change any. A change runs the Settings mode.
5. **Save.** Set `samples:` (counts per surface kept after striking, pasted or fetched). Show, save, then say
   how many samples it rests on, that it sharpens with more, and which sections are still `(empty)`. Offer the
   Story bank interview as the next step. Done when the file is saved and the user saw it.

## Story bank interview

Deep and resumable: fills Story bank and Off limits. The material every drafting skill draws facts from.
Question bank and the hard moments: `references/interview.md`.

1. **Resume.** Read the persona. Interview only the story bank lines that are `(empty)` or thin; never re-ask
   what is answered.
2. **Open wide.** One broad question about what they are working on or cannot stop thinking about, then follow
   what they get animated about. The section list is the checklist for the end, not the order of questions.
3. **Press a vague answer once.** "Recently", "a lot", "a big client", "we improved it": ask once for the month,
   the number and what it measures, or whether it can be named. Take the second answer as it comes, even if it is
   still vague, and record it as said.
4. **Go for the moments that carry posts:** what they believed a year ago and no longer do, their most expensive
   mistake, a view their peers disagree with and what holding it costs, the stories they already tell in person.
5. **Settle names and limits directly.** For every client, employer, colleague or number mentioned, ask: may use,
   never use, or ask first. Never infer it.
6. **"Rather not say" ends that line.** Record the topic under Off limits, tell the user it is recorded, and move
   on. Nothing asks about it again.
7. **Save as you go.** After each finished section, show the new lines and write them, so a stop at any point
   loses nothing. A profile, CV or scraped page can suggest questions; only the user's answers and first-person
   facts from their kept samples (noted with the sample's date) fill the bank.
8. **Close with what it unlocks.** Name two or three posts the new material could carry (hand-off:
   `linkedin-post`). Done when the user stops or every story bank line holds an answer or a recorded refusal.

## Settings

Change one setting at a time and show the frontmatter line before and after.

**Approval level.** Explain all three with their risk in plain words before the user picks:

| Level | What happens | Risk |
|---|---|---|
| `per-item` (default) | every post, comment and message shown and approved on its own | lowest: nothing goes out unread |
| `batch` | all drafts on one card, one approval, any item can be struck | a line you did not read closely goes out under your name |
| `autopilot` | sends without review | automated activity is against LinkedIn's rules and can get the account restricted (R14, R15); content goes out that no human read, and you remain responsible for it (R18) |

Autopilot needs Curviate connected with its safety settings as `../linkedin/references/curviate.md` § Autopilot
requires. Without them, offer `batch` and say why.

**Pitch before a reply** (`pitch_before_reply`). `off` (default): no offer, product, link or call request in a message
before the other person has replied. `on` allows an offer in a first message. Before switching it on, tell them
two things: no study shows pitching early works better (M17), and in the EU, especially Germany, promotional
messages without prior consent carry legal risk (L1 to L4; not legal advice).

**CRM.** Ask whether they keep contacts in a CRM and which one. Record the name in `crm:`. If that CRM's tools are
connected in this session, say that touches can be mirrored there (`../linkedin/references/log-format.md` § CRM).

**Language.** The default language for new posts and first messages. For German, record du or Sie as their
default (see `../linkedin/references/voice.md` § Language notes). Answers always follow the conversation's language regardless.

**Timezone and hours.** `timezone` (IANA name) and `hours` (default `08:00-22:00`): sends go out only inside
these hours (`../linkedin/references/guardrails.md` rule 8). Ask for a narrower window if they keep one.

## Refresh voice

1. Take newer samples (pasted, or pulled through Curviate if it is already connected and the user agrees),
   with the strike step from Quick setup step 2.
2. Compare them with the current Voice section. Propose only changes seen in at least two new samples; keep every
   quirk the new samples do not contradict. A change the user wants that the samples do not show goes under
   Pacing and preferences, not Voice.
3. Show the changed lines before and after, update `samples:` and `updated:`, save on yes.

## Add or switch persona

- **Switch:** list the personas by `name` and slug; the one picked is used for the rest of the session.
- **Add:** run Quick setup with a new slug. Each persona keeps its own log; say that other skills warn when two
  personas approach the same person.
- **Team members** each get their own persona in their own words (see `linkedin-plan`, team mode).

## After a good run

See `../linkedin/SKILL.md` § After a good run.
