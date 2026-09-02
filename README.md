# The Hub

Turns one sales call into everything that comes after it.

Paste a transcript, and you get back a reply you can send, a CRM record you can
paste, and a plan for the deal room. It also mines your calls for the week's
content, and writes grounded touches for the pile of signals and downloads
nobody gets to.

**It never sends anything.** Every single thing it produces is a draft for you to
read, change, and send yourself.

**It runs on your machine, in your Claude.** Your call transcripts, your CRM,
your inbox. Nothing goes anywhere else.

---

## Installing it

You need [Claude Code](https://claude.com/claude-code). In your terminal:

```
claude
```

Then, inside Claude:

```
/plugin marketplace add <repo-url>
/plugin install hub@hub-marketplace
```

Restart Claude Code when it asks.

### If you do not use Claude Code

The skills work as plain instruction files. Ask James to send you the `skills/`
and `reference/` folders and he will walk you through where to put them. You lose
the one-command install and the automatic updates, nothing else.

---

## Setting it up

Setup comes in two phases. Phase 1 is the workspace, and it is done live with
James beside you. Phase 2 is the interview, and you do it on your own.

### Phase 1: the workspace

```
start phase 1
```

About forty minutes, live. It sets up the five things everything else sits on:

1. **Your folder and its memory.** A `CLAUDE.md` at the root of your folder that
   gets read at the start of every session. It is yours, and it grows as you
   correct things.
2. **Obsidian on the same folder.** A second window onto the work you already
   have, not a different place it goes.
3. **The Design Pack.** What makes the things you produce look like yours rather
   than like a template. Needs a Gemini API key with billing enabled.
4. **The end-of-session routine.** Writes down what happened, saves anything
   learned, pushes your folder to GitHub. You run it yourself before you finish.
   Nothing is finished until it has run.
5. **The GitHub connection, proved.** Not "the push said it worked". Your own
   commit, on the repo page, found by you.

Anything that will not connect on the day gets written down as not connected,
and you carry on. It all lands in `~/.hub/workspace.md`, which is yours to read
and to edit.

### Phase 2: the interview

```
run phase 2
```

Do this on your own, in one sitting, with your real material to hand. It takes
as long as you give it. Six things:

1. **Connecting your coach.** One command, then log in with your normal Gap
   Selling account. No keys, nothing to copy.
2. **Where your call transcripts live.** Granola, Fathom, a folder, or nothing at
   all and you paste them. All fine.
3. **Your CRM field names.** You will need one opportunity open on screen. This
   is the part that decides whether the CRM output is paste-ready or annoying, so
   it is worth the two minutes.
4. **Your deal room library.** The case studies, one-pagers and calculators you
   actually put in front of buyers. Without this it can only describe what a slot
   needs to do rather than name the thing that does it.
5. **Your voice.** Email, social and spoken. Real things you wrote and said, not
   templates.
6. **Slack and Gmail, if you want them.** Both optional, both read only. The Hub
   never sends anything, and connecting these does not change that.

All of it lands in `~/.hub/profile.md`, which is a plain text file. It is yours.
Open it and change anything, any time.

You can stop partway. A half-set-up Hub still works, it just tells you which
parts were guesses.

---

## Using it

### After a call

```
follow up on this call
```

Then paste the transcript, or point it at the recording. You get:

- **The reply.** Under 130 words, in your voice, with a real sign-off. It uses
  `[DAY]` wherever a date goes, because it does not know your calendar and will
  not guess at one.
- **The CRM record.** Header fields plus the full call record, using your field
  names, ready to paste one box at a time.
- **The deal room plan.** Three to five slots in the order the buyer should meet
  them, each one tied to something they actually said, drawn from your library.

**On a second call with the same buyer**, it reads what it wrote last time. The
reply and room plan become updates. The CRM record is rewritten complete, so it
never decays as a deal goes on.

### For content

```
what should I write about
```

It reads your recent calls and finds the sentence a buyer said better than any
marketer would, the pattern showing up across three conversations, the objection
that keeps coming back. Then drafts an article and a few posts, each pointed at a
resource you already have.

**No buyer is ever identifiable.** Not by name, company, or a detail specific
enough to place them.

### For the pile

```
work my signals
```

Paste a list of signals, downloads, or people who went quiet. It sorts them
honestly into worth-a-real-message, worth-a-light-touch, and not-worth-writing-to,
then writes the first two. It will tell you when someone is not worth writing to
rather than padding the list.

The test every message has to pass: could it be sent to anyone else on the list
unchanged? If yes, it gets rewritten.

---

## What it will not do

- **It will not send.** No emails, no CRM writes, no posts, no calendar invites.
- **It will not invent.** If the call did not establish the budget, the record
  says "Not established" rather than a plausible number.
- **It will not put something confidential in an email.** If a buyer tells you on
  a call that his forecast is fiction, or that he might not be in the job next
  year, that goes in your notes and never into anything he could forward. This is
  the rule the whole thing is built around.
- **It will not invent a date.** You get `[DAY]` and you fill it in.

---

## Where things live

```
~/.hub/profile.md          your setup, yours to edit
~/.hub/calls/              one file per call worked
~/.hub/content/            drafts you kept
~/.hub/nurture/            who was written to, and when
```

All of it on your machine, in plain text.

---

## When something is wrong

Tell it. "That is too long", "we do not say it like that", "the CRM field is
called Pain not Problem". It will fix the draft, and where the fix belongs in
your setup it will offer to change `~/.hub/profile.md` so it stays fixed.

If the coach stops answering, run `run phase 2` again and it will reconnect just
that part.
