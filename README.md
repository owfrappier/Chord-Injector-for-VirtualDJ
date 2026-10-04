<p align="center"><img src="icon.png" width="160" alt="Chord Injector for VirtualDJ"></p>

<h1 align="center">Chord Injector for VirtualDJ</h1>
<p align="center"><b>V1.2</b> · macOS (Apple Silicon) · Windows (x64)</p>
<p align="center"><a href="https://www.paypal.com/paypalme/owfrappier"><b>☕ DONATE (PayPal)</b></a></p>

---

🇬🇧 [English](#english) · 🇫🇷 [Français](#français)

---

## English

**Chord Injector for VirtualDJ** analyses your music library and writes into VirtualDJ:

- 🎹 **Chords** as POI markers, aligned on VirtualDJ's own beat grid (fixed and variable BPM), with half-beat passing chords, 7ths, maj7, dim/dim7 and inversions (C/E…).
- 🎚️ **Fine pitch correction to A = 440 Hz**: the tuning of each track is measured to the cent and a pitch POI is added, so tracks play in tune with synths, VSTs or a piano.
- 🔑 **Key** of the track, deduced from its chords — written to the VirtualDJ database, to the audio file tag (`TKEY`), or both.

Full library (≈ 12 000 tracks) analysed in about **30 minutes** on a recent Mac.

### Download & install

Get the latest version in **[Releases](https://github.com/owfrappier/Chord-Injector-for-VirtualDJ/releases)**.
The former Python / AppleScript version (V13) is still available in the older releases of this repository.

- **macOS**: open the **.pkg** installer (signed and notarised by Apple), the app is installed in Applications.
- **Windows**: download and run *Chord.Injector.for.VirtualDJ.exe* (nothing to install). The app is not signed: if SmartScreen shows "Windows protected your PC", click **More info** → **Run anyway**.

Requirements: **VirtualDJ 2026 (build 9295 or newer)**, tracks already analysed by VirtualDJ (BPM / beat grid).

**ffmpeg** (auto-detected, or choose it in the app):

- **Windows — recommended**: needed for M4A / AAC / ALAC and videos. Install it by typing in a terminal (PowerShell):
  ```
  winget install ffmpeg
  ```
  then restart the app (or click **Auto**).
- **macOS — optional**: only for `.mkv` / `.webm` videos and rare formats: `brew install ffmpeg`.

### How to use

1. **VirtualDJ database** — detected automatically: the database of the external drive first (`/Volumes/<drive>/VirtualDJ/database.xml`, `E:\VirtualDJ\database.xml`), otherwise the internal one. Use *Other…* to pick another.
2. **Tracks** — *One track* (search by title / artist) or *Whole database*.
3. **Analyse**, check the log, then **Write to VirtualDJ**.

### Safety

- VirtualDJ is **always closed while writing** (it rewrites its database when quitting), then reopened.
- A **backup** `database.backup-YYYYMMDD-HHMMSS.xml` is created next to the database at every write (last 20 kept).
- Audio tags: only the `TKEY` tag is changed, in place; audio data and other tags are untouched. ⚠️ There is no backup of audio tags — your previous keys stay in the database backup.
- Use at your own risk. Not affiliated with VirtualDJ / Atomix Productions.

### Tip

The first chord is placed 0.25 s after the pitch POI. If the two labels overlap in VirtualDJ, **zoom in on the waveform**.

---

## Français

**Chord Injector for VirtualDJ** analyse votre bibliothèque et écrit dans VirtualDJ :

- 🎹 **Les accords** en POI, calés sur la grille de beats de VirtualDJ (BPM fixe ou variable), avec accords de passage au demi-temps, 7e, maj7, dim/dim7 et renversements (C/E…).
- 🎚️ **La correction de diapason à La = 440 Hz** : l'accordage de chaque morceau est mesuré au cent près et une POI pitch est ajoutée, pour jouer juste avec un synthé, des VST ou un piano.
- 🔑 **La tonalité**, déduite des accords — écrite dans la base VirtualDJ, dans le tag du fichier audio (`TKEY`), ou les deux.

Une bibliothèque entière (≈ 12 000 morceaux) est analysée en **30 minutes environ** sur un Mac récent.

### Téléchargement et installation

Dernière version dans **[Releases](https://github.com/owfrappier/Chord-Injector-for-VirtualDJ/releases)**.
L'ancienne version Python / AppleScript (V13) reste disponible dans les anciennes releases de ce dépôt.

- **macOS** : ouvrez l'installeur **.pkg** (signé et notarisé par Apple), l'app s'installe dans Applications.
- **Windows** : téléchargez et lancez *Chord.Injector.for.VirtualDJ.exe* (rien à installer). L'application n'est pas signée : si SmartScreen affiche « Windows a protégé votre ordinateur », cliquez sur **Informations complémentaires** → **Exécuter quand même**.

Prérequis : **VirtualDJ 2026 (build 9295 ou plus récent)**, morceaux déjà analysés par VirtualDJ (BPM / grille).

**ffmpeg** (détecté automatiquement, ou à choisir dans l'app) :

- **Windows — recommandé** : nécessaire pour les M4A / AAC / ALAC et les vidéos. Installez-le en tapant dans un terminal (PowerShell) :
  ```
  winget install ffmpeg
  ```
  puis relancez l'app (ou cliquez sur **Auto**).
- **macOS — facultatif** : seulement pour les vidéos `.mkv` / `.webm` et les formats rares : `brew install ffmpeg`.

### Utilisation

1. **Base VirtualDJ** — détectée automatiquement : celle du disque externe d'abord (`/Volumes/<disque>/VirtualDJ/database.xml`, `E:\VirtualDJ\database.xml`), sinon la base interne. *Autre…* pour en choisir une autre.
2. **Morceaux** — *Un morceau* (recherche titre / artiste) ou *Toute la base*.
3. **Analyser**, vérifier le journal, puis **Écrire dans VirtualDJ**.

### Sécurité

- VirtualDJ est **toujours fermé pendant l'écriture** (il réécrit sa base en quittant), puis rouvert.
- Une **sauvegarde** `database.backup-AAAAMMJJ-HHMMSS.xml` est créée à côté de la base à chaque écriture (20 gardées).
- Tags audio : seul le tag `TKEY` est modifié, sur place ; l'audio et les autres tags ne sont pas touchés. ⚠️ Pas de sauvegarde des tags audio — les anciennes tonalités restent dans la sauvegarde de la base.
- Utilisation à vos risques. Projet indépendant, non affilié à VirtualDJ / Atomix Productions.

### Astuce

Le premier accord est placé 0,25 s après la POI pitch. Si les deux étiquettes se chevauchent dans VirtualDJ, **zoomez sur la forme d'onde**.

---

© Olivier FRAPPIER 2026 · [DONATE](https://www.paypal.com/paypalme/owfrappier) · VirtualDJ is a trademark of Atomix Productions.
