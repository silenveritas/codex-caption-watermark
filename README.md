# Codex Caption and Watermark

A Codex skill for finishing narrated videos. It works with an existing video or an animation project. Request the full preset or use any of its three features on its own.

| Feature | Result |
| --- | --- |
| Voice-over timing | The edit runs to the end of the supplied recording, and the closing shot follows the final spoken phrase. |
| Boogaloo captions | Burned-in captions in the narration language, with the active word highlighted in yellow. |
| Konon Katanya Sih watermark | A small, translucent `@kononkatanyasih` watermark in the upper left of channel episodes. |

## Origins

This companion skill grew out of the narration and caption rules in our Codex adaptation of Mr omi’s `cartoon-3d-short` workflow. The Konon Katanya Sih watermark is specific to this companion. [Codex adaptation](https://github.com/silenveritas/codex-cartoon-3d-short) · [Original cartoon workflow by Mr omi](https://github.com/mromidev/claude-animated-shorts)

The Boogaloo caption styling draws on the Bang Story caption preset. [Bang Story caption presets](https://github.com/bangtutorial/bang-story/blob/c71651a/src/shared/captions.ts)

## Install

Clone the repo into your Codex skills directory. If an earlier copy is already installed, update that copy or back up any local edits before replacing it.

```bash
skills_dir="${CODEX_HOME:-$HOME/.codex}/skills"
mkdir -p "$skills_dir"
git clone https://github.com/silenveritas/codex-caption-watermark.git \
  "$skills_dir/codex-caption-watermark"
```

Open a new Codex chat, attach the relevant media, and invoke the skill by name.

> Use `$codex-caption-watermark` to add word-highlighted Boogaloo captions to this MP4. Keep the existing edit and audio.

For a new episode, invoke the companion animation skill alongside this one. [Codex Cartoon 3D Short](https://github.com/silenveritas/codex-cartoon-3d-short)

The repository includes Boogaloo Regular for local rendering. [Skill instructions](SKILL.md) · [MIT license](LICENSE) · [Boogaloo font license](assets/Boogaloo-OFL.txt)
