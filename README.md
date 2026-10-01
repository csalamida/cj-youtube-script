# CJ YouTube Script

CJ’s current AI-agent skill for conversational, recording-ready YouTube tutorials, especially HighLevel walkthroughs.

## What it includes

- Guided intake, one question at a time.
- Full tutorial scripting and whole-lesson continuity checks.
- Five text-rehearsal passes for natural wording, speaking units, repetition, screen-action fit, and overall flow.
- Optional `/` trim pauses after complete speaking units.
- Recording batches, Full Screen/PiP cues, and inline demo values.
- Factual checks and evidence gates for product demonstrations.
- Six reference files covering hooks, numbered series, research, and discovery.

## Get it

Clone this repository, or use **Code → Download ZIP**:

```sh
git clone https://github.com/csalamida/cj-youtube-script.git
```

Load `SKILL.md` and its `references/` folder into your AI agent’s skill system. If your tool does not support skills, provide the Markdown files as instructions and context. Tool-specific capabilities are not included.

## Adapt it yourself

This is the existing CJ-specific skill, not a generalized affiliate edition. Fork it and adapt the presenter name, voice, pacing, recording format, tool names, and output paths for your own setup.

The skill refers to these external voice documents, which are **not included**:

- `ai-marketing-team/content-engine/_shared/cj-voice-soul.md`
- `ai-marketing-team/content-engine/_shared/cj-voice-calibration.md`
- `ai-marketing-team/content-engine/_shared/cj-youtube-conversational-english-standard.md`

Replace those dependencies with your own voice profile and writing standards. Local worksheet paths, related skills, Google Docs tooling, and image-generation routes mentioned in the files belong to CJ’s setup; adapt them or supply your own. No private scripts, accounts, credentials, or source worksheet are included.

## Important limits

Text review is not audio rehearsal or proof of voice match. Verify current product behavior before recording result claims. The skill does not guarantee retention, reach, leads, or video performance. Research references are editorial inputs, not guarantees.
