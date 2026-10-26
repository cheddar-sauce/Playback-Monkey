# Companion setup

1. Extract `PlaybackMonkey-Companion-1.0.0.zip`.
2. In Companion's **Modules** area, enable/show developer modules if needed and
   use **Import module package** to install `playbackmonkey-control-1.0.0.tgz`.
   Importing a page alone does not install its module. If Companion reports
   **Unknown module**, finish installing this package first.
3. In **Import / Export → Import configuration**, choose either
   `PlaybackMonkey-15-Key.companionconfig` or
   `PlaybackMonkey-32-Key-XL.companionconfig`.
4. Import the single page into a **new empty page**. Create one new connection
   named `monkey`. Do not choose Full Reset or replace an occupied page.
5. Open Playback Monkey. In **File → Controls / I/O**, copy its current control
   key. In Companion's `monkey` connection enter address `127.0.0.1`, HTTP port
   `8099` (or your configured port), and that key. Save and enable the connection.
   Templates start disabled and contain no key. The connection should show OK.
6. Optionally import the numbered Clips pages into other empty pages. Map those
   imports to your **existing monkey connection**, rather than creating copies.
   Alternatively, drag presets from **Playlist → Preview** onto your own buttons.
7. Connect your Stream Deck through Companion's **Surfaces** page and choose the
   imported control page as its startup page.

The 15-key numbered pages cover cues 1–48, twelve per page. XL numbered pages
cover cues 1–48, up to 29 per page. Numbered buttons select Preview only. Wait
for the cue to be ready and press GO separately. Blue indicates Preview and red
indicates Program. A number beyond the current playlist is unavailable.
After reordering a playlist, each button still selects the current row at that
number. It does not identify a particular media file. Review any custom names.

For Companion on another computer, manually enable LAN control in the app and
enter the playback computer's IP address. LAN control uses HTTP and should be
used on a trusted show network. This package changes no firewall or LAN settings.
Keep the control key private and never include it in a shared export.

Blackout fades picture and sound for 500 ms, blocks linked Next, then pauses.
Restore fades back to the previous transport state. Stop is immediate.
Transition actions configure the next TAKE. Mark In/Out changes apply at the
next TAKE. Preview Reset returns to the saved In; it does not clear trims.

401 means the key does not match. A refused GO usually means Preview is not
ready. If a request times out, check Program before pressing again: commands
are not automatically retried. Status refreshes about once a second.

Validated with Companion 4.2.6. If your version has different module import
controls, consult that version's custom/developer module instructions.
