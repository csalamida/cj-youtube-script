# CJ YouTube Script

**An AI-agent skill for writing conversational, recording-ready YouTube tutorials—especially HighLevel walkthroughs.**

Instead of asking an AI to “write a YouTube script” and receiving a polished essay, this skill gives the agent a working process: understand the lesson, build the explanation, make the wording easier to say, prepare the recording instructions, and check the whole script before handing it back.

This repository shares CJ’s current implementation. Affiliates can fork it and adapt it themselves. It is not a generalized presenter profile or a standalone app.

## What is a skill?

A skill is a set of Markdown instructions and reference files that an AI agent loads when working on a particular task. It tells the agent how to approach the task, what to ask, what to produce, and what to check.

This repository contains instructions—not a video editor, an automated publishing service, or executable Google Docs integration. Results depend on your model, available tools, supplied context, and your feedback.

## Who this is for

- HighLevel affiliates creating practical product tutorials.
- Educators explaining software features and workflows.
- Creators who want full scripts that are easier to say aloud.
- People recording screen walkthroughs with their face in a corner (picture-in-picture, or PiP).
- Presenters who prefer recording in short batches rather than performing an entire video in one take.

The examples and defaults are HighLevel-focused. You can adapt the workflow to other subjects, but you must supply the relevant product knowledge and verify the demonstrations.

## What the skill does

### 1. Helps you define the actual video

The skill starts by choosing the type of lesson:

| Video type | What it helps you explain |
| --- | --- |
| How-to | One specific task, start to finish. |
| Complete build | Several connected parts that produce a useful system. |
| Changelog-to-build | What a product update lets someone build or do. |
| Troubleshooting | Why something is not working, how to trace it, and how to retest a correction. |
| Feature explainer | What a feature means, when to use it, and what people confuse it with. |

It guides intake **one question at a time**. Questions establish the viewer, starting point, outcome, example scenario, prerequisites, limits, and next step. Personal experience and opinions must come from the presenter—not from the AI inventing them.

### 2. Builds a lesson, not just a list of talking points

The agent checks what the viewer needs to understand and what the video actually promises to deliver.

Depending on the topic, the structure can be:

- A start-to-finish demonstration.
- A comparison of genuinely different ways to do something.
- A decision framework for choosing an option.
- A sequence of connected steps.
- A diagnostic route through a problem.

For a numbered video, the number must come from useful, distinct content. The agent should not invent extra methods just to reach “five ways.”

The skill also checks that the opening, demonstrations, transitions, recap, and ending teach the same lesson.

### 3. Writes a full conversational script

The goal is wording you can say, not prose that merely looks polished on a page.

The skill directs the agent to:

- Use ordinary words and natural contractions.
- Explain concrete meaning before introducing technical terms.
- Keep speaking units manageable without chopping phrases in half.
- Connect explanations to the demo person, record, or action on screen.
- Cut repeated definitions, formal transitions, and generic takeaway slogans.
- Avoid fake jokes, personal stories, opinions, frustration, or experience.
- Give a clear opening and a useful next step.

A direct introduction such as “In this video, I’ll show you…” is allowed when it quickly names the task and payoff. The skill does not require a clever cold open, manufactured drama, or a sensational hook.

### 4. Runs five whole-script text review passes

Before delivery, the agent should inspect the entire script through these five lenses and save what it found and changed:

1. **Spoken wording:** Does this sound like an explanation, or like a manual?
2. **Speaking units:** Is each line a complete thought that is manageable to say?
3. **Repetition:** Are definitions, warnings, transitions, or conclusions being repeated without adding value?
4. **Screen-action fit:** Do the words match what the presenter is actually showing or doing?
5. **Overall flow:** Does the whole lesson have a clear introduction, useful progression, and practical ending?

The agent must apply the findings. Five reviews without meaningful revisions are not an improvement.

**These are text reviews, not five audio rehearsals.** Your read-aloud reaction remains the final test of whether the wording fits your voice.

