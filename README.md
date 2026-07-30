# Locus — Releases & Update-Feed

Öffentliches Release-Repo für das [Locus](https://www.bimover.ch/products/locus)
Archicad-Add-on (Geodaten-Import + Origin-Verschiebung): GitHub-Releases mit
den installierbaren Bundles und der Sparkle-kompatible Update-Feed
[`appcast.xml`](appcast.xml), den das Add-on über
`https://www.bimover.ch/updates/locus/appcast.xml` abruft.

## Feed-Format

Ein Feed für beide Plattformen — die Items unterscheiden sich per
`sparkle:os` (`macos` / `windows`) und tragen die Archicad-Version im
Dateinamen. Pro Release vier Assets:

| Asset | Inhalt |
|---|---|
| `Locus-<ver>-mac-AC29.zip` | `Locus.bundle` (macOS, Archicad 29) |
| `Locus-<ver>-mac-AC28.zip` | `Locus.bundle` (macOS, Archicad 28) |
| `Locus-<ver>-win-AC29.zip` | `Locus.apx` + `libcrypto-4-x64.dll` (Windows x64, Archicad 29) |
| `Locus-<ver>-win-AC28.zip` | `Locus.apx` + `libcrypto-4-x64.dll` (Windows x64, Archicad 28) |

Das Add-on wählt das Item nach Plattform **und** `locus:acVersion`
(Custom-Attribut) passend zur laufenden Archicad-Hauptversion.

Quellcode: privates Repo (`locus-source`). Releases werden mit
`scripts/publish-release.sh` aus dem Quell-Repo erzeugt — nur PROD-Builds
(Lizenzprüfung aktiv), niemals DEV-Builds mit Bypass.
