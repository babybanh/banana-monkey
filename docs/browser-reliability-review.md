# Browser reliability review — 2026-10-27

## Intent preserved

Keep movement-triggered music and the existing delay. Preserve the sunset default and the sunny tuning option. Relevant history: fa29efa (gesture-bound music), 39ce049 (music delay), 3bbb26d (popup warmup).

## Changes

Decode active short WAV effects before collision and play buffers after a real gesture, retaining HTML audio fallback. Clear stale keys/joystick and stop hidden sound. Defer music and alternate backgrounds until needed; avoid repeated hidden tuning and unchanged HUD updates.

## Validation

7 Node regression tests; production build; desktop Chromium and mobile WebKit lifecycle/play tests; 18-pickup phase progression and restart; alternate background; cold pickup handler 50 ms before and 1 ms after in one mobile WebKit run.

Mobile checks used WebKit on macOS with a 390×844 touch viewport. Cold-pickup fixtures position collectibles at the player and run the normal collision/score/audio path. Playback was checked through running audio contexts and started buffers, not recorded speaker output. These are not physical iPhone/Android tests. Occasional long cold frames also occur with SFX off; repeat on a real phone before treating overall frame smoothness as resolved.

Mobile pickup policy: play only when the selected buffer is already decoded and the audio context is already running. Otherwise omit that pickup sound; never fetch, decode, resume or start an HTML audio fallback in the phone pickup path. Desktop and important event SFX retain their existing fallback behavior.
