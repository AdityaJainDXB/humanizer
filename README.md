# Humanizer

A skill for Claude that makes the text it writes sound like a person wrote it.

AI writing is easy to spot once you know the tells: "delve", "a testament to", "not just X, it's Y", lists of three adjectives, a bold label on every bullet, an em dash in every other sentence. Wikipedia's editors keep a long list of these in their guide [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing). Humanizer turns that list into a checklist Claude runs over every essay, email, post or speech before handing it to you.

## What it does

When the skill is on, Claude:

1. Works out who will read the text and matches the tone (formal for school or work, relaxed for personal stuff).
2. Writes in plain, specific words instead of filler.
3. Checks the draft against about 30 known AI patterns and rewrites anything that matches.
4. Reads it back for rhythm, mixing short and long sentences.

Here's the difference:

> Before: Nestled in the heart of Dubai, our studio serves as a vibrant hub of creativity, showcasing innovative, high-quality, and affordable designs, highlighting the transformative power of 3D printing.
>
> After: We're a small 3D printing shop in Dubai. We print custom parts, gifts and prototypes, and most orders ship within a week.

The full checklist is in [`humanizer/SKILL.md`](humanizer/SKILL.md).

## Install it

### Claude app (claude.ai, desktop or mobile)

1. Download this repo: click the green **Code** button, then **Download ZIP**.
2. Unzip it. Inside you'll find a folder called `humanizer` with a `SKILL.md` file in it.
3. Zip just that `humanizer` folder on its own, so the zip has `humanizer/SKILL.md` at the top.
4. In Claude, open **Settings → Capabilities** and make sure Skills are turned on.
5. Under Skills, choose **Upload skill** and pick your zip.
6. Turn the skill on.

Menu names move around now and then. If you can't find them, search "skills" in the [Claude help center](https://support.claude.com).

### Claude Code

Personal install (works in every project):

```bash
git clone https://github.com/AdityaJainDXB/humanizer.git
mkdir -p ~/.claude/skills
cp -r humanizer/humanizer ~/.claude/skills/
```

Project install (shared with everyone working in one repo):

```bash
mkdir -p .claude/skills
cp -r /path/to/humanizer/humanizer .claude/skills/
```

Restart Claude Code and the skill is picked up automatically.

### Claude API

Upload the `humanizer` folder through the Skills API, then pass its skill ID in your requests. The [Agent Skills docs](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview) cover the steps.

## Use it

You don't need a special command. Ask Claude to write or fix something:

- "Write a caption for this photo of my new speaker build."
- "Rewrite this paragraph so it doesn't sound like ChatGPT."
- "Draft an email to my teacher asking for an extension."

Claude loads Humanizer on its own when the task is writing you'll send or publish. To be sure, say "use the humanizer skill".

## Make it yours

Open `SKILL.md` and edit it. Add words you're sick of seeing, remove rules you don't care about, or swap in a before-and-after example from your own writing. Then reinstall the folder.

## A fair warning

This skill is about writing better, not about hiding AI use. If your school, job or publisher asks you to disclose AI help, disclose it. The Wikipedia guide itself says these patterns are signs, not proof, and plenty of humans write this way too.

## Credits

The patterns come from [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) by WikiProject AI Cleanup, shared under CC BY-SA 4.0. This repo describes those patterns in its own words.

Made by [Aditya Jain](https://github.com/AdityaJainDXB).

## License

[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/), to match the Wikipedia source.