### 5. Supports line-by-line trim pauses

When you request trim mode, the skill uses one complete speaking unit per line, ending with `/`.

For example:

> Let’s open the contact and check the email address. /  
> Then we’ll look at the service they selected. /

The slash means:

- Finish the line.
- Pause speaking, but keep recording.
- Look at the next line and continue when ready.
- Do not say the slash aloud.

The gap can be trimmed during editing. It is not a dramatic delivery instruction.

**`STOP — END THIS BATCH` means stop recording completely.** A slash pause and a batch stop are different actions.

Slash notation is optional in the current skill; ask for it explicitly.

### 6. Prepares a recording-ready document

The skill separates what you say from what you do:

| Layer | Purpose |
| --- | --- |
| Spoken script | The words you may say aloud. |
| `DO NOT READ` instructions | What to prepare, show, type, or check. |
| Camera cues | When to show yourself full-screen or share your screen with PiP. |
| Batch boundaries | Where to end a take and prepare the next section. |
| Inline demo values | Exact fictional names, labels, messages, and settings at the point of use. |
| Pre-recording checks | Fixtures, permissions, current controls, and evidence needed before filming. |

CJ’s current formatting uses centered black 17-point narration, selective black 21-point bold emphasis, and red non-spoken instructions. Change those defaults to suit yourself.

The camera cues are explicit:

- **`FULL SCREEN OF YOURSELF HERE`** — presenter only, no screen share.
- **`TALK WHILE SHARING SCREEN HERE (PiP)`** — real screen shared, presenter visible in the corner.

A batch stop does not automatically mean a camera change.

### 7. Keeps the recording information in one scroll

For multi-video Google Docs delivery, the skill calls for the main topic tab to contain the continuous recording surface: script, camera cues, inline values, and setup reference.

Ordinary demo values belong beside the step where they are needed, rather than in a separate tab you must keep switching to. CSV uploads can remain separate files, but the agent should actually create the required assets when its tools allow—not merely tell you to prepare them.

If supporting recording-script copies are retained, they must stay synchronized. Existing presenter edits and completed recording versions should not be silently overwritten.

**This repository does not include the Google Docs automation or authorization needed to carry that out.** Your agent needs suitable tools and access; otherwise use local documents.

### 8. Helps with titles, hooks, and numbered-series ideas

The references guide topic and opening development, including:

- A concrete viewer task and payoff.
- Truthful working titles and thumbnail concepts.
- Spoken opening, short on-screen text, first visual, and demo handoff that agree.
- Genuinely different opening approaches rather than superficial wording variations.
- A clear reason to move from one method or chapter to the next.
- Real product screenshots, or explicitly conceptual illustrations—not fabricated interfaces or results.

Search and recommendation intent are editorial hypotheses, not guarantees. A viral video or a creator’s advice is an input to examine—not proof that the same structure will work for you.

The skill refers to a “Pizza Method” ideation worksheet. That local worksheet is not included; supply your own ideation framework if you want to use that part.

### 9. Protects factual accuracy and demonstration honesty

The skill distinguishes what is prepared from what has actually been observed.

For product tutorials, the agent should:

- Prefer official product documentation for capability claims.
- Flag controls and behaviors that need current-interface checks.
- Require a reproducible example before scripting a staged troubleshooting failure.
- Keep live-result lines behind explicit observation checks.
- Avoid describing a scheduled result as if it already happened.
- Separate a submitted request from a completed workflow, and a completed action from actual delivery.
- Avoid inventing customers, testimonials, earnings, demand, or personal experience.

It is a scriptwriting workflow, not permission to mutate accounts, send messages, or publish videos. Those actions require your authorization and appropriate tools.

### 10. Uses your feedback to improve the writing

Your reaction outranks an automated review verdict. If a line makes you feel like you are giving a presentation, rewrite it.

Keep separate records of:

