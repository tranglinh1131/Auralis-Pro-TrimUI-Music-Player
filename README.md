# Auralis Pro

A music player for **TrimUI Brick, Brick Hammer, and Brick Pro**, running on **NX Redux** and **NextUI**.

Latest version: **6.19.11**

---

## 🙏 Credits

**Auralis Pro is built on top of the default Music Player by mohammadsyuhada, with a whole set of new features and customization options added on top:**
Thanks to the NextUI and NX Redux developers for creating such amazing apps and OSes <3

---

## Table of Contents

- [🙏 Credits](#-credits)
- [Installation](#installation)
- [Quick Start](#quick-start)
- [Global Shortcuts](#global-shortcuts)
- [Per-Screen Shortcuts](#per-screen-shortcuts)
- [Features](#features)
- [Settings Reference](#settings-reference)
- [Audio Quality](#audio-quality)
- [Your Data](#your-data)
- [Troubleshooting](#troubleshooting)

---

## Installation

Pick **one** package that matches your firmware.

### NX Redux

1. Extract `Auralis Pro.pak.zip` and copy the `Auralis Pro.pak` folder into `Tools` on your SD card.
2. Verify the folder exists:
/mnt/SDCARD/Tools/Auralis Pro.pak
3. Reboot the device and open **Tools → Auralis Pro**.


### NextUI

Extract `Auralis Pro NextUI.pak.zip` into NextUI's `Tools/tg5040` folder.

> Data still lives in `/mnt/SDCARD/.userdata/shared/music-player/` — do not rename
> or delete this folder. Close the old version before opening Auralis Pro.
> The default Menu Prefix for a fresh install is **Auralis Pro**; any custom
> text from an older install is preserved (change it under Settings → Display →
> Menu Prefix Text).

---

## Quick Start

1. Copy your music to the SD card under **`/mnt/SDCARD/Music`**. Keep your
subfolder structure as-is — the app scans everything.
2. Open the app. The first launch takes a little longer while it scans your
library.
3. If the app can't find your music, go to **Settings → Library → Scan Now**.

> **Auto Scan Media** is enabled by default so the app rescans every time you
> open the library. Turn it off if your library is large and rarely changes.

### Supported Formats

 Hi-Res: AIFF, DSF, DFF

 Lossless: FLAC, WAV

 Lossy: MP3, OGG, OPUS, M4A, AAC


Case-insensitive. Raw DSD in DSF and DFF is converted to PCM 176.4 kHz for
playback, but the quality line still shows the original DSD clock; DST-compressed
DFF is not supported. TIFF is an image format, not audio.

---

## Global Shortcuts

Available on every screen.

| Button | Action |
|---|---|
| **L3** | Open **Queue** |
| **R3** | Open **Settings** |
| **SELECT** | Open **Now Playing** (while on a browsing screen) |
| **SELECT** (during playback) | Turn off the screen |
| **SELECT + A** | Lock / unlock the screen |
| **X + ▲** | Play / Pause |
| **X + ▼** | Stop playback |
| **X + ◀** | Back to **Main Menu** |
| **X + ▶** | Open **Search** |
| **START** | Play / Pause (Media button) |
| **Y + ◀** | **BG EXIT** — close the app while playback continues |
| **MENU** (short press) | Open the **Context Menu** for the current page |
| **Vol +/−** | Adjust volume — shows a volume toast |
| **Right stick ▲ / ▼** | Volume up / down on any page — shows a volume toast. Up/Down in Now Playing is unchanged. |

> **On Brick Pro:** `L3` and `R3` are **two separate analog buttons**. This frees
> `L1` / `R1` for Previous / Next and `L2` / `R2` for switching effects / toggling
> lyrics. Don't confuse them with the analog sticks.

---

## Per-Screen Shortcuts

### Now Playing

| Button | Action |
|---|---|
| **A** | Play / Pause |
| **B** | Go back to the page you came from |
| **▲ / ▼** | Volume up / down *(see the Settings option)* |
| **◀ / ▶** | Seek back / forward 5 seconds — hold to seek continuously |
| **L1 / R1** | Previous / next track |
| **L2** | Cycle the **waveform effect** |
| **R2** | Toggle **lyrics** |
| **X** | Toggle **Shuffle** |
| **Y** | Cycle **Repeat** through `Off → All → One`; Repeat One shows a `1` badge on both themes |
| **MENU** | Quick menu: Sleep Timer · Parametric EQ · Import / Export PEQ · USB DAC Auto Power |

In the top-left corner, just below the format/source→output-rate badge, Now
Playing shows the file size, bit depth when available, source sample rate, and
average bitrate.

### Library (top level)

Twenty items across **two horizontal pages** (14+6), **fully reorderable**:

`Folders` · `Albums` · `All Songs` · `Artists` · `Playlists` · `Queue` ·
`FAV Songs` · `Recently Added` · `Most Played` · `Least Played` ·
`Never Played` · `Recently Played` · `Bad Songs` · `Shuffle Songs` ·
`FAV Albums` · `Listening History` · `Familiar Mix` · `Discover Mix` ·
`Daily Mix` · `Random Album`

- **Recently Added** — tracks recently copied to the card, newest first.
- **Most Played / Least Played / Never Played / Recently Played** — the app
automatically counts how many times each track has been played and builds four
lists from those stats.
- **Bad Songs** — a list of tracks you've marked as "not for me" (see below).
- **Shuffle Songs** — one press picks and plays a random batch of tracks (count
and source configured under **Settings → Library**).
- **Random Album** — picks a random album that still has playable tracks and
plays it immediately in track order; it does not touch the Queue manually.

| Button | Action |
|---|---|
| **A** | Open the selected item |
| **A + ▲ / ▼** | **Reorder** items in the menu |
| **◀ / ▶** | Switch columns; going past the edge slides to the adjacent page |
| **A + ◀ / ▶** | Move an item to the next column; can be dragged back and forth between pages |
| **MENU** | **Shortcut** reference · Parametric EQ · Quit App |

### Smart Mix (MVP)

- **Familiar Mix** prioritizes FAV Songs, PlayStats, and listening sessions of
meaningful length within the most recent 512 History records. A short listen
or skip does not disqualify a track.
- **Discover Mix** prioritizes unplayed, rarely played, or long-unplayed tracks;
it tries to keep at most 2 tracks per artist/album, relaxing to 3 and then
removing the limit entirely for small libraries.
- **Daily Mix** uses the Familiar/Discover ratio set under **Settings → Library →
Daily Mix Familiar Share** (default 60%). **Smart Mix Size** sets the track
count (5–100, default 20).
- All three remove duplicate paths, Bad Songs, missing/unreadable files, and
unsupported formats. With no history, Familiar falls back to the whole library
as its pool; Discover uses unplayed tracks. The generated count never exceeds
the number of valid candidates.
- Opening or generating a mix **does not modify the Queue**. `A` plays using the
existing playlist behavior; `Y + Up/Down` adds tracks to the Queue as an
explicit user action.

> The two radio dots in the middle of the **Library** header show which page is
> selected. The default layout is still 14 items on the first page, with **FAV
> Albums**, **Listening History**, the three Mixes, and **Random Album** on the
> second. Hold A + a direction to freely reorder any item across both pages; the
> previous order is preserved when upgrading.
>
> The sort order is remembered.
> `A + ▲ / ▼` in this **menu** reorders the *menu items*. In a *track list*,
> `A + ▲ / ▼` reorders the *list contents*.
>
> The **Most Played / Recently Played** screens show the **play count** right
> next to the track name, so you can see what you've been listening to most.

### Searching for Songs (All Songs, Album, Artist)

| Button | Action |
|---|---|
| **A** | Open / play |
| **B** | Go back |
| **L1 / R1** | Change **sort order** |
| **X + ▶** | Search |
| **Y + ▲ / ▼** | Add the selected track to the **Queue** |
| **Y + R1** | **Favorite** the selected track |
| **Y + L1** | Mark / unmark as a **Bad Song** |
| **Y + R1 / Y + L1** | Also works in Recently Added, Most/Least/Never/Recently Played |
| **R2** | Edit tags of the selected track in a track list |
| **Y + ◀** | BG EXIT |
| **MENU** | Delete Song · Rescan Library · Parametric EQ · Quit App |

> Favorited tracks get a **♪ heart at the end of the track name**, just before
> the `[FLAC]` or `[MP3]` tag. Statistic lists also show the **play count**. `R2`
> edits tags on track lists (All Songs, Album Tracks, Queue, FAV Songs), but not
> on Album/Artist selection lists.

### Queue

| Button | Action |
|---|---|
| **A** | Play the selected track |
| **A + ▲ / ▼** | **Move** a track up / down in the queue |
| **L1 / R1** | Change sort order, or restore the original playback order |
| **X** | Remove a track from the Queue |
| **Y** | Clear the **entire** Queue |
| **B** | Go back |

### FAV Songs (Favorites)

| Button | Action |
|---|---|
| **A** | Play the selected track |
| **A + ▲ / ▼** | **Move** a track up / down in the list |
| **X** | Remove a track from Favorites |
| **Y + X** | **Undo** the last removal |
| **Y + L1** | Clear **all** Favorites |
| **Y + L2** | **Undo** the clear-all |
| **B** | Go back |

> **The order within FAV Songs is the actual order** — the app never re-sorts it
> automatically. This list shows a red heart at the end of each track name; there
> is no `L1 / R1` sort toggle.
>
> **Every delete action can be undone.** A mistaken delete is not a disaster.

### FAV Albums (Favorite Albums)

An **album** list, independent of track favorites. `Y + R1` on an album row in
Albums or Artists → Albums adds/removes the whole album and shows a **red** heart.
`Y + R1` on a track row still only toggles that track's favorite status.

| Button | Action |
|---|---|
| **A** | Open the album and pick tracks to play, like the Albums screen |
| **Y + R1** | Remove the selected album from favorites |
| **X** | Remove the album from the list (does not delete music files) |
| **Y + X** | Restore the recently removed album to its previous position |
| **Y + L1** | Clear the entire favorite album list |
| **Y + L2** | Restore the list from before the clear-all |
| **L1 / R1** | Sort: Default, name, artist, Shuffle, date added |
| **A + ▲ / ▼** | Manually reorder albums, saved immediately |
| **B** | Go back to Library (from a track list, returns to FAV Albums) |

> **Default** is the manual order. Like the Queue, moving with A + ▲/▼ returns
> to Default while staying anchored to the selected album. L1/R1 never overwrites
> the manual order. A single-album undo only exists for the current session; the
> clear-all undo persists across app restarts. Temporarily missing albums are
> hidden, not removed from the store. Albums are identified by folder + album
> name + album artist, so rescanning or deleting the first track of an album
> won't lose the favorite.

### Playlists

| Button | Action |
|---|---|
| **A** | Open or play |
| **L1 / R1** | Change sort order |
| **X** | Delete the selected playlist |
| **MENU** | Rename · Delete · Export to SD card · Remove track from playlist · **Create from every folder** · Parametric EQ · Quit App |
| **Y + R1** | Favorite a track (on the playlist detail screen) |
| **B** | Go back |

> **Create from every folder** is a handy trick: it creates a playlist for
> **each subfolder** of `/Music` all at once, giving you ready-made playlists by
> artist or by album.

### Folders (file browsing)

| Button | Action |
|---|---|
| **A** | Open folder / play |
| **B** | Go up to parent folder |
| **Y + R1** | **Favorite** the selected track |
| **Y + ▲ / ▼** | Add to Queue |

### Shared track-list controls

These buttons are available in **All Songs, Album, Artist, Bad Songs**, and the
statistic lists:

| Button | Action |
|---|---|
| **Y + R1** | **Favorite** the selected track |
| **Y + L1** | Mark / unmark as a **Bad Song** (a track that's "not your thing") |
| **R2** | Edit the selected track's tags; works in **All Songs, Album Tracks, Queue, Favorites** (writes directly to the music file) |
| **MENU → Delete Song** | **Delete the track** from the SD card: the first press only asks (showing the track name), press again **within 7 seconds** to actually delete |
| **Y + ▲ / ▼** | Add to Queue |
| **L1 / R1** | Change sort order |

> **Bad Song** is different from **Favorite**: Favorite means "keep this around,"
> Bad Song means "skip this one." Marked tracks live in the **Bad Songs** section
> of the Library; to remove the label, just press `Y + L1` on that track again.
>
> **Track deletion has a confirmation step**, so you can't accidentally delete:
> the first press only shows a message with the track name, and a second press
> actually deletes it. The app rescans the library afterward.

### Main Menu

Five items: `Resume` · `Library` · `Online Radio` · `Podcasts` · `Settings`

| Button | Action |
|---|---|
| **A** | Open the selected item |
| **B** | Exit the app |

### Settings

Settings is split into **8 tabs**, each grouping related options:

`Timers` · `Audio` · `PEQ` · `Lyrics` · `Display` · `Library` · `Appearance` ·
`System`

| Button | Action |
|---|---|
| **A** | Select the current row |
| **◀ / ▶** | **Switch tabs** |
| **L1 / R1** | Change the value of the current row |
| **A (hold) + ◀ / ▶** | **Reorder the tabs** |
| **B** | Go back |

> **System** is a separate tab to avoid accidental taps: it contains Reset Sort
> Order (restore everything to defaults) plus **Check for Update** and **Change
> Log** (see [Updating the app](#updating-the-app-check-for-update--change-log)).

### Radio

| Button | Action |
|---|---|
| **A** | Play the selected station |
| **B** | Go back |

### Podcast

| Button | Action |
|---|---|
| **A** | Open / play / follow |
| **B** | Go back |
| **X + ▶** | Search podcasts |

### Shortcut Reference

The app includes a **Shortcut** page right in the Library menu. Open it any time
to review the button map without needing to visit the web.

---

## Features

### Library

- Automatically scans every subfolder of `/Music` and builds a fast index.
- Twenty items across two pages (14+6): **Folders · Albums · All Songs · Artists ·
Playlists · Queue · FAV Songs · Recently Added · Most Played · Least Played ·
Never Played · Recently Played · Bad Songs · Shuffle Songs · FAV Albums ·
Listening History · Familiar Mix · Discover Mix · Daily Mix · Random Album**.
Every item can be dragged between the two pages with `hold A + arrow`.
- **Listening stats**: the app automatically counts plays per track and builds
four ready-made lists — Most Played / Least Played / Never Played / Recently
Played — with play counts shown next to each track name.
- **Bad Songs**: mark tracks that aren't your thing with `Y + L1` and review them
in their own section.
- **Smart Mix**: Familiar prioritizes favorites/frequent listens; Discover
prioritizes unplayed/long-unplayed tracks with artist/album diversity; Daily
Mix blends them at an adjustable familiar ratio. Each generation is a temporary
list that never modifies the Queue. Mix Size and the Daily Mix ratio live under
Settings → Library.
- **Shuffle Songs**: one press plays a random selection; choose the pool (artist
/ album / playlist) and how many tracks per press in Settings.
- **Random Album**: picks and immediately plays a random album that still has
readable tracks.
- Many sort modes: name A–Z (correct Vietnamese diacritic ordering), artist,
album, year, date added, reverse, random. Entering an album defaults to **disc
/ track** order.
- The track number column in albums is always **1, 2, 3…** in the displayed
order, never scrambled by sorting.
- Quick search in every list: type the whole word/phrase in the title, or keep
using the initials syntax; you can also add artist initials after a space.
- **Delete tracks** from the SD card right in the app (with a two-step
confirmation).
- **Edit tags** with `R2`: title, artist, album, year — written directly to the
music file.
- Reset all sort orders to defaults (Settings → System).

### Favorites

- Mark with **`Y + R1`** anywhere there's a track list, including file browsing.
- The list is **preserved** after every library rescan.
- Reorder manually with `A + ▲ / ▼`.
- Deleting a single track or the whole list — **both are undoable**.

### Listening History

Library → page 2 → **Listening History** opens your session history, newest
first, grouped by date. Each session records a metadata snapshot (title/artist/
album), start time, path, and the **actual decoder duration in the PLAYING
state**; Pause time doesn't count and seeking doesn't add time. A session is
recorded when a track is left/stopped — no need to reach 70% like PlayStats
does. History keeps up to 10,000 sessions; the UI loads only 40 sessions per
page to avoid loading a large file all at once. Date headers are for grouping
only and do **not** show daily totals.

| Button | Action |
|---|---|
| **A** | Replay the selected session/track if the file still exists |
| **Y + Down / Up** | Add the track to the end of the Queue / Play Next |
| **R2** | Open the Tag Editor if the file is still accessible |
| **X** | Delete the history record, not the music file |
| **Y + X** | Undo a single-record deletion, restoring it to its exact position |
| **Y + L1** | Clear all history |
| **Y + L2** | Restore history after a clear-all; newly created sessions are kept |
| **L1 / R1** | Older / newer page (40 sessions per page) |
| **MENU → Export Listening History** | Export CSV to `/mnt/SDCARD/Listening History.csv` |
| **B** | Return to Library |

History is stored at
`/mnt/SDCARD/.userdata/shared/music-player/listening-history.v1.dat`. If the file
is moved/deleted, the metadata snapshot still displays; playback/tag actions
report the missing file safely. Daily statistics aren't enabled yet, so there are
no daily hour/play totals.

### Sorting Albums and Album Tracks

In **Albums**, **Artists → Albums**, or an album's track list, hold **A + ▲ / ▼**
to move an item/track up or down. The order is saved per album/artist and does
not depend on the library's temporary indices; it stays correct after a rescan.
If another sort mode is active, the first move takes the currently visible order
as the manual order and keeps it from there — just like Queue reordering.

### Queue

- Add tracks from any list with `Y + ▲ / ▼`.
- Reorder playback with `A + ▲ / ▼`.
- Restore the exact original playback order.
- Remove a single track or clear everything.

### Playlists

- Create, rename, and delete playlists.
- Add and remove tracks within a playlist.
- **Import / export `.m3u`** to move between devices.
- **Bulk-create** playlists from every subfolder.

### Parametric EQ

- **31 frequency bands** (20 Hz – 20 kHz, international standard), each
adjustable with left/right, press-and-hold, or the analog stick for fast
movement.
- **10 profiles**, each saved independently — experiment without losing settings.
- Enable / disable EQ.
- **Auto-bypass when a DAC is connected** — avoids processing audio twice.
- **Auto gain compensation** to prevent clipping when boosting bands.
- **Import / export** in TP35 text format, placed in the same `Music` folder.

### Lyrics (karaoke)

- Toggle lyrics with `R2` right on Now Playing.
- Automatically fetches lyrics by title and artist from lrclib.net — **any
language**: Vietnamese, English, K-pop, J-pop… if it's online, it's fetched.
- Prefers **time-synced lyrics** (true karaoke style, lyrics follow the beat);
if only plain lyrics are available, they're evenly distributed across the
track duration.
- When multiple versions exist (different cover artists), the app opens a
**picker** so you can choose your preferred one.
- The full-screen lyrics page supports **text size** and **lyric offset**
adjustments under Settings → Lyrics.
- **Fetch All Lyrics**: pre-fetch lyrics for the whole library in one go
(requires network), so offline playback has lyrics ready.
- **Cached** — no network needed on subsequent views.

### Cover Art

- Reads embedded art from music files and caches it for fast display.
- **Full-screen cover** mode.
- Clear the cache when the card fills up (button in Settings, showing current
size).

### Radio & Podcast

- **Radio**: a built-in station list plus your own stations; **search stations
by name** with `X + ▶`.
- **Podcast**: search, follow, download, and play episodes.

### Sleep Timer & Automation

- **Sleep Timer**: stop playback or quit the app after a set duration.
- **Auto Quit After Silence**: quit after N minutes of silence.
- **Auto Screen Off**: turn off the screen during playback.
- **Auto return to Now Playing**: return to the playback screen after a period
of inactivity.
- **BG EXIT**: close the app while playback continues, and reopen right where
you left off.

### NXT Retro Keyboard

The in-app keyboard uses the NXT Retro layout, with Vietnamese Telex and six
manually selectable languages: **Latin (default), Vietnamese, ไทย, 日本語,
한국어, Русский**. The language is remembered for future launches. Press **MENU**
to quickly toggle between Latin and the most recently selected non-Latin
language; select the language code key in the bottom-left (LAT/VI/TH/JP/KR/RU) to
choose another language with A or R1. The keyboard background automatically uses
the color/image set for Settings; the Search prompt uses a smaller size to fit
fully. The keyboard font uses Auralis Pro's default MiSans at its original
weight, not synthetic bold.

| Button | Action |
|---|---|
| **D-Pad / analog** | Move the cursor |
| **A** | Type the selected key |
| **B** | Backspace before the cursor; when the input is empty, Back out. In the language panel, B returns to the keyboard |
| **X** | Space |
| **Y** | One-shot Shift |
| **L1** | Caps Lock on/off |
| **L2 / R2** | Move the input cursor left / right to edit mid-content |
| **R1** | Confirm and accept the input |
| **MENU** | Quick toggle Latin ↔ Vietnamese |
| **PLAY / Start** | Cancel |
| **SELECT** | Confirm and accept the input |
| **TAB / ← / ENTER / CANCEL** | Tab, delete one character, confirm, or cancel — the on-grid keys |

> Telex `s/f/r/x/j`, `w`, `k`, `t`, `dd` still work. The diacritic for `uâ` goes
> on **â** (e.g. `tuaans` → `tuấn`). Repeating a transform key undoes the
> diacritic/structure while inserting the just-typed character, e.g. `Aurralis`
> → `Auralis`. The on-grid **←** key deletes one full Unicode character per
> press; L2/R2 let you position the cursor mid-content.

### Interface

- **Per-page theming**: all 6 app pages (Now Playing, Settings, Library, Radio,
Podcast, Browse) support custom background color, background opacity, highlight
row color, and highlight row text color — Settings → Appearance.
- **Sample wallpapers**: 30 pattern images in total; bg08, bg10, and bg14–bg23
are unchanged, while the other 18 are new patterns/line designs. Each ZIP
package includes a `LICENSE` file.
- **Menu Prefix**: add custom text to the title bar; the new default name is
`Auralis Pro`, and existing settings files that still store the old `Trang
Linh` label are updated automatically.
- **Full-screen Cover Art**.
- **Auralis No-Cover Color**: choose a dedicated background color for tracks
without cover art; the color background is overlaid with a blurred glow from
the default red vinyl image, while the square vinyl stays clearly visible in
the center.
- **Show Up Next**: view the upcoming track list.
- **Now Playing Hints**: toggle the keycap strip on the Auralis interface;
StockOS always shows keycaps.
- **Repeat**: tap `Y` to cycle `Off → All → One`. Repeat All plays through the
list then loops from the start, also returning automatically played tracks to
the Queue; Repeat One shows a `1` badge on both Auralis and StockOS.
- **Now Playing Theme**: choose the current Auralis look or a StockOS-style look;
Auralis is the default.
The StockOS style shows the album and file info as plain text (format · size ·
bit depth · sample rate · bitrate); the title wraps to at most 2 lines and
scrolls horizontally if longer. All metadata/time text is white; buttons are
white-outlined, with L3/L1/Start/R1/R3 hints on a blurred backdrop, progress
advances with time with a mask-capped head, and Spectrum is 32 columns wide.
**StockOS Full-screen Cover Art**: On keeps the background vivid; Off blurs the
background and darkens the middle/lower area with an adjustable elliptical dome
via **StockOS Dome Strength/Size**. Strength has a stronger effect on darkness;
Size ranges 50–200%, from a low narrow dome to one nearly covering the screen.
A subtle color glow remains outside the dome; **StockOS Blur Strength/Spread**
stays independent. Display → **StockOS Full-screen Cover Art** keeps the image
vivid when On.
- **Confirm album replacement**: asks before overwriting.

### Updating the App (Check for Update & Change Log)

Open **Settings → System → Check for Update** (requires Wi-Fi):

1. The app checks for the latest version — downloading only **a few dozen bytes**
of version info, not the full installer.
2. Already on the latest version → a popup says **Already on the latest
version**, and you're done.
3. A newer version exists → a **Download** screen appears with a progress bar,
and the update installs over the old version automatically when finished; a
popup says **Installed — restart the app**.
4. Close and reopen the app to run the new version. **Your data, settings,
favorites, playlists, lyrics, radio stations… all stay intact** through the
update.

> If music is playing during an update, the current track keeps playing to the
> end — the new version only takes over on the next app launch.

**Change Log** right next to it: open it to see what was added/fixed in this
version, no guessing required.

---

## Settings Reference

How to use: **A** selects a row, **◀ / ▶** switches tabs, **L1 / R1** changes the
value, **B** goes back. Each tab is labeled with the exact name shown in the app.

### Timers tab (scheduling & automation)

| Item | Description |
|---|---|
| **Auto Screen Off** | How long before the screen turns off while **playing** |
| **Screen Lock Action** | How to unlock the screen: `Select + A` (default) · `Select` · `Screen off + media` |
| **Auto return to Now Playing** | How long without input before returning to the playback screen, so `Auto Screen Off` can turn the screen off. `0` = off |
| **Sleep Timer** | Stop (or quit) after a set duration |
| **Sleep Timer Quits App** | When the Sleep Timer expires, **quit the app** instead of just stopping playback |
| **Auto Quit After Silence** | Quit the app after how many minutes of silence |

### Audio tab (sound & USB-C port)

| Item | Description |
|---|---|
| **Balance** | Balance between game audio and music audio |
| **L/R Balance** | Left / right channel balance |
| **Bass Filter** | Low-pass filter (Off or various Hz levels) |
| **Soft Limiter** | Volume limiting to prevent clipping |
| **Sample Rate** | Follow the device, or **match the file's exact rate** |
| **Resampler Quality** | `Off` skips SRC when the source rate matches the output rate; if they differ, rate conversion is still needed and the app uses `Fast` to keep timing correct. `Fast` uses less CPU/lower latency; `Best` uses more CPU to reduce filter distortion |
| **Audio Buffer** | 1024–16384 frames. Larger buffers can reduce drop-outs under high load but increase control/track-change latency and use more RAM; applies from the next track |
| **Clear Album Art** | Clear the cover art cache — shows current size |
| **Clear Lyrics** | Clear the lyrics cache — shows current size |
| **Bit-Perfect DAC Output** | Request that the USB DAC output at the source rate when supported; bypasses EQ |
| **USB-C Port** | `Charge` or `Host` (for DAC / USB devices) |
| **DAC Port Auto Power** | Automatically power the port when a DAC is connected |

### PEQ tab (equalizer)

| Item | Description |
|---|---|
| **Parametric EQ** | Open the EQ editor |
| **EQ On / Off** | Enable / disable EQ |
| **EQ Paused For DAC** | Paused because a DAC is connected (no action needed) |
| **Profile** | Switch between 10 profiles |
| **Import PEQ** | Load a profile from a text file in the `Parametric EQ` folder |
| **Export PEQ** | Write the current profile to a text file |

### Lyrics tab

| Item | Description |
|---|---|
| **Lyrics Page Text Size** | Text size on the full-screen lyrics page |
| **Lyrics Page Delay** | Shift lyrics earlier / later relative to the track (in seconds) |
| **Lyrics Screen Off** | Allow the screen to turn off even while lyrics are open |
| **Fetch All Lyrics** | Automatically fetch lyrics for the **entire** library in one go (requires network), so offline playback needs no fetching later |

### Display tab

| Item | Description |
|---|---|
| **Show Menu Prefix** | Enable / disable the custom title-bar text |
| **Menu Prefix Text** | The content of that text |
| **Full-screen Cover Art** | Cover art fills the screen |
| **Now Playing Up/Down** | Whether `▲ / ▼` on Now Playing controls **volume** or **track skipping** |
| **Now Playing Hints** | Show the keycap strip on the Now Playing screen |
| **Now Playing Theme** | Choose the Auralis or StockOS look |
| **Show Up Next** | Show the upcoming track list |

### Library tab

| Item | Description |
|---|---|
| **Auto Scan Media** | Rescan the library every time you open the app |
| **Scan Now** | Rescan immediately |
| **Confirm Album Replacement** | Ask before replacing an album |
| **Shuffle Rules** | Choose the pool for the **Shuffle Songs** button: which artists / albums / playlists to draw from |
| **Shuffle Limit** | How many tracks one press of Shuffle Songs plays and adds to the queue (10–1000) |

### Appearance tab (colors)

Choose colors for each app screen — each row is one page (Now Playing, Settings,
Library, Radio, Podcast, Browse):

| Item | Description |
|---|---|
| **6 page color rows** | Open a color picker for each page, including **background opacity** |
| **Active Item (highlighted row background)** | Background color of the selected row |
| **Active Item Text** | Text color on the selected row — set to `Auto` to let the app pick a readable color, or enter a custom color |

> The color picker has an **analog rotary dial**: rotate left/right to change hue,
> up/down to change brightness — like a color wheel on a phone…

### System tab (maintenance)

| Item | Description |
|---|---|
| **Reset Sort Order** | Restore all sort orders (menus, tabs…) to defaults |
| **Check for Update** | Check for and install a new version over Wi-Fi (see below) |
| **Change Log** | See what changed in this version |

---

## Audio Quality

### Automatic output selection

The app does **not** hard-code an audio device. It selects based on the active
output:

| You're listening on | The app plays through |
|---|---|
| Built-in speaker | Built-in speaker |
| **Bluetooth** headphones | Bluetooth headphones |
| **USB DAC** | USB DAC |

When multiple outputs are connected, the priority is **wired USB DAC →
Bluetooth → speaker**. The app switches routes automatically. When switching from
speaker → DAC/Bluetooth, it carries over the current level; when the last
external route is lost and it returns to the speaker, the speaker starts at 10%
to avoid startling you. Before changing PCM, the old route is temporarily lowered
to 10%. If the external PCM isn't ready, the app stays silent and retries the
selected route; it never falls back to the speaker at an unknown level.

### Bit-Perfect and output sample rate

The `44.1→48kHz` badge shows the source rate → the actual rate that SDL/PCM
opened, not the DAC's advertised rate. **Bit-Perfect DAC Output** only takes
effect when a USB DAC is the active sink. When enabled, Auralis requests PCM to
open at the track's exact sample rate (44.1 kHz opens at 44.1 kHz); the software
EQ is bypassed. Your DAC/driver must support that rate for PCM to open correctly.

The reason pre-v6.10.0 builds showed the `44.1→48kHz` badge even with Bit-Perfect
enabled: the target calculation path called `AudioMgr_pickRate()`, which
intentionally returns the clock of the running mixer in `/tmp/nx_audio_sink`
(usually 48 kHz) and ignores the desired rate. So the decoder stream was set to a
48 kHz output and resampled 44.1→48 itself before writing to the buffer; PCM was
never asked to open at 44.1 kHz. Version 6.10.0 bypasses the shared-rate path for
Bit-Perfect and requests the source rate at the moment `Player_play()` opens the
device.

Fixed and working perfectly.

---

## Your Data

| Content | Location |
|---|---|
| Music library | `/mnt/SDCARD/Music` |
| Favorites, FAV Albums, Listening History, manual Album/Track order, keyboard language, Bad Songs, playlists, listening stats, settings | `/mnt/SDCARD/.userdata/shared/music-player/` |
| Cover art and lyrics cache | `/mnt/SDCARD/.cache/` |
| User-added radio stations | In the settings folder, file `stations.txt` |

**To move devices or back up:** copy the entire
`/mnt/SDCARD/.userdata/shared/music-player/` folder to the new device — favorites,
FAV Albums, Listening History, manual Album/Track order, keyboard language, Bad
Songs, playlists, listening stats, and all settings come along.

**SD card full:** go to **Settings** and clear the cover art / lyrics cache.

---

## Troubleshooting

### The app doesn't see my music

1. Make sure your music is in `/mnt/SDCARD/Music`.
2. **Settings → Scan Now**.
3. Restart the app to be sure.

### No sound

1. Adjust the system volume with Vol +/−.
2. If a DAC is connected: **Settings → USB-C Port** must be set to `Host`.
3. Try disabling **Bit-Perfect DAC Output** — some DACs don't accept the exact
sample rate.
4. Close and reopen the app. If multiple music apps are open at once, close all
but one.

### A favorited track disappeared

This shouldn't happen. If it does, check that
`/mnt/SDCARD/.userdata/shared/music-player/` is still intact — don't delete it.

### The app won't start after installation

1. Check that the folder name is correct.
2. Try the other package (use whichever one works).
3. Reboot the device and reopen from the Tools / Apps menu.

### App update reports an error

1. Make sure Wi-Fi is on and connected.
2. **Check for Update** only downloads a few dozen bytes, so it should open
quickly — if it takes too long, your connection is weak.
3. Read the popup carefully: a network error means try again, while "Already on
the latest version" means you're up to date and nothing needs doing.

### Two music apps open at once

Close everything except **Auralis Pro**. The default NX Redux Music Player and
Auralis Pro should not run together.

---

## Info

- **Author:** Trang Linh
- **Hardware:** TrimUI Brick Pro
- **Supported firmware:** NX Redux · NextUI · StockOS
- **Version:** 6.19.11

---
