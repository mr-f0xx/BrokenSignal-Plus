# BrokenSignal+ v1.0.0

Initial clean firmware-only release for the M5Stack Cardputer ADV.

## BrokenSignal+ identity

- Native 240 × 135 `BROKEN / SIGNAL+` boot artwork matching the repository banner.
- Original Matrix/glitch atmosphere retained.
- Correct RGB565 colors on Cardputer ADV hardware.
- Explicit `NEW BUILD // V1.0.0` marker.

## Fullscreen Now Playing visualizers

- Provides two selectable theme-aware Now Playing interfaces, both designed natively for 240 × 135.
- Animated spinning vinyl, grooves, label, highlights, and tonearm.
- Live smoothed spectrum, volume, shuffle/repeat state, battery, track information, codec, progress, timing, queue position, and transport status.
- Colors automatically follow the selected firmware theme.
- Adds a second `Retro Deck` layout matching the supplied digital-player design: framed status bar, prominent title, codec badges, mode indicators, U-shaped spectrum, dB display, and compact transport footer.
- Restores a simple two-choice Visualizer selector in Settings and persists the selection.

## Stability and flicker control

- No fullscreen framebuffer is allocated, preserving memory for libFLAC and compressed-audio buffers.
- Metadata is refreshed only when the track, station, or theme changes.
- The screen is never cleared during animation.
- Vinyl highlights are erased and redrawn in place instead of repainting the complete vinyl panel.
- Spectrum columns and progress elements update only their own pixels.
- Footer text refreshes at one-second intervals.
- Animated LCD writes are grouped in one transaction.

## Cleaner browser header

- Removes the legacy `H` shortcut marker from every music-browser header style.
- Removes the decorative right-side vertical/diagonal separator visible beside the track counter.
- Keeps the track-position counter intact while freeing visual space around it.

## Radio stability isolation

- Disables fullscreen visualizers throughout Web Radio and Gonic modes.
- Ignores the `V` visualizer shortcut while a radio interface is active.
- Disables PCM spectrum collection before starting network streams.
- Removes the animated spectrum widget from the radio status refresh loop.
- Automatically closes any fullscreen visualizer before entering Web Radio.
- Leaves CPU time, heap, and jitter-buffer bandwidth available to the MP3 network decoder.

## Additional changes from BrokenSignal-Next

- Native local FLAC playback and seeking.
- Stable MP3 web-radio path.
- Gonic/Subsonic integration.
- Ten themes and multilingual menus.
- Clean settings layout without overlapping shortcut helpers.

## Firmware

Flash `BrokenSignal-Plus-v1.0.0.bin` at address `0x0`.

SHA-256: `98281b933474c078383a358741e1abff79347c734189ed70c4aa6a45a56e5c07`

PlatformIO build validated: 54,804 bytes static RAM (16.7%), 1,415,749 bytes flash (42.4%). Physical Cardputer ADV validation is recommended.
