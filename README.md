# Audio-DSP-Labor: TP2, TP3 und TP4

Drei einsteigerfreundliche Laborversuche zur digitalen Audiosignalverarbeitung mit Python. Sie sind für Bachelor-Studierende gedacht, die zum ersten Mal mit Python und Audio arbeiten. Alle Texte, Aufgaben und Code-Kommentare sind in einfachem Deutsch.

Zu jedem Versuch gehören ein **Begleitheft (PDF)** und ein **Notebook**, das direkt in Google Colab läuft. Abschnitte und Aufgaben haben im PDF und im Notebook dieselben Nummern.

| TP | Thema | PDF | Open in Colab |
|---|---|---|---|
| TP2 | Audioanalyse: Abtastung, Stereo, Spektrum und Filter (mit Python-Kurzeinführung) | [TP2_Audioanalyse.pdf](https://github.com/Lamhour-Mohamed-Akram/audio-dsp-lab/blob/main/handouts/TP2_Audioanalyse.pdf) | [![In Colab öffnen](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Lamhour-Mohamed-Akram/audio-dsp-lab/blob/main/TP2_Audioanalyse.ipynb) |
| TP3 | Denoising und Equalizer: Rauschen reduzieren und Klang verändern | [TP3_Denoising_Equalizer.pdf](https://github.com/Lamhour-Mohamed-Akram/audio-dsp-lab/blob/main/handouts/TP3_Denoising_Equalizer.pdf) | [![In Colab öffnen](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Lamhour-Mohamed-Akram/audio-dsp-lab/blob/main/TP3_Denoising_Equalizer.ipynb) |
| TP4 | Spektrogramm und Sprachaktivität: Frequenzen über der Zeit | [TP4_Spektrogramm_Sprachaktivitaet.pdf](https://github.com/Lamhour-Mohamed-Akram/audio-dsp-lab/blob/main/handouts/TP4_Spektrogramm_Sprachaktivitaet.pdf) | [![In Colab öffnen](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Lamhour-Mohamed-Akram/audio-dsp-lab/blob/main/TP4_Spektrogramm_Sprachaktivitaet.ipynb) |

**Zeitbedarf (Schätzung):** TP2 ca. 30 bis 45 Minuten Python-Einführung plus 60 bis 90 Minuten Pflichtaufgaben. TP3 und TP4 je ca. 60 bis 90 Minuten Pflichtaufgaben nach der Einrichtung.

## So arbeiten Sie (Studierende)

1. Den Versuch in der Tabelle auswählen und das PDF öffnen oder ausdrucken.
2. Auf **Open in Colab** klicken. Gegebenenfalls mit einem Google-Konto anmelden.
3. Die Zellen von oben nach unten mit **Shift + Enter** ausführen. Erscheint eine Warnung, dass das Notebook nicht von Google stammt, mit "Trotzdem ausführen" bestätigen.
4. Antworten ins gedruckte Heft schreiben **oder** eine eigene Kopie speichern: **Datei > Kopie in Drive speichern**. Schreibrechte für das Original sind nicht nötig.

Jedes Notebook ist unabhängig. Es installiert nur fehlende Pakete und lädt die benötigten Audiodateien automatisch herunter. Uploads, Google Drive, ein GitHub-Konto oder eine GPU sind nicht nötig.

**Neustart in Colab:** Nach *Sitzung neu starten* sind die Variablen weg, die Dateien bleiben. Nach *Laufzeit trennen und löschen* oder in einer neuen Laufzeit sind auch die Dateien weg. In beiden Fällen die Zellen in Abschnitt 1 und danach alle Zellen bis zur aktuellen Stelle erneut ausführen, am einfachsten mit **Laufzeit > Alle ausführen**.

## Audiodaten

| Datei | Inhalt | Format | Lizenz |
|---|---|---|---|
| `data/speech.wav` | deutsche Sprache, eine Sprecherstimme (LibriVox, gelesen von marham63) | 16 kHz, mono, 15,9 s | Public Domain |
| `data/music.wav` | Marsch "Entrance of the Gladiators", United States Marine Band | 44,1 kHz, stereo, 20,0 s | Public Domain |
| `data/sound.wav` | Rennwagen "Audi R8 (2000)", aufgenommen von Edvvc (Wikimedia Commons) | 22,05 kHz, stereo, 8,0 s | CC BY-SA 3.0 |

Herkunft, Lizenzen und Schnitt sind in [`DATA_SOURCES.md`](DATA_SOURCES.md) dokumentiert. Verrauschte und bearbeitete Signale erzeugen die Notebooks selbst.

## Lokal ausführen (optional)

```bash
git clone https://github.com/Lamhour-Mohamed-Akram/audio-dsp-lab.git
cd audio-dsp-lab
python3 -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook TP2_Audioanalyse.ipynb
```

Lokal werden die Dateien im Ordner `data/` direkt benutzt. Getestet mit Python 3.12, eine GPU ist nicht nötig.

## Begleithefte mit LaTeX neu erzeugen

Benötigt wird eine TeX-Distribution mit `pdflatex` und `latexmk` (zum Beispiel TeX Live) sowie die Pakete `babel` (ngerman), `lmodern`, `geometry`, `setspace`, `microtype`, `tabularx`, `enumitem`, `fancyhdr`, `url` und `hyperref`. Der gemeinsame Stil liegt in `handouts/laborstil.sty`.

```bash
cd handouts
latexmk -pdf TP2_Audioanalyse.tex
latexmk -pdf TP3_Denoising_Equalizer.tex
latexmk -pdf TP4_Spektrogramm_Sprachaktivitaet.tex
latexmk -c                        # Zwischendateien entfernen
```

Die QR-Codes in `handouts/qr/` verweisen auf die Colab-Links. Neu erzeugen (optional, mit `pip install segno`):

```bash
python3 -c "import segno; [segno.make('https://colab.research.google.com/github/Lamhour-Mohamed-Akram/audio-dsp-lab/blob/main/' + n + '.ipynb', error='m').save('handouts/qr/' + n + '_colab.pdf', scale=4, border=2) for n in ['TP2_Audioanalyse', 'TP3_Denoising_Equalizer', 'TP4_Spektrogramm_Sprachaktivitaet']]"
```

## Projektstruktur

```
audio-dsp-lab/
├── TP2_Audioanalyse.ipynb
├── TP3_Denoising_Equalizer.ipynb
├── TP4_Spektrogramm_Sprachaktivitaet.ipynb
├── handouts/
│   ├── laborstil.sty
│   ├── TP2_Audioanalyse.tex / .pdf
│   ├── TP3_Denoising_Equalizer.tex / .pdf
│   ├── TP4_Spektrogramm_Sprachaktivitaet.tex / .pdf
│   └── qr/
├── data/
│   ├── speech.wav
│   ├── music.wav
│   └── sound.wav
├── archiv/
│   └── Audio_DSP_TP2_TP3_TP4_kombiniert_ARCHIV.ipynb   (alte kombinierte Fassung, nicht mehr aktuell)
├── DATA_SOURCES.md
├── requirements.txt
└── README.md
```
