# Conversations: openers, steering, follow-ups, exits

Shared by `dm` and `inbox`. A LinkedIn conversation is a slow, public-feeling exchange between two professionals.
The job is to earn the next reply, then an outcome, without ever sounding like a sequence. No peer-reviewed study
covers LinkedIn DMs themselves; the rules below transfer from email, InMail, lab and face-to-face research, or are
stated as practice (evidence D-, G-rows).

## The ladder of relationship

Every message sits on one rung. Write for the rung you are on; move up one rung at a time.

| Rung | Situation | What a message may do |
|---|---|---|
| 0 Cold | no connection, no prior exchange | open a conversation on one real, specific hook; ask one easy question |
| 1 Aware | they engaged with you (comment, reaction, reply) or you with them | refer to that exchange; ask one question about their side of it |
| 2 Talking | they replied at least once | answer them, go one step deeper on what they said |
| 3 Earned | they named a need, a tool, a problem you solve, or asked what you do | make one offer, stated plainly, with one way to act on it |
| 4 Committed | they said yes to a next step | confirm logistics; ask the user for times, never invent availability |

With `pitch_before_reply: off` (the default), a message carries an offer only after the person has replied to
the user (`guardrails.md` rule 6). A reply to the user in a comment thread counts, and so does a direct request
for the offer: then answer it plainly. A need they stated in public makes the offer relevant later; on its own it
is not a reply.

## Openers

- **One hook, real and specific.** The best hook is an uncommon thing you share or something they made or said,
  read this session. A common trait ("we're both in SaaS") does nothing. No hook: send a shorter, honest message
  or none.
- **Short.** A cold opener is a few short sentences, well under 400 characters (D2); shorter messages get
  more replies across email, InMail and survey research (W2).
- **Written for one person.** Individually written messages beat templated ones. Templates are allowed as a
  shape, never as text.
- **Easy to answer.** End on one question they can answer in a line from their own experience ("what did you end
  up using for X?"), never a yes/no qualifier or a request for time. Asking for advice or their view works (D4);
  cold asks for interest outperform asks for a time slot in email data (D7).
- **Personalisation you can show.** Use the most specific thing you actually read: nothing, the profile, a recent
  post, a prior thread. Quote one thing, not three; quoting several posts reads as surveillance. A wrong detail is
  worse than none.
- **No flattery.** A specific, true observation about their work is fine; praise as an opener is not.

### Opener types

| Type | Shape |
|---|---|
| Cold | hook sentence tied to them; one question from their world; what you sell stays out while `pitch_before_reply` is `off` (to someone who needs it, "I do X for companies like yours" is the offer); your profile answers who you are |
| After they engaged | "thanks for the comment on X" only if you add something; then a question about their side |
| New connection | greet by first name, glad to be connected, one open question about how things are going for them; nothing about you |
| Warm network (1st degree, known) | a plain hello; a courtesy line is fine here; say what is new with you in one sentence only if it is relevant to them; one question or one offer, not both |
| Role change | congratulate, one sentence tying their background to the new role, one question answerable in a line |
| Connection note | one line, the real reason to connect; or no note when a comment exchange already carries the context |

## Steering

- **Answer first.** When they asked something, the first line answers it concretely. Then continue.
- **Follow up on what they said**, not on their headline. A follow-up question on their last message makes
  people like you more (C2).
- **One idea per message.** One question, one offer, one link. Stacked asks read as a form.
- **Mirror their length and register.** A two-line reply gets a two-line answer.
- **Correct a misunderstanding first**, in one sentence (what it is not, then what it is).
- **Make offers when earned** (rung 3): name their problem in their words, state the offer as a fact, give one way
  to act (a link, "want me to send the docs?"), and leave them free to decline ("no worries if not" said once,
  plainly, is fine; it raises compliance, D6).
- **Disagree receptively.** Acknowledge their point in their terms before yours. When a thread gets heated,
  suggest a call instead of escalating in text.
- **Know when it is done.** A conversation is done when it reached an outcome: a next step, a referral, a clear
  no, or a natural end. A thread that goes quiet after two friendly messages is normal and needs no rescue.

## Follow-ups

- Follow up only on your own unanswered message. The cap:
  - **Cold or unanswered opener**: at most 3 follow-ups (4 messages in total), inside the range vendor data
    supports (D11). Space them wider each time (practice, G2: for example 3 to 5 days, then about a week, then
    about two weeks).
  - **Warm network contact**: 1 follow-up. Two unanswered messages are an answer.
- Each follow-up adds something new: a different angle on the same hook, something useful, or a smaller ask.
  Never "bumping this", "did you see my message", or a copy of the first message.
- The last follow-up offers a clean exit that you state yourself ("I'll take this as bad timing and leave it
  here", D13).
- While your own last message is unanswered (openers and follow-ups), send at most one message per person per
  day, and never a second message to correct the first. Replies in a live conversation are never held back by
  this.

## Reading a reply

| Reply | Next move |
|---|---|
| Interested or asks a question | answer; move one rung up |
| Refers you to someone | thank them; ask how they would like you to mention them |
| "Later" / out of office | stop; resume at the date they gave, or after about 90 days (practice; auto-reply: after their return date) |
| Polite no | one gracious line ("All good, thanks for saying so."), then log a `suppress` line with `until` 90 days out (practice); plan no re-contact: the suppression ends a block, it does not schedule a check-in |
| Hostile or annoyed | no reply; log a `suppress` line with `until` 180 days out (practice) |
| "Stop" / "don't message me" | no reply; log a `suppress` line with `until: permanent`; never contact again from any channel the user runs |
| Pushback ("if this is a pitch, no") | acknowledge in a few words, then continue on their topic with something real, or stop |

## Before any send

Check the log for this person (`log-format.md` § Reading). Each of these stops the send; tell the user why:
- an open suppression;
- the follow-up cap above reached;
- a message sent today that is still unanswered (a reply in a live conversation is not held back);
- another persona of the user who contacted them in the last 90 days (practice).
