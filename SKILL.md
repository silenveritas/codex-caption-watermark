---
name: codex-caption-watermark
description: Finish narrated videos with an edit timed to the supplied voice-over, word-highlighted Boogaloo captions, and the Konon Katanya Sih watermark. Use for this finishing preset or for an individual request involving these captions, branding, or voice-over timing.
---

# Codex Caption and Watermark

Use this skill with an existing video or an animation project. For a full preset, establish the voice-over timeline before locking shots, burn in captions, and apply the watermark to Konon Katanya Sih episodes. For a request limited to one feature, apply only that feature. A caption-only or watermark-only pass preserves the existing edit and audio. Respect explicit caption, branding, and runtime overrides.

## Voice-over as the edit master

1. Transcribe the supplied recording before planning shots. Align each spoken word to its actual start and end in seconds. Check names against the draft, listen through long pauses, and stage the words in the recording. Use one cue list for captions and animation. A compatible cue format is `[{"w":"Listen","s":0.12,"e":0.42}]`. If automatic timings are unavailable, align the words against the recording and verify them by listening.
2. Measure the full recording, including its ending silence. At a constant frame rate, set the frame count to `ceil(audio samples × fps / sample rate)`, using samples per channel and the exact frame rate. The last frame index is one less than that count. For example, 48,240 samples at 48 kHz span 1.005 seconds. At 30 fps the edit needs 31 frames, numbered 0–30. Keep the full recording in the mix.
3. Match the closing shot and any call to action to the final spoken phrase. Finish on the frame containing the end of the recording. Add a separate epilogue only when requested.

## Boogaloo captions

Burn captions into the picture in the language of the voice-over. Load the bundled [Boogaloo Regular font](assets/Boogaloo-Regular.ttf) at its native weight and include its [font license](assets/Boogaloo-OFL.txt) when copying it into a project. In Remotion, copy both files into the project, load the font via `FontFace` from a `staticFile()` URL, and wait for it to finish loading before measuring text or rendering any frame.

- Use uppercase white text (`#FFFFFF`), a yellow active word (`#FFC93C`), a dark outline (`#1F1D1A`), and a transparent background. Center at the bottom with a margin of about 7% of frame height. At 1080 × 1920 use 71 px type, a 5 px outline, 77 px between baselines, and a maximum text width of 773 px. Scale vertical measurements with frame height and the width limit with frame width. Wrap at two lines using the loaded font's metrics. [Original caption preset](https://github.com/bangtutorial/bang-story/blob/c71651a/src/shared/captions.ts)
- Group up to five words or about 30 characters. Close the current group at a sentence ending, a pause longer than 0.45 seconds, or a shot change. Display the group together and move the highlight at each word's onset. End the group at the earliest of the next group's onset, 0.6 seconds after the last word ends, the shot boundary, or the end of the video.
- Check spelling against the recording and draft, especially character and place names. Remove performance directions and vocal tags. Use the same cues for preview and export. Composite text above scene effects so lens blur and grading leave it legible.

## Konon Katanya Sih watermark

For Konon Katanya Sih episodes, burn the exact lowercase handle `@kononkatanyasih` into every frame, including transitions. Use Boogaloo Regular at 1.5% of frame height, white at 38% opacity, with a subtle dark shadow. Place its top-left corner 4.5% of frame width from the left and 5.5% of frame height from the top. Apply branding to other projects only when requested.

## Check the exported video

Inspect the opening, a reveal, a shot boundary, and the ending at phone size. Play a spoken passage to check the active-word highlights. Verify that text leaves faces and actions readable and the watermark remains visible on both bright and dark shots. For a voice-over-led edit, compare the exported frame count with the recording-based count and listen to the last phrase for clipping. Check only the features used in the edit.
