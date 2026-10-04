# Changelog

## V1.2.3 — 2026-10
- Accords de 6te (aussi joués sans tierce, ex. Fm6) et suspendus déduits de la basse : C6, Cm6, Fm6, Csus2sus4, G7sus4. / 6th chords (also played without a third, e.g. Fm6) and suspended chords deduced from the bass.

## V1.2.2 — 2026-10
- Accord demi-diminué **m7b5** (Aø = A C E♭ G), auparavant détecté comme Am7. / Half-diminished **m7b5** chord (Aø), previously detected as Am7.
- Lignes de basse chromatiques (Cm → Cm/B → Cm/Bb → Am7b5) écrites avec leur basse. / Chromatic bass lines written with their bass note.
- Correction de diapason par `key_smooth` : tempo inchangé, fonctionne avec Master Tempo ; POI nommée en cents (« -43.6c »). / Tuning correction now uses `key_smooth`: tempo unchanged, works with Master Tempo; POI named in cents ("-43.6c").
- Bouton « Effacer accords / POI pitch » (un morceau ou toute la base), tonalités conservées, sauvegarde automatique. / "Clear chords / pitch POI" button (one track or whole database), keys kept, automatic backup.
- Renversements aussi sur les accords de 7e, dim et m7b5 (G7/B, Cm7/Bb, Bdim/D). / Inversions also on 7th, dim and m7b5 chords.

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
- Tonalité écrite aussi dans la détection de VirtualDJ (`<Scan Key>`, notation C# Eb F# G# A#) : c'est elle que VirtualDJ affiche.
- Accords guidés par la tonalité (2e passe) : Edim / Dm au lieu d'Em / D dans un morceau en ré mineur ; les diminués de passage restent détectés.
- Tags `TKEY` écrits sur place (quelques Ko, sans recopier l'audio), fichiers déjà à jour ignorés ; progression de l'écriture affichée.
- macOS ne ralentit plus l'analyse quand la fenêtre passe en arrière-plan (App Nap).
- VirtualDJ est (ré)ouvert après l'écriture si la case est cochée.
- Outil terminal : `vdjchord-cli scankey --write` recopie la tonalité du tag dans la détection VirtualDJ.