- Your wording and recording preferences.
- Editorial judgments about a draft.
- Observations from actual footage or audio.
- Audience outcomes from authorized analytics.

An improved script is not automatically proof of improved retention, views, or leads.

## What you can ask it to produce

With the required context and suitable tools, the skill directs the agent to prepare:

- A focused intake brief.
- A full word-for-word rehearsal script.
- Recording notes in the same lesson order.
- Production notes and unresolved checks.
- Camera and screen directions.
- Inline copy-and-type demo values.
- Requested CSV or workbook assets.
- A record of the five text-review passes and applied changes.
- Title and opening options when requested.
- A synchronized recording document when document tools are available.

These are workflow instructions, not bundled software features. No paid model, API connection, browser, image generator, or document integration comes with the repository.

## Quick start

### Download

Use **Code → Download ZIP**, or clone:

```sh
git clone https://github.com/csalamida/cj-youtube-script.git
```

### Load it into your agent

Load `SKILL.md` and the `references/` folder through your agent’s skill system. If your assistant does not support skills, provide the files as instructions and reference context; that is manual use, not an automatic installation.

### Adapt the CJ-specific parts

This is CJ’s existing skill, shared as-is. Replace the presenter name, voice dependencies, pacing, formatting, tool names, and local output paths for your setup.

The following external documents are referenced but **not included**:

- `ai-marketing-team/content-engine/_shared/cj-voice-soul.md`
- `ai-marketing-team/content-engine/_shared/cj-voice-calibration.md`
- `ai-marketing-team/content-engine/_shared/cj-youtube-conversational-english-standard.md`

Supply your own voice profile and standards, or edit those dependencies. Tell the agent explicitly that you are the presenter and it must not invent your opinions, experiences, stories, or speaking mannerisms.

References to related skills, local worksheets, Google Docs tooling, and image-generation routes belong to CJ’s setup. Adapt or replace them. Private scripts, accounts, credentials, worksheets, and voice-evidence records are not bundled here.

### Give it a task

Example starter prompt:

> Use this skill to help me write a HighLevel tutorial about adding contacts. I’m the presenter, not CJ. Use conversational English and ask intake questions one at a time. Give me the complete recording script with `/` trim pauses, Full Screen/PiP cues, and exact demo values inline. Run all five text-review passes and apply what you find. Flag any product behavior or result that still needs testing. Use my voice profile instead of CJ’s external files.

For an existing script:

> Review the entire script using this skill. Find wording that sounds formal, awkward, repetitive, or disconnected from the screen demonstration. Run five full-script text passes, apply the revisions, and explain the important changes. Preserve the demo values, factual boundaries, and recording directions.

## Repository contents

| File | Purpose |
| --- | --- |
| `SKILL.md` | Main intake, drafting, review, and recording workflow. |
| `references/discovery-and-evidence.md` | Discovery hypotheses, analytics interpretation, and evidence limits. |
| `references/numbered-series-hooks.md` | Numbered-series ideation and matched opening packages. |
| `references/numbered-hook-practice.md` | Proposed hook examples and their verification requirements. |
| `references/hook-research-source-audit.md` | Inspected hook sources and adopted editorial checks. |
| `references/practitioner-hook-notes.md` | Bounded lessons from practitioner material and visual-review guidance. |
| `references/creator-script-case-study.md` | Transferable script structures without treating virality as causal proof. |

Some reference examples predate the latest conversational corrections. Treat them as exercises and source notes—not wording that overrides the main skill or your current instructions.

## Limits and final checks

- This is not a standalone application or an automatic video-production system.
- Text review is not audio rehearsal, proof of voice match, or evidence that a demonstration worked.
- Current HighLevel behavior must be checked in the account you will record.
- A script or successful recording does not guarantee retention, reach, leads, or revenue.
- References and creator examples are editorial inputs, not a proven universal YouTube formula.
- Review the script aloud yourself before filming. Your corrections are the final authority.
