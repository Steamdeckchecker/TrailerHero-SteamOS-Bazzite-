# TrailerHero

TrailerHero is a Decky Loader plugin that makes Steam Big Picture feel a little more like a console dashboard.

When you open a game page, the plugin keeps the original Steam hero artwork in place for three seconds, then fades in a muted trailer inside the same hero area. It can use Steam trailers first, and YouTube automatically when Steam has nothing useful.

Press the controller's physical **west face button** to switch from ThemeDeck music to trailer audio, and press it again to switch back. Steam's own live glyph in the footer follows the active controller layout (for example Square on PlayStation, X on Xbox/Steam, or Y on Nintendo).

It also supports per-game Steam video choices, strict YouTube auto-search, intro/outro trimming, optional CRT styling for low-resolution videos, and a small logo assist for game pages that use tiny SteamGridDB logos.

## Languages

TrailerHero follows the current Steam or browser language automatically.

Included languages:

- English
- Italian
- French
- Spanish
- Portuguese
- Brazilian Portuguese
- German
- Dutch
- Ukrainian
- Chinese
- Japanese

## Main Controls

- **Enabled** turns the effect on or off.
- **Game page logo** moves the game logo to the bottom-left while the trailer is visible, then restores it when you leave.
- **Automatic CRT** applies a subtle CRT look to low-resolution trailers.
- **Source** lets each game use automatic mode, Steam, or YouTube.
- **Quality** chooses the preferred video quality for both Steam and YouTube: 720p, 1080p, or 2160p.
- **Steam video** lets you choose any Steam video returned for that game from a dropdown, not just the highlighted trailer.
- **Trim start / Trim end** saves per-game video trimming.
- **Custom YouTube link** lets you save a specific YouTube trailer for one game. If no link is saved, auto-search stays enabled by default, prefers 4K results, and keeps the game title match strict.

## Screensaver

Select **TrailerHero** in Steam's Personalization screensaver selector, then choose the idle delay in Steam. Trailers play in a shuffled order with preloaded crossfades, each game's library logo, and Steam-sized time, date and weather in the upper left. The separate **Screensaver audio** switch in TrailerHero controls sound; it is off by default. Steam handles waking and dismissing the screensaver.

Custom library logos and the Steam UI font are prepared locally from your Steam installation. Weather follows the Weather plugin when available. Unavailable trailers are skipped.

- Selecting a dropdown result immediately applies it.
- Global YouTube enable/disable toggle.
- Cleaner Steam title detection to avoid global UI text.
- More aggressive YouTube quality requests.
- Global non-Steam YouTube reassignment with Decky confirmation modal.
- Destructive reset of saved YouTube videos, queries, and YouTube preferred sources before reassignment.

Excluded the broken 0.1.16 / 0.1.17 YouTube layout experiments.
