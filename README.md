[![English](https://img.shields.io/badge/lang-English-111111?style=flat-square)](README.md)
[![한국어](https://img.shields.io/badge/lang-%ED%95%9C%EA%B5%AD%EC%96%B4-lightgrey?style=flat-square)](README.kr.md)

# Record Room

**Your songs, your photo as the album cover, played on a cover, a vinyl record, or a cassette tape.**

A one-page music player for when the usual streaming app feels too familiar. Build your own playlist, put any photo you love on the cover, pick the player you like, and save the moment as a moving card.

**▶ Open → https://toddoward.github.io/record-room/**

<img src="qr.png" alt="QR code for https://toddoward.github.io/record-room/" width="140">

<table>
  <tr>
    <th width="33%">Cover</th>
    <th width="33%">LP</th>
    <th width="33%">Cassette</th>
  </tr>
  <tr>
    <td width="33%"><img src="assets/cover.webp" alt="Cover screen" width="100%"></td>
    <td width="33%"><img src="assets/lp.webp" alt="LP record screen" width="100%"></td>
    <td width="33%"><img src="assets/cassette.webp" alt="Cassette tape screen" width="100%"></td>
  </tr>
</table>

<sub>All three clips above were saved with Record Room's own “moving card” feature.</sub>

---

## Why Record Room

- **Your own playlist** — mix YouTube videos, whole YouTube playlists, and MP3 files in one list
- **Your photo is the album cover** — any photo becomes the cover, and the whole screen takes on its colors
- **Your own player** — switch between a cover view, a spinning LP, and a cassette tape
- **Keep the moment** — save what's playing as a 5–15 second moving card — MP4 for Instagram Stories and Karrot — and share it straight from your phone

## Features

### 1. Three players

| Player | What you see |
|---|---|
| **Cover** | Colors are picked from the cover and fill the screen; the rest drift softly in the background |
| **LP** | The record spins; the tonearm swings onto the record when you play and back when you pause |
| **Cassette** | A label printed with your photo and retro stripes in its colors; the tape thickness shifts as the song plays, and the reel with less tape spins faster |

### 2. Add songs

- **YouTube video link** — cover and colors come from the video thumbnail
- **YouTube playlist link** (`list=…`) — the whole playlist is added at once
- **MP3 files** — reads the title, artist, and cover art stored inside the file

### 3. My cover photo

- Upload a photo or paste an image link → it becomes the cover for **every song**, and colors come from that photo
- Tap the photo button at the bottom-right of the artwork; it stays until you change it or tap **기본 커버로** (Default cover)

### 4. Moving card

- Saves the current screen as a 9:16 card: **MP4** (for Instagram Stories and Karrot, where GIF/WebP won't play), animated WebP, or GIF
- Length: **5, 10, or 15 seconds**. MP4 needs a recent Chrome or Safari
- Choose whether to show the playback buttons on the card (off by default, your choice is remembered)
- Share through your phone's share sheet, or download it

### 5. Playback

- In order / shuffle, repeat off / all / one, **지금 섞기** (Shuffle now), volume
- Keyboard: `Space` play/pause, `←` `→` previous/next
- Control from your phone's lock screen
- Laptops and phones held sideways show the artwork on the left and the controls on the right

## Quick start

1. Open **https://toddoward.github.io/record-room/** (or scan the QR at the top with your phone)
2. Tap **＋** and add a YouTube link, a playlist link, or MP3 files
3. Pick **커버 / LP / 테이프** (Cover / LP / Tape) at the top, and optionally set your own cover with the photo button on the artwork
4. Tap **움직이는 카드 저장** (Save moving card) to keep the moment

> The interface is in Korean; labels above are shown with their English meaning.

## Good to know

- **Privacy** — MP3s and uploaded photos never leave your device
- **What's remembered** — your YouTube songs, cover photo, and settings are kept in this browser. MP3s need to be added again after reopening
- **Videos that won't play** — videos whose owners block playback on other sites are skipped
- **“… - Topic” tracks** — YouTube Music's auto-generated tracks often stop after a few seconds; add the official music video or another upload instead (YouTube Premium makes no difference)
- **Cover photo by link** — if the image's server blocks access from other sites, it is fetched through the image relay [wsrv.nl](https://wsrv.nl) (the image link is sent to wsrv.nl)
- **Open it from the web address** — opening the file directly on your computer (`file://`) stops YouTube from playing

## For developers

- `index.html` — the whole app in a single file, no external libraries (only the YouTube player)
- `assets/` — README screenshots · `qr.png` — QR code for the site
- Pushing to `main` publishes to GitHub Pages

## Credits

- Cover color extraction re-implements the same procedure as [trackpic](https://github.com/pic-kn/trackpic) (center 70% · median cut to 25 colors · colors close to the dominant one · 5 colors sorted by brightness)
