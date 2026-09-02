---
name: phase-1
description: >
  Hub Phase 1. Sets up the workspace the rest of the Hub sits on: the folder and
  its memory file, Obsidian reading the same folder, the Design Pack, the
  end-of-session routine, and the GitHub connection proved on the repo page.
  Run this first, live, with someone beside you.
  Use when the user says "start phase 1", "run phase 1", "hub phase 1", "set up
  my workspace", "set up the hub, phase 1", or when any Hub skill finds no
  `~/.hub/workspace.md`.
---

# Hub Phase 1

Phase 1 is the workspace. Phase 2 is the interview. This skill is Phase 1 only.
When it finishes, hand off to Phase 2 and stop.

**Read `../../reference/house-rules.md` first** (the `reference/` folder at the
root of this plugin, two levels up from this skill). They govern how you write,
here and everywhere else.

This runs live, with someone sitting beside the user. Expect about forty
minutes, and expect to be paused partway: the session that installs this does
parts 1 to 3, teaches for twenty minutes, then comes back for parts 4 and 5.
Handle that. Check `~/.hub/workspace.md` at the start and resume from the first
part that is not done rather than starting again.

**Do not do it all in one message.** One part at a time, confirmed out loud
before the next.

---

## The rules this skill runs on

**Never name a button you have not seen.** Screens change and they differ by
operating system and by version. Say "find the option that creates a new
repository", not "click the green New button". If the user cannot find it, ask
them what they can see and work from that.

**Nothing is done because a tool said so.** Every part below has a check that
looks at the thing itself: a file open on screen, a page in a browser, an image
that exists on disk. An install message is not proof, and a command that exits
quietly is not proof. This is the whole point of the phase.

**A part that will not connect is recorded as not connected, and you move on.**
Write it down and carry on to the next part. Do not spend the session on one
stubborn key. A half-done Phase 1 that is honest about which half is far more
useful than a stalled one.

---

## Before you start

Check for `~/.hub/workspace.md`.

- **It exists.** Read it. Show a short summary of what is already done and what
  is recorded as not connected, and ask what they want to pick up. Do not re-run
  the parts that are done.
- **It does not.** Say what Phase 1 covers in one line each, say it is about
  forty minutes, and begin.

Also check which operating system you are on before giving any command. macOS
and Windows differ in three places below and getting it wrong wastes the block.

---

## Part 1: the folder and its memory

The folder is already there and already a git repository by the time you run.
Confirm that before anything else: ask them for the folder, `cd` into it, and
check `git status` answers rather than erroring. If it is not a repository,
stop and say so. Everything after this assumes it.

Now give the folder a memory. Create `CLAUDE.md` at the root of the folder:

```markdown
# <their name>'s workspace

<one line on what they do and who they sell to, in their words>

## How I want you to work with me

<empty. This fills up as they correct things.>

## Things that are true here

- My work lives in this folder. Obsidian and Claude Code both read it.
- Nothing is finished until the end-of-session routine has run.
```

Write it with them, not for them. Ask the two questions, use their answers, keep
it short. The file matters less than them understanding that it exists and that
it is read at the start of every session.

**Show them the two ways it grows.** A message that starts with `#` offers to
save that line straight away, and the end-of-session routine writes down what
was learned in the session. Do not just describe the `#` shortcut, have them use
it once, on something real, and open the file so they see their own line in it.

**Check:** open `CLAUDE.md` and read their own words back to them off the screen.

## Part 2: Obsidian on the same folder

Obsidian is a second window onto the folder they already have. It is not a
different place their work goes, and that is the sentence to say out loud.

- Install Obsidian from its official site, choosing the download for their
  operating system.
- On first run it asks what to open. Find the option that opens an existing
  folder as a vault, and point it at their folder.
- It may warn about opening a folder that already has files in it. That is
  expected and it is safe.

**Check, and do not skip this one.** Have them open `CLAUDE.md` in Obsidian and
the same file in Claude Code at the same time, on screen together. Add a word in
one and watch it appear in the other. The point they need to leave with is that
there is one folder and two windows onto it.

If Obsidian will not install today, record `obsidian: not connected`. Nothing
else in Phase 1 depends on it.

## Part 3: the Design Pack

The Design Pack is what makes the things they produce look like theirs rather
than like a template. It is five skills that ship with the Hub: `design-pack`
runs the pass, `impeccable`, `emil-design-eng` and `taste-skill` are the craft
floor it holds work to, and `banana` is what actually generates images.

Images need a Google Gemini API key with billing enabled on the Google account
behind it. Without billing the key exists and every generation fails, which
looks like a broken install rather than an unpaid account, so check that first.

Ask them to have the key to hand. Then set it in their environment, which
survives a restart, rather than pasting it into a file that gets committed.

**Set two names for the same key.** The tooling reads `GOOGLE_AI_API_KEY`, and
`GEMINI_API_KEY` is the name Google's own console uses and the one they will
have written down. Set both to the same value and neither of you has to remember
which is which.

- **macOS.** Add both `export` lines to their shell profile, which is `~/.zshrc`
  on any recent macOS:

  ```
  export GEMINI_API_KEY=<their key>
  export GOOGLE_AI_API_KEY=<their key>
  ```

  Adding the lines is not enough for the terminal already open, so either
  `source` the profile or open a new one.
- **Windows.** The PowerShell equivalent for both names, set for the user rather
  than the session so they survive a restart.

**Never write the key into a file inside the folder.** The folder is pushed to
GitHub. If the key is already in a file there, stop, take it out, and tell them
plainly that a key that has been committed should be rotated rather than reused,
even to a private repo.

