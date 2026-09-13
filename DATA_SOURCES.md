# Datenquellen und Lizenzen (`data/`)

Alle drei Audiodateien in `data/` sind gekürzte und konvertierte Ausschnitte aus
öffentlich lizenzierten Aufnahmen. Die Herkunft wurde am 13.09.2026 über die
Metadaten der jeweiligen Plattform (Wikimedia Commons API bzw. archive.org
Metadaten) geprüft. Die Konvertierung erfolgte mit Python (`librosa`,
`soundfile`). An den Schnittgrenzen wurde ein Ein- und Ausblenden von 20 ms
angewendet, damit keine Knackgeräusche entstehen. Es wurde keine sonstige
Bearbeitung (kein Equalizer, keine Lautstärkeänderung, kein Rauschfilter)
vorgenommen.

| Datei | Inhalt | Format | Dauer |
|---|---|---|---|
| `data/speech.wav` | Sprache (deutsch, eine Sprecherstimme, Vorlesen einer Fabel) | 16 000 Hz, mono, 16-Bit PCM | 15,9 s |
| `data/music.wav` | Musik (Blasorchester, Marsch) | 44 100 Hz, stereo, 16-Bit PCM | 20,0 s |
| `data/sound.wav` | Umgebungsgeräusch (vorbeifahrender Rennwagen) | 22 050 Hz, stereo, 16-Bit PCM | 8,0 s |

## `data/speech.wav`: Sprache

- **Quelle:** LibriVox-Hörbuch "Fabeln" von Magnus Gottfried Lichtwer,
  Abschnitt 005 "Das Wiesel und die Hühner", gelesen von **marham63**.
- **URL:** <https://archive.org/details/fabeln_1905_librivox>
  (Datei `fabeln_005_lichtwer_64kb.mp3`)
- **Lizenz:** Public Domain (Creative Commons Public Domain Mark 1.0,
  <http://creativecommons.org/publicdomain/mark/1.0/>). Alle
  LibriVox-Aufnahmen sind gemeinfrei. Der Text von Lichtwer (1719 bis 1783) ist
  ebenfalls gemeinfrei.
- **Bearbeitung:** Ausschnitt 12,8 s bis 28,7 s der Originaldatei (Beginn der
  eigentlichen Fabel, nach der LibriVox-Ansage), MP3 (22 050 Hz, mono)
  dekodiert und auf 16 000 Hz umgetastet, als 16-Bit-WAV gespeichert.
- **Hinweis:** Die Aufnahme enthält genau **eine** Sprecherstimme. Sie eignet
  sich für Sprachaktivitäts-Erkennung, nicht für Sprecher-Erkennung.

## `data/music.wav`: Musik (stereo)

- **Quelle:** Julius Fučík, "Entrance of the Gladiators" ("Einzug der
  Gladiatoren"), gespielt und aufgenommen von der **United States Marine
  Band** (ca. 1999), veröffentlicht auf
  <https://www.marineband.marines.mil/Audio-Resources/Educational-Series/Live-in-Concert/>.
- **URL (Wikimedia Commons):**
  <https://commons.wikimedia.org/wiki/File:Julius_Fu%C4%8D%C3%ADk%27s_%22Entrance_of_the_Gladiators%22,_performed_by_the_United_States_Marine_Band.flac>
- **Lizenz:** Public Domain. Die Aufnahme ist ein Werk der US-Bundesregierung
  (United States Marine Band) und damit gemeinfrei. Die Komposition
  (Fučík, 1897) ist ebenfalls gemeinfrei.
- **Bearbeitung:** Ausschnitt 24,0 s bis 44,0 s der FLAC-Datei (44 100 Hz,
  stereo, 24 Bit), Wandlung nach 16-Bit-WAV. Beide Stereokanäle wurden
  unverändert übernommen (echtes Stereo, Korrelation L/R etwa 0,15).

## `data/sound.wav`: Umgebungsgeräusch (Rennwagen)

- **Quelle:** "Audi R8 (2000)", Rennwagen beim Start am Goodwood Festival of
  Speed 2009, aufgenommen von Wikimedia-Commons-Nutzer **Edvvc**.
- **URL:** <https://commons.wikimedia.org/wiki/File:Audi_R8_(2000).ogg>
- **Lizenz:** **CC BY-SA 3.0** (<https://creativecommons.org/licenses/by-sa/3.0/>).
  Urheber: Edvvc. Die hier abgelegte, gekürzte Fassung ist eine Bearbeitung
  und steht ebenfalls unter CC BY-SA 3.0.
- **Bearbeitung:** Ausschnitt 4,0 s bis 12,0 s der Ogg-Vorbis-Datei
  (44 100 Hz, stereo), auf 22 050 Hz umgetastet, als 16-Bit-WAV gespeichert.
  Beide Stereokanäle wurden übernommen (Korrelation L/R etwa 0,68).

Es wurden keine Lizenzen angenommen oder erfunden. Nur die oben verlinkten,
auf der jeweiligen Plattform angegebenen Lizenzen wurden übernommen.
