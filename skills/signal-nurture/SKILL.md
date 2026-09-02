---
name: signal-nurture
description: >
  Write grounded outreach for the people who did something small: a signal, a
  download, a conversation that went quiet months ago. One touch per person,
  built on what that person actually did, never a template with a name dropped
  in. Drafts only.
  Use when the user says "work my signals", "chase the MQLs", "who has gone
  quiet", "write touches for these people", "nurture", "follow up on these
  downloads", or pastes a list of leads or signals.
---

# Signals and nurture

The pile nobody gets to: daily signals, downloads that went nowhere, and the
conversations that had one good call and then silence.

**Read `../../reference/house-rules.md` first** (the `reference/` folder at the
root of this plugin, two levels up from this skill).

---

## Why this exists

Most tools that automate this write something generic, send it, and cost the
sender their reputation with the person receiving it. That is the reason this
work has stayed manual.

So the bar here is higher than volume: **a touch that would embarrass them if
sent is worse than no touch at all.** If there is not enough to say something
real to a person, say so and skip them. A list of forty where eleven are worth
sending is a good outcome. Forty generic ones is a bad one.

Nothing here sends. Every draft is reviewed.

---

## 1. Load the profile and the list

Read `~/.hub/profile.md` for voice.

Take the list however it comes: a paste, a CSV, an export, a connected tool.
For each person, work out what is actually known:

- What they did, and when. Which page, which download, which post, which job
  change.
- Whether there is any history. Check `~/.hub/calls/` and `~/.hub/nurture/`:
  a person who has already had a conversation is a completely different message
  from a cold signal.
- Anything about their company that is public and relevant.

## 2. Sort them honestly

Three piles, and say how many are in each:

- **Worth a real message.** There is something specific to say.
- **Worth a light touch.** Thin, but a short honest note is not embarrassing.
- **Not worth writing to.** Say so and move on. Do not pad this pile into the
  others to hit a number.

## 3. Write

One touch per person in the first two piles.

**Ground it in the specific thing.** The test: could this message be sent to
anyone else on the list unchanged? If yes, it is a template and it fails.

- Short. Three or four sentences. Longer is not more considered.
- Lead with the reason for writing, which is the thing they actually did.
- One question worth answering, or one thing worth reading. Not both.
- No fake familiarity. No "I was just thinking about you". No invented reason
  for getting in touch.
- Never say "I saw you downloaded" in a way that reads as surveillance. Reference
  the topic, not the tracking.
- If they have gone quiet after a real conversation, acknowledge the gap plainly
  rather than pretending it did not happen.

House rules apply throughout: no em dashes, no exclamation marks, nothing
confidential from any prior call, and a real sign-off from the profile.

## 4. For the ones going quiet

A person who had one conversation and then nothing needs a different message
from a fresh signal. Read the earlier record first. Reference what was actually
discussed, name what has changed since, and give them an easy way to say the
timing is still wrong. A polite close is a good outcome; it clears the pile.

## 5. Show the work

Present them as a numbered list, each with a one line note on **why** this
person is worth writing to and what the message is grounded in. That note is
what makes it reviewable at speed.

Name the ones skipped and why.

Save to `~/.hub/nurture/<yyyy-mm-dd>.md` with who was written to and what was
said, so the next run does not repeat an angle on the same person.

**Never send anything.** Drafts only, every time.
