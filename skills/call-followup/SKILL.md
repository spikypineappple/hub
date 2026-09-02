---
name: call-followup
description: >
  Turn one sales call into everything that comes after it: a sendable reply
  under 130 words, a full CRM record, and a plan for the deal room. Grounded in
  what was actually said, drafts only, never sends.
  Use when the user says "follow up on this call", "work this call", "run the
  follow up", "here is a transcript", "I just got off a call with", "do the
  follow up for <company>", or pastes or points at a call transcript.
---

# Call follow-up

One transcript in. Three drafts out: the reply, the CRM record, the deal room
plan.

**Read `../../reference/house-rules.md` and `../../reference/artefacts.md` before
drafting anything** (they sit in the `reference/` folder at the root of this
plugin, two levels up from this skill). **They are not optional.** They are not background. Each rule in them is there because a draft
already got it wrong.

---

## 1. Load the profile

Read `~/.hub/profile.md`.

If it is not there, say so and offer to run setup. Do not guess at CRM field
names or invent a resource library: the whole point of the profile is that those
are theirs, not yours. If they would rather push on without it, use the fallbacks
in `../../reference/artefacts.md` and say clearly at the end which parts were guesses.

## 2. Get the transcript

In order of preference:

1. **They pointed at one.** A path, a file, a Granola or Fathom meeting. Fetch
   it.
2. **The profile names a source.** Look there for the most recent call, and
   confirm which one they mean before working it.
3. **They pasted it.** Use that.

If the transcript is enormous, say so and ask whether to work the whole thing or
a section. Do not silently truncate.

## 3. Is this a later call on a deal already in here?

Look in `~/.hub/calls/` for an earlier record on the same company.

If there is one, read the most recent record before you start, and tell them you
are treating this as a continuation. The reply and the room plan become deltas.
The CRM record does not: it is rewritten complete. See `../../reference/artefacts.md`.

If you are unsure whether two calls are the same deal, ask. Guessing wrong
merges two customers.

## 4. Get the diagnosis from the coach

Read `connected:` under Coach in the profile. **That field is the only authority.
A tool being present in the session does not mean it is theirs**, and calling
someone else's coach produces confident output from the wrong account, which
looks identical to the right answer.

- `connected: yes` and the tool is reachable: use it.
- `connected: no`, or the field is missing, or the named tool is not there: do
  not call any coach. Do the diagnosis yourself and say so at the end.
- Anything in between, including "not yet verified": treat it as no, and offer to
  run setup to fix it properly.

When you do use it, **this is the step that makes the output theirs rather than
generic**: the coach carries the methodology and their account's context.

Send the transcript and ask for the diagnosis only. Not drafts, not an email. The
gap as it actually stands: where this buyer is, where they want to be, what it is
costing them, what is causing it, what is still unknown, and what could kill the
deal.

Ask it to be blunt about a weak deal.

Then **you** write the artefacts, applying the house rules and the profile. That
split matters: the coach knows the methodology, you know their CRM labels, their
library, their voice, and the rules about what must never reach a buyer.

**Without the coach**, do the same diagnosis yourself before drafting: where this
buyer is now, where they want to be, what the gap is costing them in their own
numbers, what is actually causing it as opposed to what they blamed, what is
still unknown, and what could kill the deal. Write it down before you draft, so
the artefacts come off a diagnosis rather than off the transcript directly. Then
say at the end that it ran without the coach.

## 5. Write the three artefacts

To the specs in `../../reference/artefacts.md`. In order: reply, CRM record, room plan.

Then check your own work before showing it:

- **Reply**: **count the words, do not estimate them.** Under 130 in the body?
  Sign-off present? `[DAY]` rather than a real date, and no arithmetic anywhere?
  Nothing from the confidence rule, **in the body or the subject line**? Read the
  subject line on its own and ask who it damages if their boss sees nothing else.
  Is any named colleague praised in a way that indicts the others?
- **CRM**: does it use the profile's field names, in her order? **Count every
  field that has a character limit**, do not eyeball it: a field that overruns
  truncates silently on paste and she will not notice until the record is wrong.
  Is everyone who was on the call in there somewhere? Is anything invented?
- **Room**: are the slots genuinely different jobs? Is every BECAUSE traceable to
  something said? **Does any asset name resemble the buyer's own company?** If it
  does, flag it rather than slotting it: the better it seems to fit, the more
  likely it is their own story coming back at them.
- **Everything**: no em dashes, no en dashes, no methodology labels in the reply.

Fix what fails, then show them.

## 6. Save it

Write to `~/.hub/calls/<company>-<yyyy-mm-dd>.md`, dated by **the day the call
happened**, not today. If the transcript carries no date, or one that cannot be
right, say so and ask rather than inferring one: this filename is what finds the
deal next time, so a wrong date quietly breaks the continuation: the three artefacts, the date,
and who was on the call. This is what makes the next call on this deal an update
rather than a duplicate.

Do not save the raw transcript unless they ask. It is the largest and most
sensitive thing in play and they already have it wherever it came from.

## 7. Hand it over

Show the three artefacts clearly separated so they can copy each one out.

Say in one line what you were unsure about, if anything, and what the call did
not establish. A field the buyer never gave you is worth naming out loud, because
that is the question for next time.

**Never send anything.** No email, no CRM write, no calendar invite. Drafts only.
