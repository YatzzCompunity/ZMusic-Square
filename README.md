<p align="center">
  <img src="docs/square.png" width="112" alt="">
</p>

<h1 align="center">ZMusic</h1>

> **ZMusic public fork** — maintained by [@YatzzCompunity](https://github.com/YatzzCompunity), based on [Square](https://github.com/Lelonio/Square), originally created by [@Lelonio](https://github.com/Lelonio). This is an independent, unofficial fork—not an official Square release. Upstream and third-party attribution and license notices are retained. ZMusic-specific changes include the app name and package ID, maintainer credit, and disabling upstream self-updates. The main project is licensed under GPL-3.0-or-later; the lyrics view retains its separate AGPL-3.0 notice. See [Licence](#licence).

<p align="center">
  An unofficial Android music client for Spotify Premium and YouTube Music,
  built in Liquid Glass.
</p>

<p align="center">
  <a href="https://github.com/YatzzCompunity/ZMusic-Square/actions/workflows/build.yml"><img src="https://img.shields.io/github/actions/workflow/status/YatzzCompunity/ZMusic-Square/build.yml?branch=main&label=latest%20APK%20build" alt="Latest ZMusic APK build"></a>
  <a href="https://github.com/YatzzCompunity/ZMusic-Square/actions/workflows/build.yml"><img src="https://img.shields.io/badge/download-APK%20artifact-blue" alt="Download APK from Actions artifact"></a>
  <img src="https://img.shields.io/badge/Android-8.0%2B-3DDC84" alt="Android 8.0 or later">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-GPL--3.0--or--later-blue" alt="GPL-3.0-or-later licence"></a>
</p>

<p align="center">
  <a href="#download"><b>Download</b></a> ·
  <a href="#features"><b>Features</b></a> ·
  <a href="#first-launch"><b>First launch</b></a> ·
  <a href="#faq"><b>FAQ</b></a> ·
  <a href="https://t.me/+-XDmbFwz7uBkMjc0"><b>Telegram community</b></a> ·
  <a href="docs/DEVELOPMENT.md"><b>Building</b></a>
</p>

| Player | Lyrics | Effects |
| :---: | :---: | :---: |
| ![The player](docs/screenshots/player-2.png) | ![Synced lyrics](docs/screenshots/lyrics-2.png) | ![The effects panel](docs/screenshots/effects-2.png) |
| **Artist** | **Album** | **Glass settings** |
| ![An artist's page](docs/screenshots/artist-2.png) | ![An album](docs/screenshots/album-2.png) | ![The glass settings](docs/screenshots/glass-3.png) |

## Features

### Two sources, one app

- **Spotify or YouTube Music**, chosen at first launch and switchable in the
  settings. Home, search, the library and the player work the same on both.
- **Spotify**: your own account, with its playlists, library and Connect
  devices. Needs Premium.
- **YouTube Music**: the whole catalogue and the music videos, with no account
  needed. Sign in with Google to bring in your playlists, albums and followed
  artists.

### Player

- The cover or the song's looping canvas video behind the controls.
- Music videos: switch from the song to its video in place, without losing the
  queue or the position, and keep watching in picture-in-picture.
- Radio from any song, and autoplay of similar songs when the queue ends.
- Crossfade between songs, with an option to skip trailing silence.
- Sleep timer: after 5 to 60 minutes or at the end of the song, fading out
  before it stops.

### Audio effects

- Speed and pitch, each on its own, plus reverb.
- Presets, so "slowed + reverb" is one tap on any song.
- Karaoke: turn the voice down.
- Streaming quality that follows the connection, or a fixed one.

### Lyrics

- Synced lyrics, word by word where they exist and line by line otherwise.
- Translation into your language, under the original lines.

### Library and discovery

- Playlists, albums, artists and liked songs. Create, rename and delete
  playlists, add and remove songs, pin favourites, follow artists.
- A home page of shelves made for you, a **New** tab with releases and charts,
  and a **Radio** tab of stations, moods and genres.
- Search, with your recent searches kept (swipe one away to remove it).
- The music already on your phone, in a Local files shelf.

### Offline

- Download playlists, albums and songs, from either source. A song kept by two
  playlists is downloaded once.
- Downloads over Wi-Fi only, and automatic downloads of your liked songs.
- Offline mode: play only what is on the phone.

### Spotify extras

- A **Connect** device: send playback to ZMusic from any other device, and
  control your other devices from it.
- What your friends are listening to.
- Similar playlists at the end of each playlist.
- Song credits: performers, writers and producers.
- What you play is saved to your listening history, as it would be anywhere
  else you listen.
- Spotify links can open straight in ZMusic.

### Android Auto

- Browse playlists and recently played, search by voice, like a song or start a
  radio from the car.

### Look and language

- Every control, the tab bar, the player, the sheets and the menus are made of
  one refracting glass. Blur, refraction and tint are adjustable, with a lighter
  mode for slower phones.
- Eight languages: English, Italian, Spanish, French, German, Portuguese, Hindi
  and Turkish, chosen independently of the phone's own.

## Download

ZMusic APKs are built by GitHub Actions. Open the [Build workflow](https://github.com/YatzzCompunity/ZMusic-Square/actions/workflows/build.yml), choose the latest successful run, then download the `zmusic-dev-<commit>` file under **Artifacts**. The artifact is a universal APK and is retained for 14 days.

These builds are not signed with a release key; they use a debug key and are for testing. The signing key can differ between runs, so Android may require you to uninstall an earlier ZMusic test build before installing a newer one. ZMusic uses its own package ID (`com.yatzzcompunity.zmusic.square`) and does not use Square upstream self-updates; get future builds from this repository. It supports Android 8.0 or later. It is not on the Play Store; see the [disclaimer](#disclaimer).

<details>
<summary><b>The first minutes after installing are slower</b></summary>

Android takes a while to optimise a freshly installed app, and until it does
the interface is noticeably slower. To do it straight away, open the app once
and give it a few seconds, then run this with the phone connected:

```bash
adb shell cmd package compile -m speed-profile -f com.yatzzcompunity.zmusic.square
```

Run before the app has been opened, the command finds nothing to compile.

</details>

## First launch

ZMusic first asks where the music should come from. You can change it later in
the settings.

- **YouTube Music** plays straight away. Signing in with Google, from the
  settings, is optional.
- **Spotify** needs a Premium account and a few minutes of guided setup: you
  sign in, then register a free app of your own in Spotify's developer
  dashboard and paste its client ID. Search and a few other features go
  through Spotify's Web API, which limits requests per app, so with your own
  app the limit is yours alone. The setup walks you through every step.

## FAQ

**ZMusic does not appear in Android Auto.**
Android Auto only lists apps installed from the Play Store. Turn on "Unknown
sources" in Android Auto's developer settings and ZMusic shows up.

**Can I use a free Spotify account?**
No. A free account can sign in, but Spotify only streams to a client like this
one with Premium. YouTube Music works with no account at all.

**YouTube Music search works, but songs do not play.**
YouTube changes how its streams are served every so often. Install the
latest successful build from the Actions artifact, which is usually where the fix is.

## Disclaimer

ZMusic is an independent, unofficial fork based on Square; neither ZMusic nor
Square is affiliated with, endorsed by or connected to Spotify or Google. The
Spotify source re-implements Spotify's protocol, which Spotify's Terms of
Service forbid, and the YouTube Music source uses private endpoints used by its
web client. ZMusic cannot be published on the Play Store, and you use it at your
own risk. There is no warranty of any kind; see the licence.

## Help and feedback

- **ZMusic bugs and feedback**: [open an issue in this repository](https://github.com/YatzzCompunity/ZMusic-Square/issues/new/choose). If the app closed or froze, attach a report from Settings → About → Save a report.
- **Square upstream community and announcements**: [Telegram community](https://t.me/+-XDmbFwz7uBkMjc0) and [official Square release channel](https://t.me/SquareAppOfficial).
- **Square upstream discussions**: [Q&A](https://github.com/Lelonio/Square/discussions/categories/q-a) and [ideas](https://github.com/Lelonio/Square/discussions/categories/ideas). These are for the original Square project, not ZMusic support.

The same two links are in the app, under Settings → About.

## Support

ZMusic is free and has no ads. The [Ko-fi link](https://ko-fi.com/lelonio) is
for Square upstream development and goes to the original maintainer, not ZMusic.

## Credits

| Project | Licence | How it is used |
| --- | --- | --- |
| [librespot](https://github.com/librespot-org/librespot) | MIT | The Spotify engine. `librespot-core`, `librespot-playback` and `librespot-connect` are vendored with local patches. |
| [Spotify Web Playback SDK](https://developer.spotify.com/documentation/web-playback-sdk) | Spotify Developer Terms | Playback for accounts Spotify refuses audio keys, through the listener's own developer app. |
| [Metrolist](https://github.com/mostafaalagamy/Metrolist) | GPL-3.0 | Its InnerTube client, vendored as [`innertube/`](innertube/), because it is published nowhere else. Powers the signed-in YouTube Music library. |
| [NewPipeExtractor](https://github.com/TeamNewPipe/NewPipeExtractor) | GPL-3.0 | Anonymous YouTube Music search and stream URLs. |
| [lossless.wtf](https://lossless.wtf) | n/a | Synced lyrics timed to the word, asked first on both sources. |
| [LrcLib](https://lrclib.net) | n/a | Synced lyrics for the YouTube Music source, over its open API. |
| [Spicy Lyrics](https://github.com/Spikerko/spicy-lyrics) | AGPL-3.0 | The lyrics animation, ported to Compose by [@donutnotnut](https://github.com/donutnotnut) in [#50](https://github.com/Lelonio/Square/discussions/50). |
| [Bungee](https://github.com/kupix/bungee) | MPL-2.0 | Time stretching, fetched at build time. |
| [AndroidLiquidGlass](https://github.com/Kyant0/AndroidLiquidGlass) | Apache-2.0 | The glass material; the catalog components are copied with their notice. |
| [Phosphor Icons](https://phosphoricons.com) | MIT | Every icon in the app. |
| [ebur128](https://github.com/sdroege/ebur128) | MIT | Loudness of local files, so they play at the level of the streamed tracks. |
| librespot-java | Apache-2.0 | The listening-event format, re-implemented from its `EventService` rather than copied. |
| [go-librespot](https://github.com/devgianlu/go-librespot) and [go-librespot-termux](https://github.com/SEKY443/go-librespot-termux) | GPL-3.0 | The remote sleep timer's command and state fields, the check on truncated audio keys, and how Spotify's DJ is resolved and voiced (the session service, `client-tts`, the narration metadata), re-implemented from their findings rather than copied. |

## Building from source

Requirements, build steps, signing, the architecture and notes on the code are
in [docs/DEVELOPMENT.md](docs/DEVELOPMENT.md).

## Licence

ZMusic is licensed under GPL-3.0-or-later. See [LICENSE](LICENSE) for the full
text and preserve all upstream and component-specific notices. The lyrics view,
[`LyricsView.kt`](app/src/main/java/dev/lelonio/square/ui/player/LyricsView.kt),
is ported from Spicy Lyrics and remains under AGPL-3.0 as permitted by section
13 of both licences; the full AGPL text is in
[`LICENSE-AGPL-3.0.txt`](LICENSE-AGPL-3.0.txt).
