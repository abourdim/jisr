# جِسْر — Jisr v1.0

> **"Le pont entre les civilisations"** · *The bridge between civilizations* · الجسر بين الحضارات

```
بِسْمِ ٱللَّهِ ٱلرَّحْمَٰنِ ٱلرَّحِيمِ
```

---

## ✦ Présentation

**Jisr** (جِسْر, « pont » en arabe) est une application web d'étymologie qui révèle les mots d'origine arabe présents dans le français et l'anglais modernes. Elle célèbre l'âge d'or de la civilisation islamique — de l'Alhambra de Grenade aux bibliothèques de Bagdad, de Cordoue à Médine — et le rôle des savants arabes dans la transmission du savoir universel.

**279 mots** · 3 langues · étymologie complète · audio · quiz · zéro dépendance

---

## 🕌 Thème & Esthétique

L'interface s'inspire de l'architecture islamique classique :

| Référence | Élément visuel |
|-----------|---------------|
| **Alhambra (Grenade)** | Arcs nasrides CSS, palette or, motifs zellige |
| **Médine** | Silhouette de mosquée, coupole, fond nuit profonde |
| **Cordoue** | Turquoise andalou, entrelacs géométriques |
| **Manuscrits abbassides** | Typographie Amiri, calligraphie mise en valeur |

**Palette** · Nuit de Médine `#080C10` · Or nasride `#C9A84C` · Turquoise andalou `#2A7B8C` · Ivoire `#F0E6CC`

**Typographies** · Amiri (calligraphie arabe) · Cormorant Garamond (affichage) · Lato (interface)

---

## 📁 Structure du projet

```
jisr/
├── index.html           ← Application (fetch data/ — pour serveur / GitHub Pages)
├── jisr-v1.0.html       ← Application standalone (tout inline, zéro serveur)
├── README.md            ← Ce fichier
├── HELP.html            ← Guide utilisateur illustré
├── FAQ.html             ← Questions fréquentes
├── ROADMAP.md           ← Plan de développement
└── data/
    ├── index.json       ← Manifeste des catégories
    ├── astronomie.json  ← 31 mots
    ├── botanique.json   ← 98 mots
    ├── medecine.json    ← 131 mots
    └── … 9 autres catégories
```

---

## 🚀 Fonctionnalités v1.0

### Contenu & Langues
- Définitions en **3 langues** dans chaque fiche : 🇫🇷 FR · 🇬🇧 EN · 🇸🇦 AR
- Exemples d'usage en 3 langues · arbre étymologique visuel avec dates
- Interface trilingue FR/EN/عربي avec basculement RTL/LTR complet

### Apprentissage
- 🎵 TTS multilingue — arabe (ar-SA), français (fr-FR), anglais (en-US)
- ⌨️ Clavier arabe virtuel — 28 lettres + diacritiques
- 🧠 Quiz — 8 questions, 4 choix, score persisté
- ✅ Marquage "appris" avec badge visuel

### Persistance (localStorage)
| Clé | Contenu |
|-----|---------|
| `jisr_favs` | IDs des mots favoris |
| `jisr_history` | 20 derniers mots consultés |
| `jisr_learned` | Mots marqués appris |
| `jisr_quiz_scores` | 10 derniers scores |
| `jisr_ui_lang` | Langue d'interface |
| `jisr_card_lang` | Filtre de langue des cartes |

### Navigation
- ⬅️➡️ Navigation entre mots dans la modale · 🔗 Partage URL `?word=4`
- ⭐ Favoris · 🕐 Historique · 🎬 Mode démo animé

---

## 📚 Sources

- **CNRTL** — cnrtl.fr
- **Oxford English Dictionary**
- **Dozy, R.** — *Supplément aux dictionnaires arabes* (1881)

---

## 🗂 Catégories

Astronomie · Botanique · Médecine · Mathématiques · Chimie · Cuisine · Commerce · Zoologie · Géographie · Militaire · Architecture · Arts & Musique

---

## 🛠 Compatibilité

Chrome 90+ · Firefox 88+ · Safari 14+ · Edge 90+ · **IE : non supporté**

APIs : Web Speech API · localStorage · CSS Grid · CSS Custom Properties

---

## 📜 Changelog

### v1.0 — 2026-03-07
- **279 mots** répartis en 12 catégories (astronomie, botanique, médecine…)
- Architecture multi-fichiers : `data/*.json` chargés en async (`index.html`)
- Filtre par catégorie dans la barre de recherche
- Fichier standalone `jisr-v1.0.html` (429 KB, tout inline)
- Arabe classique الفصحى uniquement · translitération académique

### v0.1 — 2026-03-06
- Application initiale · 18 mots · recherche · filtres
- Interface trilingue · clavier arabe · TTS · quiz · mode démo
- Thème islamique : Alhambra, Médine, Cordoue
- Panel latéral Favoris / Historique / Appris

---

## 🤲 Intention

> « Seek knowledge, even unto China. »
> — Hadith attribué au Prophète Muhammad ﷺ

Ce projet est un hommage à la civilisation islamique classique (VIIe–XVe s.) et aux savants arabes, persans et berbères qui ont préservé et enrichi le savoir de l'humanité. Des mots comme **algèbre**, **algorithme**, **alcool** sont des ponts vivants entre civilisations.

---

*جِسْر — Jisr v1.0 · Fait avec ❤️ et calligraphie*
