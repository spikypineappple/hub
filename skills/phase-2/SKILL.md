---
name: phase-2
description: >
  Hub Phase 2. The interview: connects the coach, finds where transcripts live,
  learns the CRM field names and the deal room library, and captures voice. Run
  it after Phase 1, on your own, with your real material to hand.
  Use when the user says "run phase 2", "hub phase 2", "set up the hub", "hub
  setup", "connect the hub", "reconnect", "the hub is not working", "change my
  settings", or when any other Hub skill finds no profile at ~/.hub/profile.md.
---

# Hub Phase 2

This is a conversation, not a form. Ask, listen, write down what you learn.

**Read `../../reference/house-rules.md` first** (the `reference/` folder at the
root of this plugin, two levels up from this skill). They govern how you write,
here and everywhere else.

**Do not do it all in one message.** Work through the six parts below in order,
one at a time, and confirm each one before moving on. If something cannot be
connected today, record that and move on. A half-set-up Hub still works.

Everything lands in `~/.hub/profile.md`, which is a plain file the user owns and
can edit by hand at any time.

---

## Before you start

**Check `~/.hub/workspace.md` first.** That is Phase 1's record. If it is not
there, Phase 1 has not run, and Phase 1 is the folder, the memory file, the end
routine and the GitHub connection that everything here gets saved into. Say so
and offer to run Phase 1 instead. If they want to go ahead anyway, that is their
call, but tell them their answers will not be backed up until Phase 1 is done.

If it is there, read it. Anything recorded as not connected is worth naming now
rather than discovering halfway through.

Then check whether `~/.hub/profile.md` already exists.

- **It exists.** Read it, show a short summary of what is already configured,
  and ask what they want to change. Do not re-run the whole thing.
- **It does not.** Say what this will take (about ten minutes, one of the five
  parts needs them to look something up) and begin.

---

## Part 1: the coach

The Hub asks a Gap Selling coach for the diagnosis on each call. It has to be
**their** coach, on their own account, so it answers with their account's
context rather than someone else's.

Ask them to run this in their terminal:

```
claude mcp add --transport http keenan https://gapup.replicatelabs.ai/mcp/server/
```

Then to restart Claude Code and log in when prompted. The login is OAuth against
their existing Gap Selling account, so there is no key to copy and nothing to
paste.

**If they use a different Replicate Labs product**, the URL follows the product:
`https://<product>.replicatelabs.ai/mcp/server/`. The exact URL for their account
is shown in that product's Settings, under MCP.

**Verify it, do not assume it.** Once they say it is connected, call the coach
and ask it to name itself and the methodology it is trained on. Show them the
answer. If no coach tool is available, or the answer is not the coach they
expect, stop and sort that out before continuing: every artefact depends on it.

**Only write `connected: yes` once you have called it and it answered.** Not when
they say it is set up, not when a tool with the right name appears. Every other
skill treats that field as the single authority on whether to call a coach at
all, so a hopeful "yes" sends their calls to whichever coach happens to be
reachable, and the output looks right either way.

If they cannot connect it today, write `connected: no` and leave the rest blank.
The Hub still runs, it just does the diagnosis itself and says so each time.

## Part 2: where the calls come from

Ask how they record calls, and what happens to the transcript afterwards.

Look at what is actually connected before suggesting anything. Common answers:

- **Granola or Fathom, connected to Claude.** Best case. The follow-up skill can
  read the transcript directly. Ask which one and check you can reach it.
- **A file, a folder, or a Drive.** Ask for the path or folder. Record it.
- **Copy and paste.** Completely fine. Record `transcripts: paste`.

Record what they actually have, not what would be ideal.

## Part 3: the CRM fields

**This is the part that decides whether the CRM record is usable or annoying.**

The Hub writes a record to paste into their CRM. If the field names it uses are
not the field names on their screen, they remap eight labels by hand after every
call, and they will stop using it by week three.

Ask them to open one opportunity in their CRM and read out, or screenshot, the
fields they actually fill in. Ask for the labels exactly as they appear.

Then ask:

- Which of those are required?
- Do any have a character limit that bites? A field that truncates at 255
  characters needs shorter paragraphs.
- What are the stage names, in order?

