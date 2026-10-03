# Changelog

## V1.2 — 2026-10
Réécriture complète en C++ / JUCE (remplace le script Python V13 + AppleScript).

- Interface graphique macOS / Windows, en français et en anglais.
- Détection automatique de la base VirtualDJ (disque externe prioritaire) et de ffmpeg, modifiables.
- Analyse ≈ 24× plus rapide (bibliothèque de 12 000 morceaux en ~30 min au lieu de ~12 h).
- Accords calés sur la grille de beats VirtualDJ, accords au demi-temps, dim / dim7, renversements.
- Diapason mesuré au cent près (l'estimateur V13 était limité à des pas de 25 cents), sans pitch-shift de l'audio.
- Tonalité déduite des accords, écrite dans la base et/ou le tag `TKEY` des fichiers.
- Vidéos (.mp4, .mov, .m4v ; .mkv / .webm via ffmpeg).
- Sécurité : VirtualDJ fermé pendant l'écriture puis rouvert, sauvegarde de la base à chaque écriture, écriture atomique vérifiée.
- Corrections : POI dont le nom contient un retour à la ligne, accords existants non reconnus (D5, C/2, hdim7…).
