---
name: call-content
description: >
  Mine real sales calls for the week's content: one article and a few posts,
  each built on something a real buyer actually said, and each pointed at a
  resource that already exists. Never invents a customer story.
  Use when the user says "content from my calls", "what should I write about",
  "write this week's article", "turn my calls into posts", "I need posts for
  next week", or asks for a LinkedIn post drawn from their own conversations.
---

# Content from calls

The week's calls already contain the week's content. The job is finding what is
in them, not inventing something plausible.

**Read `../../reference/house-rules.md` first** (the `reference/` folder at the
root of this plugin, two levels up from this skill). The confidence rule applies here more
sharply than anywhere else, because a post is public and permanent.

---

## The rule that governs this skill

**A buyer must never be identifiable.** Not by name, not by company, not by a
detail specific enough to place them. Someone in their market reading the post
should not be able to work out who it was, and the buyer themselves should be
able to read it without recognising the call.

Change the industry when the pattern survives the change. Round the numbers or
drop them. Never use a quote verbatim if the phrasing is distinctive.

If a story only works because of the identifying detail, it is not a story you
can publish. Find another.

---

## 1. Load the profile and gather the calls

Read `~/.hub/profile.md` for voice and transcript source.

Ask which calls to mine, or offer the last week's worth from `~/.hub/calls/` and
the transcript source. More calls is better here: patterns across several are
worth more than one good line from one.

## 2. Find what is actually there

Read for the things that only come from real conversations:

- **A sentence a buyer said that names the problem better than any marketer
  would.** This is the most valuable thing in a transcript.
- **A pattern across calls.** Three buyers reaching for the same wrong
  explanation is an article. One buyer saying something interesting is a post.
- **A moment someone changed their mind mid-call**, and what moved them.
- **The objection that keeps coming back**, and what actually answers it.
- **The gap between what they blamed and what was really wrong.** For Gap
  Selling this is usually the piece worth writing.

Do not go looking for content that flatters the product. The strongest post is
usually one that names something uncomfortable and true.

## 3. Match to what already exists

Read the library in the profile. For each idea, say which existing resource it
points at: a case study, a framework, a calculator, a guide.

An idea with nothing behind it is worth flagging as a gap, not padding out with
an asset that would have to be written first.

## 4. Draft

Ask what they want before writing everything. Default, unless they say otherwise:

- **One article**, 700 to 1,000 words. One argument, carried by real
  conversations rather than by lists. Not a listicle.
- **Two or three short posts**, each standing alone, each on a different idea.

In their voice, from the profile, and to the house rules. No em dashes, no
exclamation marks, no marketing register. If an opening line sounds like a hook
someone else wrote, cut it.

## 5. Check before showing

- Could anyone identify the buyer? Read it as though you were them.
- Is every claim traceable to something actually said on a call?
- Does each piece point at a resource that exists?
- Does it sound like them, or like content?

Show the drafts, name which call each came from so they can check it, and say
which ideas had no asset behind them.

Save what they keep to `~/.hub/content/<yyyy-mm-dd>-<slug>.md`, so the next run
does not repeat an angle.

**Never post anything.** Drafts only.
