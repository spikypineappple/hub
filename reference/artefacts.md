# The three artefacts

What each one is, what it must contain, and what makes it fail. Read
`house-rules.md` first: every rule there binds all three.

---

## 1. The reply

**What it is:** the email to send this buyer now. Not a summary of the call.
They were there.

**Hard limit: under 130 words in the body.** This is read on a phone between
meetings.

**Shape:**

- Open on the thing they will recognise as their own insight. Never on thanks
  for your time.
- Pick **one or two** load-bearing things they said. Not four. A sentence
  packing every number from the call is a compressed summary, which is the thing
  the word limit exists to prevent.
- One line on what it is costing them, and only if they gave a real number.
- One clear next step, with `[DAY]` where a date would go.
- A proper sign-off from the profile, so it can go as it stands.

**What makes it fail:**

- Anything from the confidence rule. Re-read it before writing. The rule works
  where it is enumerated and fails where it has to be inferred, so when a fact is
  powerful and was said about their own position, their own numbers, or a
  colleague, leave it out.
- The subject line carries the same rule and is the part that survives every
  forward.
- Restating the call back at them.
- A limp middle paragraph that says nothing. If a sentence would survive being
  cut, cut it.

**Output:** subject line, body, sign-off, and nothing else inside the artefact
itself. Notes about what the call did not establish go after all three artefacts,
not inside the email.

---

## 2. The CRM record

**What it is:** internal. The confidence rule does not apply here. Everything
that was said belongs in this record, including what they said about their own
position, because that is the deal risk.

### The profile wins. Always.

**If the profile lists CRM fields, that list replaces everything below it.** Not
merges with, replaces. Use its labels, spelled exactly as written, in its order,
with its character limits.

The blocks further down are a fallback for when the profile has no fields at
all. They are printed as code blocks because they are examples, not because they
outrank a real configuration. A record in the wrong labels means she remaps
every field by hand after every call, which is the friction this exists to
remove.

**Mapping the content into her fields:**

- Put each piece of content in the nearest field she actually has. Her "Pain"
  takes the problem, her "Metrics" takes the impact numbers, and so on.
- A fallback field with no home in her list gets folded into the closest one, not
  appended as a stray heading.
- A field of hers with nothing to put in it gets "Not established".
- Never add a field she does not have.
- **When more than one person was on the call**, the contact field takes the one
  whose deal it is, and everyone else goes in the decision process and champion
  fields by name and role. Do not drop a second stakeholder because there is only
  one contact field: a CFO joining call two is the most important thing that has
  happened to the deal.

**If one of her field names is ambiguous, do not stall.** Pick the reading that
fits the methodology, draft with it, and ask at the end alongside the other
caveats. "Metrics" is the common case: in Gap Selling it means the numbers that
size the problem, but plenty of teams use it for target outcomes. Default to the
Gap Selling reading, say which you used, and offer to record her answer under
Notes in the profile so nobody has to ask again. Never hold up three finished
artefacts on a labelling question.

**Check the character limits before showing her.** Where the profile records a
limit, count the field and stay inside it. A field that silently truncates on
paste loses the end of the sentence, and she will not notice until the record is
already wrong.

### Close date

**A timeframe counts as a value.** "Signed by mid September", "before end of
quarter", "once the audit finishes in October": all of these go in the close
date field, in the buyer's own words. Only write "Not established" when they gave
nothing at all.

This is the single most commonly missed field, because the answer usually arrives
as a phrase in the middle of a sentence rather than as a date.

**When the field will only accept a real date**, and most CRMs will not take a
phrase, give both: their words, then the last day of the window they named, so
she can paste one and keep the other. "Signed before end of September (their
words). For the field: 30 September." Naming the boundary of a window they stated
is not inventing a date. Working out that the window is six weeks away is, so
still do not do that.

### The fallback shape

Only when the profile has no CRM fields.

Header, one field per line, values only:

```
CONTACT:
TITLE:
COMPANY:
AMOUNT:
CLOSE DATE:
STAGE:
NEXT MEETING:
```

Then the record, one tight paragraph per field:

```
CURRENT STATE:
PROBLEM:
IMPACT:
ROOT CAUSE:
FUTURE STATE:
DECISION PROCESS:
WHO ELSE MATTERS:
WHAT COULD KILL THIS:
NEXT STEP:
```

**Rules for either shape:**

- Keep each paragraph under 60 words, or under whatever limit the profile
  records for that field.
- Write "Not established" where the call did not cover it, and nothing else.
- No bullets inside a field. These paste into single boxes.

**On a later call on the same deal:** give the **complete** record every time,
rewritten to include everything from the previous record that still holds plus
everything new. It is the whole state of the deal, not a diff, because it becomes
the starting point for the next call. Where the new call contradicts the old
record, the new call wins. A record that arrives as a delta decays a little more
with every call, and most calls are not the first one.

---

## 3. The deal room plan

**What it is:** what this buyer needs to see, in the order they should meet it.

**Pick from the library in the profile.** Name real assets when they exist. Never
invent a title or imply an asset exists that does not: a plan full of things that
would have to be built first is a content backlog, not a plan.

When nothing in the library fits a genuine need, say so and name the gap.

**Shape.** Number each slot. Three to five of them, and no two may do the same
job: if two slots would prove the same thing to the same person, merge them.

For each slot:

```
USE: <the asset from their library, or NOTHING FITS>
NEEDS TO: <what this slot has to prove or answer, one line>
BECAUSE: <the thing they said on the call that makes it necessary, quoted>
```

Add a `MISSING:` line where the library has no answer, saying what would have to
be made.

Finish with one line:

```
WATCH: <the person in this deal who is not yet convinced, and what they will want to see>
```

**If a library asset's name resembles the buyer's own company**, stop and flag it
rather than slotting it in blind. It is either their own story, which is either
perfect or a breach, or a coincidence that will read as sloppy. Say what you
found and let her decide.

**What makes it fail:** slots that are the same slot sliced three ways, and
BECAUSE lines that paraphrase the methodology instead of quoting the buyer. Every
BECAUSE must be traceable to something actually said.

**On a later call:** this one is a delta. Say what to add, what to reorder, and
what to pull, against the room **as it was recorded**, even where that older
record does not match the shape above. Do not rewrite the old plan to spec first.
She built the room from what was written at the time, and that is the room that
actually exists.
