# TrailerHero for SteamOS (1.7.3)

This is a SteamOS x86-64 port of LoZazaMastro's TrailerHero 1.7.1. It keeps
the original game-page effect, source choices, local import, preview, download,
audio controls and optional screensaver. No Windows executable is installed.

## Install

1. Install Decky Loader on the Steam Deck and update SteamOS and Steam.
2. Copy `TrailerHero-v1.7.3_Installer.zip` to the Deck. In Decky's developer
   settings, choose the option to install a plugin from a ZIP and select it.
   If Decky offers no ZIP option, extract the archive so its `TrailerHero`
   directory is inside `/home/deck/homebrew/plugins/`, then restart Decky.
3. Restart Steam/Decky after replacing an earlier TrailerHero build. Existing
   per-game settings and downloaded videos live in Decky's settings directory;
   the package does not include or reset them.

The bundled binaries target **x86-64 Linux**. The plugin uses the `deck` user's
home for its Steam installation and starts its local file browser there. It
prepares executable permissions on first start if ZIP extraction removed them.
It uses a private, loopback-only server for saved and previewed clips. YouTube
downloads may access npm for yt-dlp's JavaScript challenge component; Steam and
YouTube streaming also need internet access. Downloaded trailers need free disk
space. The screensaver must be selected in Steam's Personalization settings.

This package was checked by automated frontend/backend tests and by running
the included Linux executables on x86-64 Linux. **It has not been run on a
physical Steam Deck**; Steam's UI hooks and video playback still require a
real-device check. If a video will not play, check Decky's TrailerHero log and
try a different source or an imported MP4.

The Decky panel now shows the live playback status, AppID and last media error.
If every source fails, open a game's library page, wait several seconds, then
open Decky and note the exact status line. The SteamOS build recognizes CEF
gamepad windows by their library document even when their title is just Steam.

Original project: https://github.com/LoZazaMastro/TrailerHero
