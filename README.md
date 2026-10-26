# Playback Monkey

Windows video playback software for live event production, with a separate
fullscreen output and Bitfocus Companion / Stream Deck controls.

**Public test release: 1.15.** This is an early evaluation build. Test it with
your own media, monitor setup and audio hardware before relying on it in a show.
Windows x64 with .NET Framework 4.8 is required. There is no installer or code
signature in this release.

## Download and start

Open [Releases](https://github.com/cheddar-sauce/Playback-Monkey/releases/latest)
and download **PlaybackMonkey-1.15-Windows-x64.zip**. Extract the entire ZIP into
a writable folder, then open `PlaybackMonkey.exe`. Keep the `runtime` folder
beside the EXE. The Windows ZIP includes the playback engine and two original
demo clips; no separate VLC installation is needed.

Use **File → Add media** to add videos, JPEGs or PNGs. Select a playlist row to
load Preview, wait for it to finish preparing, then press **TAKE / GO** to put it
on Program. Enable the output and select the destination display in the output
controls. Preview selection does not interrupt Program.

## What you can test

- Preview scrubbing, source screenshots, and In/Out marks with timeline markers.
- Cut, dissolve, fade through color and directional wipes; custom duration and
  an eyedropper for transition colors.
- Independent fullscreen output, monitor/audio selection, crop and canvas
  placement, squeeze, playback speed, and audio delay.
- Hold, Loop, Black and linked Next end actions; JPEG/PNG Freeze or timed cues.
- Half-second picture/audio blackout that pauses at black and blocks auto-next.
- Save/open show files, recovery, keyboard controls and remote control.

Preview stays on the taken cue unless its end action explicitly links Next.
Numbered remote cue buttons always refer to the current playlist row.

## Companion and Stream Deck

Download **PlaybackMonkey-Companion-1.0.0.zip** from the same release. It includes
the custom module, 15-key and 32-key XL control pages, and generic numbered cue
pages. Follow [COMPANION-INSTALL.md](COMPANION-INSTALL.md). A Stream Deck can be
connected through Companion's Surfaces page.

The module was validated with Companion **4.2.6** and app **1.15**. Other
Companion versions have not been verified. This module is supplied here as a
custom integration and is not an official Bitfocus store module.

## Source and builds

**PlaybackMonkey-1.15-Source.zip** contains the application and Companion source.
Extract it to access `app/src` and `companion/src`.

On Windows, run `app/build.ps1` with PowerShell to build the application using
the .NET Framework x64 compiler. Put the `runtime` folder from the Windows
release beside the resulting EXE. Build does not need the show media.

For the Companion module, use Node.js 22 and pnpm: run `pnpm install
--frozen-lockfile`, then `pnpm run build`. Run `pnpm test` for the mocked HTTP
and packaged SDK IPC checks. Generated page presets are in `companion/dist`.
To make a module archive, run `tar -czf playbackmonkey-control-1.0.0.tgz
--transform=s,^pkg,package, pkg` with a tar implementation that supports that
option, or archive the contents of `pkg` under a top-level `package` directory.

## Feedback

Please [open an issue](https://github.com/cheddar-sauce/Playback-Monkey/issues)
with your Windows version, app version, GPU, output resolution/refresh rate,
audio device, media codec/frame rate and steps to reproduce. Describe expected
and actual behavior. See [TESTING.md](TESTING.md) for a rehearsal checklist.
Do not post control keys, private show files or media you cannot share.

Settings, recovery and local diagnostic logs are stored in the current Windows
user's LocalAppData/PlaybackMonkey folder. Diagnostic logs can contain local
media paths; review them before sharing.

## Ownership and third-party software

The application is available for public testing; ownership rights are retained.
See [LICENSE.txt](LICENSE.txt). The Companion module retains its MIT license.
The dynamically loaded VideoLAN runtime and its plugins retain their respective
licenses; upstream source links and license texts are included in the download.

Playback Monkey is an independent project, not affiliated with PlaybackPro,
MITTI, Bitfocus, Elgato or VideoLAN.