Record the real labels, in their order. If they cannot get to it right now,
record `crm_fields: not captured` and use the defaults in
`../../reference/artefacts.md`, but flag it as the first thing to fix.

Ask separately whether the CRM is connected to Claude as a tool. If it is, note
it, **but the Hub still only drafts**: the record is theirs to paste. Nothing
writes to their CRM automatically.

## Part 4: the deal room library

The Hub plans what a deal room needs to contain. Without knowing what they
actually have, it can only describe things in the abstract, which turns a ten
minute task into a content-production backlog. That is the difference between a
plan and a wish list.

Ask for their resource library: the case studies, one-pagers, calculators,
frameworks, videos and decks they actually put in front of buyers. A list of
titles with one line each is enough. A folder, an export, or a screenshot of the
library all work.

For each one worth recording: the title, one line on what it proves, and who it
is for.

If the list is long, take the twenty they use most. If they cannot produce it
today, record `library: not captured`, and the room plan will describe what each
slot has to do without naming assets. Say that plainly when you write it.

## Part 5: voice

Voice is not one thing. They write differently in an email, a post and a spoken
call, and a skill that samples only the first will make their posts sound like
their follow-ups. Take all three.

**Email.** Two or three follow-ups they actually sent and were happy with. Real
ones, not templates.

**Social.** Two or three posts they wrote themselves and would write again. If
they do not post, say so in the profile rather than inventing a social voice
from their email one.

**Spoken.** A few minutes of them talking, from a call recording or a voice
note. This is the one that catches the words they actually use for their own
market, which almost never survive into their written copy.

Read all of it for: how they open, sentence length, how formal they are, how
they sign off, whether they use contractions, and which words are theirs. Write
down what you notice, in specifics, not adjectives. "Opens with the buyer's own
words, never with thanks for your time" is useful. "Professional but warm" is
not.

Note where the three differ from each other, because that difference is the
useful part.

Also capture:

- Their name, title, company as it appears in a signature
- Their sign-off ("Best," "Cheers," "Thanks,")
- American or British spelling

## Part 6: the rest of the connections

Two more, and both are optional. The Hub works without either, it just has to be
handed things by hand instead of finding them.

**Slack.** Ask whether they want the Hub to be able to read the channels where
deals get discussed. If yes, connect it and then verify by asking it to name a
channel it can see. Record the workspace and what it can reach.

**Gmail.** Ask whether they want it to read their sent mail, which is the
richest source of their real written voice and the fastest way to keep it
current. If yes, connect it and verify by having it find one message they can
identify.

For both: **the Hub reads, it never sends.** Say that out loud, because
connecting an inbox to anything sounds like the opposite. Nothing in the Hub
writes to Slack or sends an email, and connecting these does not change that.

If they would rather not connect either, that is a perfectly good answer.
Record `slack: declined` or `gmail: declined` rather than leaving it blank, so
nobody re-asks them every session.

---

## Writing the profile

Create `~/.hub/profile.md`. Use this shape, filled with what you actually
learned. Leave out sections you have nothing for rather than writing filler.

```markdown
# Hub profile

Last updated: <date>

## Coach
- connected: yes | no          # only ever "yes" after you have called it and it answered
- tool: <the MCP server name, e.g. keenan>
- verified on: <date you called it and it named itself>
- identifies as: <what it actually said>

## Transcripts
- source: granola | fathom | folder | paste
- location: <path or folder, if any>

## CRM
- system: <name>
- connected to Claude: yes | no
- fields, in the order they appear:
  - <exact label> / <required?> / <character limit, if any>
- stages, in order: <list>

## Deal room library
- <title> / <what it proves> / <who it is for>

## Voice
- name / title / company: <as signed>
- sign-off: <exact>
- spelling: american | british
- email: <specific observations from their real emails>
- social: <observations, or "does not post">
- spoken: <words and phrases that are theirs, from a recording>
- where they differ: <the useful part>

## Other connections
- slack: connected | declined | not connected     # workspace, and what it can reach
- gmail: connected | declined | not connected     # read only, never sends

## Notes
<anything else that matters: accounts, patterns, things to avoid>
```

Then show them what you wrote, tell them the file is theirs to edit, and name
the one or two things still missing.

Finish by telling them what to do next, in one line: paste a call transcript and
say "follow up on this call".
