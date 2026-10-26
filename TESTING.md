# Public testing

Use a spare output or rehearsal setup. The build is unsigned and has not been
validated on every GPU, codec, Windows release or Companion version.

- Import your media and wait for metadata/preparation. Confirm durations, sound
  routing, clip rate, trims and loop boundaries with the actual files.
- Scrub Preview outside a saved Out, set a new Out, clear trims, then TAKE.
- Try Cut, Dissolve, Fade through color and all wipe directions at several
  durations. Watch the external output for a flash at TAKE and at completion.
- Run looped audio/video through several boundaries and listen for gaps.
- Start a linked sequence, use Blackout during playback, and confirm it fades
  for half a second, pauses at black and does not advance. Restore it.
- With output fullscreen, switch to another app and minimize/restore the
  console from the taskbar. Output should remain visible. Escape/F11 can
  explicitly leave fullscreen; selecting None disables the output.
- Test JPEG/PNG Freeze and timed Next, speed, audio delay and source screenshots.
- Test keyboard controls with different controls focused and Companion with
  both generic numbered selection and GO. Confirm disconnected feedback.
- Save/reopen a copy of your show and confirm its order, paths and trims.

Before this public packaging pass, version 1.15 passed 114 targeted checks for
output protection, stills/screenshots/layout and retained Preview/linked Next.
Those checks are targeted regression evidence, not a guarantee of smooth
playback on all hardware. The public executable is rebuilt from the same
production source, with private development tests excluded.

Known limits: output smoothness depends on source cadence and display timing;
the app cannot promise pixel-perfect output on every device. Forcing a Windows
display mode is subject to driver/display support and does not emulate hardware
EDID. Media support is determined by the included libVLC runtime. Some looped
audio is decoded to PCM during preparation and can use substantial memory.
Media is not embedded in saved show files. Windows is the only supported OS.

To report a problem, include a minimal reproduction and a legally shareable
sample if possible. Keep control keys and private media paths out of reports.
