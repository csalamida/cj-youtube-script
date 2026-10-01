---
name: cj-youtube-script
description: Use when CJ wants a YouTube script. Guided intake.
version: 1.0.0
author: Hermes Agent
metadata:
  hermes:
    tags: [content, youtube, cj, scriptwriting, intake]
    related_skills: [content-engine-ops]
---

# CJ YouTube Script — Guided Intake

CJ says "script", "YouTube video", "how-to", "build video", or invokes this skill by name. Do not make him explain how to use it. You drive; he answers one question at a time.

## Before anything

Load, in this order:
1. `ai-marketing-team/content-engine/_shared/cj-voice-soul.md`
2. `ai-marketing-team/content-engine/_shared/cj-voice-calibration.md`
3. `ai-marketing-team/content-engine/_shared/cj-youtube-conversational-english-standard.md` (the writing standard; CJ's calibration is locked there — never re-ask pacing, length, audience, format, tone default)

This lane is separate from short-form Q&A. Never import Q&A drafts, provenance, or Taglish.

## Step 0 — Pick the script type

Ask with `clarify` (single-select). Wording, verbatim:

> **What kind of video are we scripting?**
> 1. **How-to** — one specific task in HighLevel, start to finish
> 2. **Complete build** — a working business system, several parts connected
> 3. **Changelog-to-build** — a new HighLevel feature, turned into something useful
> 4. **Troubleshooting** — something isn't working; trace it and fix it
> 5. **Feature explainer** — what a thing actually is and when to use it

Then run the matching question chain below. **One question per turn.** Put a recommended default first when one exists. Plain sentences, no jargon, no JSON.

## Step 1 — Question chains (chronological)

Record each answer in an intake file: `~/yt-research/intake/<slug>.md` (create dir). The intake is the brief; the draft is built from it.

### 1. How-to
1. What's the task? (one sentence, in the words a viewer would search)
2. Who's the viewer — no account yet / new user following along / existing user?
3. What do they have at the end? (the payoff, concrete: "a form that tags the lead and texts you")
4. What do most tutorials on this skip or get wrong? (the distinction)
5. Have you done this yourself in a real or sandbox account? (Teacher tone if yes; Peer if no)
6. Which account will you record in? (sandbox default)
7. One real-feeling example scenario to follow through the whole video? (business type + the lead/customer)
8. Anything you want said about when this does NOT work?
9. Next step at the end — free-trial link, next video, or nothing?

### 2. Complete build
1. What does the finished system do, in one sentence a business owner would say?
2. What are the parts? (list them; I'll order them)
3. What must exist before we start? (calendar, pipeline, tags, etc.)
4. Who's the viewer and where are they starting from?
5. One business to follow through the build — type, one lead, what happens to them
6. Have you built this exact thing before? (Teacher / Peer)
7. What's the moment where people usually break it?
8. How do we prove it works on camera? (what result do we show)
9. What can the viewer customize after?
10. Next step at the end?

### 3. Changelog-to-build
1. Which update? (paste the changelog title or link)
2. What can someone build or do now that they couldn't before?
3. Have you tested it live yet? (if no → Peer tone, and flag `CURRENT-UI-CHECK`)
4. Who cares about this — which viewer?
5. One example use to demonstrate
6. Does it replace an older way of doing it? What was the old way?
7. Any limits or gotchas you already noticed?
8. Next step at the end?

### 4. Troubleshooting
1. What's the symptom, in the viewer's words? ("form submits but nothing happens")
2. What's the working path we prove first?
3. Which one failure do we break on purpose?
4. Can you reproduce it in the sandbox before recording? (must be yes before drafting the failure section)
5. Where in the chain does the evidence stop matching? (Form → Contact → Workflow → Action → Result)
6. What's the fix, and how do we retest?
7. Who's the viewer?
8. Next step at the end?

### 5. Feature explainer
1. What's the feature, and what do people think it is?
2. What is it actually — in one plain sentence, no product words?
3. When should someone use it, and when should they not?
4. What gets confused with it?
5. One concrete situation where the difference matters
6. Have you used it in a real setup? (Teacher / Peer)
7. Next step at the end?

## Step 2 — Gap check (ask more if needed)

After the chain, run this checklist silently. For every gap, ask **one more specific question** — keep going until all are filled or CJ says "just draft it":

- [ ] One identifiable viewer and their starting point
- [ ] Concrete payoff (something that exists or is understood at the end)
- [ ] The distinction — why this beats the other videos on the topic
- [ ] One sustained example to carry the whole video
- [ ] Tone decided from CJ's actual experience (never assumed)
- [ ] Useful visible progress/results at natural lesson milestones; no universal timer or mandatory interruption schedule
- [ ] Any opinion / story / "I always" line has CJ's real words or is marked `CJ INPUT REQUIRED`
- [ ] Product behavior is tested, or marked `{{UI: …}}` / `{{OBSERVED: …}}`
- [ ] One next step

Never fill a gap with plausible copy. If CJ says "I don't know" to an opinion question, that beat stays `CJ INPUT REQUIRED` or gets cut.

## Step 3 — Draft

Follow the standard exactly:
1. Skeleton (claims, not topics) — show CJ, one reaction, then continue
2. Talk-style rehearsal draft (as if transcribing speech; one thought per line; ~20% over target words)
3. Three cut passes: value → order → read-aloud
4. Recording-notes sheet, same section order
5. Production-notes block (UI checks, evidence, demo data) — separate from spoken words
6. Internal `CJ VOICE RECEIPT`; request an independent second-bot voice-gate review before labeling `READY FOR CJ REVIEW`

Save to `ai-marketing-team/content-engine/youtube/<slug>/` as `intake.md`, `script.md`, `notes.md`, `production-notes.md`. Do not commit; do not publish.

## Step 4 — Recording-ready delivery pass

Before handing back a long-form script, convert it into a recording-ready document, not just a writing draft.

### Separate the layers

Keep these visually and structurally distinct:

1. **Spoken script** — the words CJ may say aloud.
2. **Recording instructions** — what to show, prepare, or do; mark `DO NOT READ`.
3. **Batch plan** — where a chapter starts and ends.
4. **Delivery formatting** — no slash notation by default; when CJ requests line-by-line trim mode, use one complete speaking unit per line ending in `/`, as defined below. Otherwise use natural thought blocks and whitespace. Keep selective 21 pt bold emphasis against 17 pt regular spoken text and red full-stop instructions after the relevant spoken block.
5. **Screen checklist** — a separate accessible document listing assets, screens, code, prompts, links, and test data that must be ready.

Never place a stop instruction before the spoken material it governs. A chapter label must clearly say `DO NOT READ`, followed by the spoken lines. For CJ’s PiP screen tutorials, put explicit red non-spoken camera-state cues immediately before the corresponding spoken lines in every batch: `FULL SCREEN OF YOURSELF HERE` means no screen share; `TALK WHILE SHARING SCREEN HERE (PiP)` means real screen shared with CJ’s face in the corner and the exact screen named. Begin full-screen for the opening, switch to PiP when the actual demo begins, and return full-screen only after showing the evidence. Batch stop alone never implies a camera change. Keep copy-and-type inputs inline in the same scroll; do not make CJ switch tabs to know what to say or show.

### Anti-reading workflow

Design the recording in short chapters, not one continuous performance:

- Record the opening as one batch.
- Stop completely.
- Show a chapter transition card.
- Reset framing, posture, screen, code, and composure.
- Record only the next chapter.
- Keep the final recap and CTA as separate pickups when useful.

The goal is not to read every word while staring at the page. The script is a speaking rail. CJ should read it aloud once, mark phrases he would naturally say differently, then record in thought-sized blocks. During UI demonstrations, allow controlled adlibs inside a clearly marked window, then return to the scripted comparison or takeaway.

Use delivery formatting that feels natural to CJ. If slash notation is unfamiliar, do not use `/`, `//`, or other pause symbols in the spoken script. Use one spoken thought per line, blank lines for natural breaths, selective bolding for conviction lines, and a prominent red `STOP — END THIS BATCH` marker for full stops. The script should look like something CJ can comfortably read, not like performance notation.

### Conversational rehearsal gate

CJ's correction: plain vocabulary alone does not make a script conversational. Before delivery, run five complete-script text rehearsal passes and save the findings: (1) ordinary spoken wording, (2) complete thought/trim boundaries, (3) redundant explanations and slogans, (4) words synchronized with actual screen actions, and (5) full lesson flow including a proper intro and practical close. Apply the findings; five reviews without revisions are not an improvement. Do not claim an audio rehearsal or CJ voice match from text review. A direct 'In this video...' intro is allowed when it quickly names the task and useful payoff; do not force a clever cold open or invent audience friction. Replace abstract manual language with the demo person's situation. Keep product/evidence safety boundaries, but move production-only instructions out of spoken copy. Never pad narration to meet an arbitrary word minimum. Avoid generic polished aphorisms and repeated definitions; let the demonstration teach. Review proof warnings for natural wording too: 'We're not assuming that opening the thread changes its read state' is production reasoning; 'We'll use that control so we know the thread is marked read' describes the actual screen action. Keep essential viewer-facing distinctions, but do not narrate the writer's verification protocol. Avoid doubled command verbs such as 'add Add Task'; say 'choose Add Task'. Match every demo name, label and setting to the preserved inline inputs. After voice edits, verify all source/canonical/retained recording copies and recalculate counts. Preserve live manual edits, demo values, links, camera directions, and batch boundaries.

### CJ-requested line-by-line trim mode

When CJ explicitly asks for slash pause marks, that current request overrides the no-slash baseline for that script. Put `/` at the end of a short, complete speaking unit and put each unit on its own line. Define it visibly: pause speech, keep recording, then continue; do not speak the slash. `STOP — END THIS BATCH` still ends recording. Never split a phrase mid-thought or add several levels of slash punctuation unless requested. Aim for connected speech within each unit, not a punchy performance of every clause. Audit the entire spoken script: replace manual/narrator language with screen-connected explanations, give a clear plain intro, cut repeated slogans, and keep production safety instructions in red. Do not make CJ solve stiff writing with delivery tricks. Claim only text-level rehearsal until actual audio is reviewed.

### Conviction and sentence-level delivery

Outside CJ-requested line-by-line trim mode, do not mark every sentence with a pause symbol. That creates visual clutter and makes delivery mechanical. In explicit trim mode, the slash marks an editing gap after a complete thought, not dramatic emphasis. Otherwise:

- Put one thought on each line.
- Use whitespace between complete thoughts; do not split every sentence into choppy fragments.
- Use selective larger bold black text for the idea that should land. Never require a timed pause after every sentence.
- Put the strongest sentence in a short standalone line.
- Use plain wording that can be said with conviction; do not make the performer manufacture emphasis through punctuation.
- Where useful, add a brief parenthetical delivery note such as `(land this)` or `(slow down)` — clearly marked `DO NOT READ` — but use these sparingly.

Example:

This is the fastest option.

**But you're starting with someone else's layout.**

Read this as connected speech, not three forced dramatic beats.

The script should make the conviction beat visible without turning every line into a performance instruction.

- Can CJ tell instantly what is spoken and what is not?
- Does every chapter have a clear start and stop?
- Are UI, code, prompts, links, and assets prepared in a separate checklist?
- Does the script give him permission to stop before preparing the next screen?
- Are adlib windows limited to demonstrations rather than the hook, framing, comparison, or outro?
- Does the spoken copy sound like thought-sized speech rather than written prose?
- Are repeated explanations cut before adding more production detail?
- Are tool names and method names consistent across the hook, chapters, recap, and outro?

## Multi-video Google Doc delivery

When CJ requests full scripts for an existing topic slate, do not deliver more outlines. The main topic tab is the single continuous recording script: spoken words, non-spoken camera cues, exact inline copy-and-type values, and setup reference in one scroll. Put a brief, topic-specific red `DO NOT READ — BEFORE RECORDING` gate immediately before Batch 1; it must name the required sandbox fixture, product-control checks, and evidence needed before any result pickup. A setup checklist at the bottom alone is too late for a one-scroll filming session. If a scheduled or drip example needs elapsed time, choose an allowed interval that can finish during filming or label a genuine later pickup; never script future results as if already observed. Existing child Recording Script and Screen Prep tabs may remain for reference; when updating camera cues across an existing document, update and verify both the ten main topic tabs and their matching Recording Script children so they cannot disagree. Count spoken words separately from directions and include demonstration time separately in runtime estimates. Review all scripts, not a sample; verify every recording tab's text, centered alignment, black 17 pt narration, black 21 pt bold conviction lines, and red non-spoken material. Keep direction blocks before the spoken material they govern and full STOP markers after the batch's last spoken line. Source-backed rehearsal drafts are not live-tested demonstrations; keep unresolved product checks in prep and gate result pickups on real observations.

## Copy-and-type demo inputs

Include exact ready-made demo values for recording, not only instructions to prepare examples. Place them directly inside the recording script at the relevant typing or demonstration step as red bold DO NOT READ — TYPE THIS blocks: field labels and values, asset names, message copy, tasks, settings, and expected matching/nonmatching controls. Do not require CJ to switch to a separate Copy & Type tab for ordinary text inputs. Keep downloadable CSV files separate, but actually create and deliver the file—not merely name it in the script. When CJ asks for a Google Sheet source, provide a Sheets-compatible workbook containing the exact import rows, and create an online Sheet only when Sheets write authorization is available; distinguish the local workbook from a live Google Sheet. Verify CSV ↔ workbook row parity and attach both files for recording. Preserve spoken copy when inserting these blocks. Keep names and values consistent with the script; provide downloadable CSVs when importing is demonstrated. Separate fictional input from observed evidence. Use example.com only for storage-only identities, never delivery tests; mark controlled inboxes, actual user selections, real timestamps, future dates, and picker-inserted dynamic fields explicitly. Do not invent live merge syntax, user accounts, historical creation dates, or successful results. Preserve existing recording tabs and verify every added pack after publishing. A demo pack authorizes document preparation, not account mutations or sends.

## Step 5 — Hand back

Lead with the one ask: *"Read the script aloud once and tell me what sounds wrong."* Put the word count, runtime estimate, and open `CJ INPUT REQUIRED` items below it. No governance prose.

## Numbered-series ideation and hook gate

For SEO/discovery, topic validation, or claims about what makes videos succeed, load `references/discovery-and-evidence.md`. When studying creator scripts or adapting lessons from a viral example, also load `references/creator-script-case-study.md`: separate observed script structure from attributed authorship and unproven performance causality. Never treat viral examples or creator popularity as causal proof. For primary-source hook research use `references/hook-research-source-audit.md` and `references/practitioner-hook-notes.md`; for draft exercises use `references/numbered-hook-practice.md`.

When CJ requests content generation, numbered list videos, or stronger spoken/text/visual hooks, load `references/numbered-series-hooks.md`. Use his Pizza Method worksheet as an ideation wheel. Deliver concrete numbered working titles plus matched spoken, on-screen-text and edit hooks; generic topic menus do not satisfy this request. Counts remain provisional until verified, without making CJ review the internal evidence machinery.

## Apply the research before drafting

Research notes alone do not count as an improved script. For each new draft:
- Identify why the intended viewer would click and what the opening must confirm. Search-led and recommendation-led are working hypotheses, not separate rigid formulas. Start from either the viewer's task or a truthful, filmable thumbnail concept; never let a borrowed image dictate an unsupported promise.
- Choose the lesson architecture before drafting: diagnostic decision framework, one consequential contrast, distinct alternatives, or cumulative steps. Do not force 'ways' into a fake sequence or present dependent steps as interchangeable methods.
- Design title/thumbnail promise, spoken hook, short screen text, first visual, and handoff into the demonstration together. Offer three genuinely different opening approaches; label the selection editorial judgment, not a proven winner. Check that the outcome and any important caveat agree with the title and thumbnail before writing a word-for-word script.
- Show early useful evidence or a result when appropriate. Let curiosity come from how to achieve it; never withhold an obvious answer merely to stretch watch time.
- Give each numbered method a distinct viewer situation or tradeoff and a bridge explaining why the next option matters. Verify the number; do not pad.
- Make visual changes reveal results, direct attention, clarify comparisons, or show progress. Specify the object/action rather than generic 'zoom here' instructions. For visual-hook review, deliver visible storyboard frames when requested; text descriptions alone are not produced visuals. Use real screenshots for product UI, not generated imitation interfaces.
- Build each demonstration around situation -> action -> verification -> when it fits, adapting naturally rather than repeating a mechanical template.
- Record what was applied and what remains untested in internal notes. Save CJ feedback as preference/recording evidence; audience-performance claims require actual analytics. Never claim research has improved retention before measurement.

## Editorial and document QA

- After changing a method, audit the opening, framing, every chapter, transitions, recap, outro, batch plan, prompts, and screen checklist. Search for retired names and concepts across all artifacts; checking only the edited chapter is insufficient.
- Give every section a distinct job. Do not explain an AI prompt, its advantage, its workflow, and then summarize the identical workflow again. Demonstrations can carry explanation.
- Use one decision recap. The outro should provide closure and a next action, not repeat the full recap immediately again.
- Check sequence: never refer back to an editor, action, or concept the viewer has not yet encountered. Introduce HTML plainly before asking beginners to use it.
- Avoid absolute comparison claims such as templates cannot be branded, AI removes all technical review, or HTML guarantees pixel-perfect rendering. Present a practical starting-point tradeoff, not a false capability limit.
- Keep prompt text separate from spoken narration; mark the entire prompt block as non-spoken, not just its heading.
- Put STOP after the final spoken line of each actual batch. Put transition cards before the chapter they introduce. Pausing speech and stopping recording are distinct actions; explain which one is needed.
- Google Docs is the user-facing recording artifact. Preserve user edits and live formatting: fetch current content and revision, apply targeted replacements or style updates, and read back exact text AND text/paragraph styles. Do not delete/reinsert the whole document for a small change.
- CJ's recording baseline: centered spoken text, 17 pt regular, selective 21 pt bold black emphasis, red non-spoken instructions. Inspect current formatting before changing sizes. Never claim all instructions are red after checking only headings.
- If CJ has finished recording, freeze the performed version. Offer pickups only for meaningful factual/sequence errors; put optional polish into a separately labeled next-version draft.
- Distinguish script QA from performance QA: without footage/audio, do not claim the delivery is natural or the video is good. A completed recording is not audience-performance evidence.
- Topic ideation is allowed when CJ requests it. Label ideas PROPOSED, not validated demand. Give each a viewer problem, payoff, visible proof, and research/readiness gate. Do not invent search volumes or personal experience.

## Pitfalls

- Asking five questions in one message. One per turn — CJ gets overwhelmed and stops answering.
- Re-asking locked calibration (pace, length, audience, format, tone default).
- Turning a "yes I've done this" into an invented story of how he did it.
- Skipping the gap check because the chain "felt complete."
- Treating a changelog announcement as proof the feature works today.
