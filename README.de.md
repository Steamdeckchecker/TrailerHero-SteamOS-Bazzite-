# TrailerHero für SteamOS

<p align="center"><img src="Logo.png" alt="TrailerHero Logo" width="200"></p>

<p align="center"><strong>Spieletrailer direkt in der Steam-Bibliothek auf dem Steam Deck.</strong></p>

[English](README.md) · **Deutsch**

Diese SteamOS-Version für x86-64 basiert auf [TrailerHero von LoZazaMastro](https://github.com/LoZazaMastro/TrailerHero). Auf der Bibliotheksseite eines Spiels blendet sie nach einer kurzen Wartezeit das Hero-Bild in einen Trailer über. Das funktioniert für Steam-Spiele und Steam-fremde Verknüpfungen. Grundlage von **Version 1.7.4** ist die funktionierende SteamOS-Version 1.7.3; neu ist die Option für Sammeldownloads ausschließlich installierter Spiele.

## Funktionen

- **Trailer auf Spieleseiten:** Das originale Hero-Bild erscheint zuerst und geht dann in den Trailer über. Auf der Startseite der Bibliothek startet kein Trailer.
- **Steam und YouTube:** Für jedes Spiel stehen automatische Erkennung, ein Steam-Trailer und YouTube zur Auswahl. Weitere Steam-Videos lassen sich auswählen, YouTube-Trailer suchen oder per Link festlegen. Für Steam-fremde Spiele kann automatisch ein passender Steam-Trailer gefunden werden.
- **Streamen oder lokal speichern:** Trailer lassen sich ansehen, herunterladen oder über den mit dem Controller bedienbaren Dateibrowser als eigene Videodatei importieren. Wählbare Qualität: 720p, 1080p und 2160p.
- **Filter für Sammeldownloads (1.7.4):** „Alle Trailer herunterladen“ kann auf Spiele begrenzt werden, die auf diesem Steam Deck installiert sind. Einzelheiten stehen unter [Nur installierte Spiele](#nur-installierte-spiele).
- **Einstellungen pro Spiel:** Quelle und Steam-Video wählen, Anfang und Ende kürzen, Trailer für ein Spiel deaktivieren und den CRT-Effekt einstellen. Auch die Position des Spielelogos lässt sich beeinflussen.
- **Audio:** Trailer-Ton oder ThemeDeck-Musik als Standard wählen. Mit der linken Aktionstaste des Controllers wechselst du zwischen beiden; das eingeblendete Tastensymbol passt sich dem Controller an.
- **Bildschirmschoner:** TrailerHero lässt sich in Steams Personalisierung als Bildschirmschoner auswählen. Trailer laufen gemischt mit weichen Übergängen, Spielelogos, Uhrzeit und Datum. Für den Ton gibt es einen eigenen, standardmäßig ausgeschalteten Schalter. Wetterdaten erscheinen, wenn ein kompatibles Weather-Plugin verfügbar ist.
- **Sprachen:** Die Oberfläche orientiert sich an der Steam-Sprache. Enthalten sind Deutsch, Englisch, Italienisch, Französisch, Spanisch, Portugiesisch, brasilianisches Portugiesisch, Niederländisch, Ukrainisch, Chinesisch und Japanisch. Für neue Texte ohne Übersetzung kann Englisch angezeigt werden.

## Voraussetzungen

- Steam Deck oder anderes **x86-64-Gerät mit SteamOS**, Steam und installiertem [Decky Loader](https://decky.xyz/).
- Internet für Steam- und YouTube-Trailer sowie ausreichend freier Speicherplatz für heruntergeladene Videos.
- Das **SteamOS-Installer-ZIP** dieser Anpassung verwenden, nicht das Windows-ZIP des Originalprojekts. Linux-Versionen von `yt-dlp`, `ffmpeg` und `deno` sind enthalten; eine separate Python- oder Windows-Installation ist nicht nötig.

## Installation und Update

1. `TrailerHero-v1.7.4_Installer.zip` aus dem Release herunterladen und auf das Steam Deck kopieren. **Die ZIP-Datei nicht entpacken.**
2. In Deckys Einstellungen den **Entwicklermodus** aktivieren. Dort **Plugin aus ZIP installieren** wählen und die Datei auswählen. Je nach Decky-Version kann die Bezeichnung leicht abweichen.
3. Nach der Installation Steam/Decky neu starten, insbesondere beim Update von Version 1.7.3. Danach die Bibliotheksseite eines Spiels öffnen und einige Sekunden auf den Übergang warten.

Falls deine Decky-Version keine Installation aus ZIP anbietet: Archiv entpacken und den darin enthaltenen Ordner `TrailerHero` unter `/home/deck/homebrew/plugins/TrailerHero/` ablegen. In diesem Ordner müssen unmittelbar `plugin.json`, `main.py` und `dist/index.js` liegen. Anschließend Decky neu starten.

**Ein Update löscht weder Spieleinstellungen noch bereits gespeicherte Trailer.** Persönliche Einstellungen und heruntergeladene Videos sind nicht im Installationspaket enthalten.

## Nur installierte Spiele

Im Decky-Menü unter **Trailer-Modus** die Option **„Trailer nur für installierte Spiele herunterladen“** aktivieren und dann **„Alle Trailer herunterladen“** wählen. Für die Downloadliste zählt Steams *lokaler* Installationsstatus. Spiele, die nur auf einem anderen PC installiert sind, und Spiele ohne bekannten lokalen Installationsstatus werden übersprungen.

Die Option ist **standardmäßig ausgeschaltet**. Sie gilt nur für den Sammeldownload: Streaming und gezielte Downloads einzelner Spiele funktionieren weiterhin. Bereits gespeicherte Trailer werden durch das Einschalten nicht gelöscht.

## Bedienung

Öffne für die automatische Wiedergabe die Bibliotheksseite eines Spiels. Individuelle Einstellungen erreichst du über das Menü des jeweiligen Spiels. Im Decky-Menü liegen die allgemeinen Einstellungen für Wiedergabe, Audio, YouTube, Bildschirmschoner und Downloads. Für den Bildschirmschoner musst du zusätzlich **TrailerHero** in Steams **Personalisierung** auswählen und dort die Wartezeit festlegen.

Bei Wiedergabeproblemen zeigt das Decky-Menü Status, AppID und den letzten Medienfehler an. Ob ein Trailer verfügbar ist, hängt von Spiel und Quelle ab. Für YouTube kann zur Laufzeit eine zusätzliche JavaScript-Komponente heruntergeladen werden.

## Entwicklung und Danksagung

Das Projektarchiv enthält `src/index.js`, Tests und das Release-Skript. Mit Node.js ab Version 18 und Python ab Version 3.10:

```sh
npm run build
npm test
npm run package
```

Diese Anpassung basiert auf **TrailerHero von LoZazaMastro**. Die Lizenzen des Plugins und der mitgelieferten Werkzeuge stehen in [LICENSE](LICENSE) und [THIRD-PARTY.md](THIRD-PARTY.md). Weitere SteamOS-Hinweise: [STEAMOS.md](STEAMOS.md).