**Check:** generate one small image, and open it. Not "the key is set", not "no
error". An image on disk that they have looked at. It saves to
`~/Documents/nanobanana_generated/` and the command prints the full path.

**Ask for a real photograph, not a test pattern.** A plain shape on a plain
background comes back as `finishReason: IMAGE_RECITATION` and no image, which
looks exactly like a broken key and is not one. Describe a scene: an object, a
surface, and where the light comes from. Something like a piece of fruit on a
linen tablecloth in window light works every time and takes about twenty
seconds.

If it fails, read the actual error before changing anything. They say different
things and have different fixes: `IMAGE_RECITATION` means the prompt was too
thin, a billing error means the card is not attached, and a missing key means the
environment variable did not survive the new terminal. Python 3 is all it needs
beyond the key, and it is already on macOS.

If it will not work today, record `design_pack: not connected` and move on. It
is the one part of Phase 1 nothing else depends on.

---

> **This is where the live session pauses.** Parts 1 to 3 are the install block.
> Parts 4 and 5 come back to it later, deliberately, because the routine and the
> connection are the two things they have to trust and trust comes from having
> run it themselves. If you are resuming here, say so and carry on.

---

## Part 4: the end-of-session routine

This is the habit the whole workspace rests on: nothing is finished until the
routine has run. It writes down what happened, saves anything learned, and
pushes the folder to GitHub.

It belongs to them, not to the Hub, so write it into their folder rather than
shipping it in the plugin. Create `.claude/skills/end/SKILL.md` inside their
folder:

```markdown
---
name: end
description: >
  End the session. Writes a session log to today's daily note, saves anything
  learned into CLAUDE.md, and pushes the folder to GitHub.
  Use when the user says "end the session", "wrap up", "/end", "save and exit",
  or before they exit.
---

# End of session

Do these in order, and report what actually happened at each one.

1. **Write the log.** Append to `daily/<today's date>.md`, creating the file and
   the folder if they are not there. A few lines: what was worked on, what was
   decided, what is left open. Write it so a session tomorrow could pick it up
   cold.

2. **Save what was learned.** If the user corrected something in a way that
   should hold next time, add it to `CLAUDE.md` under "How I want you to work
   with me", in their words. Show them the line and let them change it. If
   nothing was learned, say so rather than inventing a lesson.

3. **Push.** `git add -A`, commit with a one line message describing the
   session, then `git push`.

4. **Report the push honestly.** Say what the push did, including if it failed.
   A failed push is the one thing here that loses work, and it is quiet.

Never say the session is saved unless the push succeeded.
```

**A skill written during a session does not exist in that session.** Claude Code
loads skills at startup, so `/end` will not be found until they exit and open a
new session. Say that before they try it, because otherwise the first thing they
see after you build the routine is it failing. Have them `/exit`, open a fresh
session, say a couple of things, and run the routine there.

This is the same rule that bit the install twice: **a terminal session cannot
see software that arrived after it started.** Once they have met it three times
it stops being a mystery, so name it early and name it every time.

Then have them run it, themselves, on the session as it stands. Not you.

- Open the session log it wrote, in Obsidian, and read the first few lines
  together. Say that this is what a fresh session picks up.
- Have them run it a second time straight away, so the trigger is in their
  fingers rather than in their notes. It will report there is little new, and
  that is the correct answer.
- Get them to say back, in their own words, what they run and when.

## Part 5: the GitHub connection, proved

The routine pushed. Now prove the push landed, because this is the failure that
is silent and it is the one that costs them work.

**Look at the repository page in the browser, not at the terminal output.** Have
them refresh it and find the files the routine just wrote, and the commit it
just made, with its message. If the daily note is on that page, the connection
is real.

If it is not there:

- The usual cause is credentials that were never stored, so the push failed and
  the routine reported it into a wall of other output.
- On macOS the prompt asks for a username and password, where the password is a
  personal access token generated in their GitHub developer settings with
  repository access, never their login password. The keychain stores it after
  the first success.
- On Windows expect a browser window asking them to authorise instead.
- Fix it, push again, and check the page again. Do not leave this part on
  "should work now".

**Check:** a commit they made, visible on github.com, that they found
themselves.

---

## Writing it down

Create `~/.hub/workspace.md`:

```markdown
# Hub workspace

Phase 1 run on: <date>

- folder: <path>
- memory file: yes | no
- obsidian: connected | not connected
- design pack: connected | not connected     # key in the environment, one image generated
- end routine: installed and run | installed, not run | not installed
- github: verified on the repo page | not verified

## Not connected
<one line per part that did not connect, and what it would take to finish it>

## Notes
<anything specific to their machine worth knowing next time>
```

Be accurate rather than generous. Every other part of the Hub reads this to
decide what it can rely on, and a hopeful "connected" sends someone looking for
a problem in the wrong place.

---

## Finishing

Show them `~/.hub/workspace.md`, tell them the file is theirs, and name anything
recorded as not connected along with what it would take to finish it.

Then set Phase 2 and stop. Phase 2 is the Hub interviewing them about how they
actually work, and it needs their real material to hand: call transcripts, one
opportunity open in their CRM, and the resources they actually put in front of
buyers. It takes as long as they give it.

Give them the sequence, and have them write it down themselves rather than
taking a copy:

```
open the terminal
cd <their folder>
claude
ask for Phase 2
run the end routine
/exit
```

Tell them to run the end routine even if they stop halfway, so nothing is lost.

Do not start Phase 2 here.
