# Word Patent Review Threads

Use this reference when a patent or technical-disclosure DOCX contains reviewer comments and the user asks to answer, revise, preserve review mode, or place answers in Word's reply box.

## Contents

1. Deliverable semantics
2. Evidence-backed response workflow
3. Native Word thread implementation
4. Migration from an incorrect inline-reply version
5. Compatibility and preservation rules
6. Verification gates
7. Failure handling and handoff

## 1. Deliverable Semantics

Translate the user's UI language into the exact Word artifact:

- “回复框”, “reply”, or “在该批注下面回复” means a child reply in the existing thread.
- Text appended inside the parent comment is not a reply, even when it is visually placed below the question.
- A new top-level comment is not a reply, even when it has the same anchor.
- Body revisions and comment replies are separate requirements. Preserve or create tracked body edits only when requested, and create thread replies independently.

Before editing, state the intended artifact in concrete terms: retain each reviewer comment, add one child reply under it, set the requested author, preserve tracked changes, and leave the original file untouched.

## 2. Evidence-Backed Response Workflow

Build a one-to-one response map before writing replies. Record, for every parent comment:

- stable parent identity: comment ID, ordinal, anchor text, and reviewer author
- exact reviewer question
- supporting passage in the patent draft, paper, code, experiment, figure, or formula
- proposed reply text
- required body revision, if any
- confidence, unresolved fact, or inventor-confirmation need

Answer from the supplied paper, source code, experiments, and patent text. Do not invent thresholds, variables, implementation steps, claimed effects, or legal conclusions. If the evidence is incomplete, say what must be confirmed instead of presenting an assumption as fact.

Audit replies individually and as a set:

- answer the exact question rather than a nearby topic
- keep terminology and symbols consistent with the revised body
- distinguish explanation from a committed amendment
- ensure a claimed amendment actually exists in the document
- avoid duplicate, shifted, or cross-mapped replies
- preserve concise, professional Chinese suitable for inventor-agent collaboration

## 3. Native Word Thread Implementation

Prefer Microsoft Word's object model on Windows when the user requires the actual reply control. Use a copy of the DOCX and let Word write all modern comment-thread parts.

Core operation:

```powershell
$reply = $parent.Replies.Add($parent.Range, $replyText)
$reply.Author = 'zhengmin'
$reply.Initial = 'ZM'
```

Apply these safeguards:

- Set `Author` and `Initial` after `Replies.Add`; Word may initially use the signed-in Office identity.
- Process original parent comments from the highest index to the lowest. Adding a reply increases `Document.Comments.Count` and can shift later indices during forward iteration.
- Identify parents by reviewer author, anchor, stored ID/ordinal, and expected reply count. Do not rely on one attribute when the document may contain mixed authors or existing replies.
- Fail if a parent is missing, already has an unexpected reply, or the response map is not one-to-one.
- Save, close, and reopen with Word. Re-read `Replies.Count`, reply author, and reply text after reopening.
- Run automation on a duplicate and keep Word hidden only if prompts cannot be missed. A repair dialog must never be silently accepted as success.

Do not use `Document.Comments.Add` for this requirement; it creates a top-level comment. Do not create a second comment and merely imitate a thread through matching text or anchors.

## 4. Migration From an Incorrect Inline-Reply Version

When a prior artifact contains `zhengmin 回复：...` appended to each parent comment:

1. Preserve a clean backup and extract all parent/reply pairs before editing.
2. Split each comment only at the exact known marker; fail on missing, duplicate, or empty markers.
3. Restore the parent comment to the reviewer's original text.
4. Add the extracted answer through `parent.Replies.Add`.
5. Set the child author explicitly.
6. Reopen and verify that no inline marker remains and every parent has exactly one native reply.

Preserve the original comment formatting where practical. If replacing the full `Comment.Range.Text` would destroy meaningful formatting or embedded objects, delete only the appended range or restore the parent from the untouched source.

## 5. Compatibility and Preservation Rules

- Never edit the user's only copy. Produce a clearly named derivative until all gates pass.
- Preserve comment anchors, reviewer authors, tracked insertions/deletions, `w:trackRevisions`, equations, images, relationships, and content types.
- Avoid broad `document.xml` or `comments.xml` reserialization. Use minimal edits or Word-native APIs.
- Do not manually synthesize `commentsExtended.xml`, `people.xml`, `commentsIds.xml`, or `commentsExtensible.xml` for a final native-thread deliverable. Structurally plausible metadata can still trigger Word's unreadable-content repair dialog.
- Treat “Word found unreadable content”, repair prompts, compatibility warnings, and conversion-to-image warnings as failures. Do not ask the user to click “Yes” and accept a repaired deliverable.
- Ensure the target file is not already open. Clean up only automation-created lock files and processes; never terminate an unrelated visible Word session.
- On Windows PowerShell 5, read UTF-8 automation scripts explicitly as UTF-8 or save them with a compatible encoding. Garbled Chinese paths can select the wrong file or fail before editing.

## 6. Verification Gates

Pass every applicable gate before delivery.

### Word-native gate

- Open the output without a repair or compatibility prompt.
- Confirm expected total comments, parent comments, and child replies.
- Confirm every intended parent has exactly the expected reply count.
- Confirm every child reply has the requested author and correct text.
- Confirm reviewer comments retain their author and intended text.
- Confirm no inline fallback marker remains.

### OOXML structural gate

- Run ZIP CRC and XML parse checks.
- Match comment IDs to their range starts, range ends, and references.
- Confirm Word-generated thread-parent relationships for all child replies.
- Confirm comment relationships and content-type declarations exist without duplicate or dangling entries.
- Confirm tracked-change counts/authors and `w:trackRevisions` remain as expected.
- Confirm equations, images, captions, and other media counts did not unexpectedly change.

### Content gate

- Compare the final reply map against the source evidence one item at a time.
- Confirm all requested comments are answered and no extra reviewer thread was modified.
- Recheck formulas, variables, thresholds, figure descriptions, implementation sequences, and scope statements against the paper and code.
- Mark unresolved inventor facts rather than concealing uncertainty.

### Visual gate

- Render the latest DOCX and inspect all pages for layout, equations, figures, tables, captions, pagination, and blank-space defects.
- Remember that PDF and page images often omit comments; use them only for body-layout QA.
- If LibreOffice rendering is unavailable, attempt a safe Word export when appropriate. If export hangs or fails, stop only the automation-created process, keep the verified DOCX, and disclose that page-image QA was not completed.

## 7. Failure Handling and Handoff

When a native-thread attempt fails:

1. Keep the untouched source and last known clean derivative.
2. Remove or quarantine the defective generated artifact so it is not mistaken for the final version.
3. Diagnose whether the failure came from thread metadata, a locked document, account identity, Unicode paths, or rendering automation.
4. Regenerate from the clean derivative through Word rather than repairing questionable custom OOXML in place.
5. Re-run all gates after regeneration.

Deliver only the final requested DOCX unless the user asks for diagnostics. State that replies are native Word child replies, name the requested author, report save-close-reopen validation, disclose any skipped visual QA, and confirm that the original source was not modified.
