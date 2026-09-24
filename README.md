# TrailerHero for SteamOS

<p align="center"><img src="Logo.png" alt="TrailerHero logo" width="200"></p>

<p align="center"><strong>Game trailers in the Steam library on Steam Deck.</strong></p>

**English** · [Deutsch](README.de.md)

This SteamOS x86-64 adaptation of [LoZazaMastro's TrailerHero](https://github.com/LoZazaMastro/TrailerHero) turns the hero artwork on a game's Steam library page into a trailer after a short delay. It works with Steam games and non-Steam shortcuts. The working SteamOS 1.7.3 build is the basis for version **1.7.4**, which adds the installed-games-only bulk download option.

## Features

- **Cinematic game pages:** The original hero artwork remains visible briefly, then fades into a trailer. Playback is limited to game detail pages; it does not start on Library Home.
- **Steam and YouTube:** Choose automatic detection, a Steam trailer, or YouTube for each game. Select another available Steam video, search YouTube, or save a specific YouTube link. Automatic matching can also find a Steam trailer for a non-Steam game.
- **Stream or keep locally:** Preview a trailer, download it, or import your own video file using the controller-friendly file browser. Set the preferred quality to 720p, 1080p, or 2160p.
- **Bulk download filter (1.7.4):** Choose whether *Download all trailers* includes only games installed on this Steam Deck. See [Installed games only](#installed-games-only).
- **Per-game controls:** Set a source, choose a Steam video, trim the beginning and end, disable a game, and customize the CRT effect. There is also a logo placement option for game pages.
- **Audio:** Choose trailer audio or ThemeDeck music by default. The controller's west face button switches between them; the button symbol follows the controller layout.
- **Screensaver:** Select TrailerHero in Steam's Personalization settings for shuffled trailers, crossfades, game logos, clock and date. Screensaver audio has a separate switch and is off by default; weather can be shown when a compatible Weather plugin is available.
- **Languages:** The interface follows Steam's language and includes English, German, Italian, French, Spanish, Portuguese, Brazilian Portuguese, Dutch, Ukrainian, Chinese, and Japanese. New text may fall back to English where a translation is unavailable.

## Requirements

- Steam Deck or another **x86-64 SteamOS** device with Steam and [Decky Loader](https://decky.xyz/) installed.
- Internet access for Steam/YouTube trailers and enough free storage for downloaded videos.
- Use the **SteamOS installer ZIP** from this adaptation's release, not the Windows ZIP from the original project. Linux `yt-dlp`, `ffmpeg`, and `deno` are included; a separate Python or Windows installation is not required.

## Install or update

1. Download `TrailerHero-v1.7.4_Installer.zip` from the release and copy it to the Steam Deck. **Keep the ZIP intact.**
2. Open Decky's settings, enable **Developer Mode**, then use **Install Plugin from ZIP** and choose the file. Depending on Decky version, the wording may differ slightly.
3. Restart Steam/Decky after installing, especially when updating from version 1.7.3. Open a game's library page and give the artwork a few seconds to transition.

If your Decky version does not provide ZIP installation, extract the archive and place its contained `TrailerHero` folder at `/home/deck/homebrew/plugins/TrailerHero/`. The folder must directly contain `plugin.json`, `main.py`, and `dist/index.js`. Restart Decky afterward.

**Updating does not reset per-game settings or saved trailers.** The package contains no personal settings or downloaded trailer files.

## Installed games only

In the Decky panel, go to **Trailer mode**, enable **Download trailers only for installed games**, then choose **Download all trailers**. With this switch enabled, Steam's *local* installation status decides which games enter the queue. Games installed only on another PC and games with no known local installation status are skipped.

The switch is **off by default**. It affects only the bulk download action: streaming and manual downloads for individual games keep working. Turning it on does not delete previously saved trailers.

## Use

Open a game's library page for automatic playback. To customize it, open TrailerHero's per-game settings from the game's menu. Use the Decky panel for global playback, audio, YouTube, screensaver, and download settings. For the screensaver, additionally select **TrailerHero** as your screensaver in Steam's **Personalization** settings and choose Steam's idle delay there.

When diagnosing playback, the Decky panel shows the current status, AppID, and last media error. Trailer availability depends on the game and source. YouTube extraction may need to download an additional JavaScript component at runtime.

## Development and credits

The Project archive contains the editable `src/index.js`, tests, and release script. With Node.js 18+ and Python 3.10+:

```sh
npm run build
npm test
npm run package
```

This adaptation is based on **TrailerHero by LoZazaMastro**. See [LICENSE](LICENSE) and [THIRD-PARTY.md](THIRD-PARTY.md) for licenses of the plugin and bundled tools. For further SteamOS details, see [STEAMOS.md](STEAMOS.md).
