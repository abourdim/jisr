# Jisr (جِسْر) — Roadmap v1.0 → v2.0

## État actuel — v1.0 (livré)

| Catégorie | Mots | Objectif | Restants |
|-----------|------|----------|----------|
| astronomie | 31 | 150 | 119 |
| botanique | 98 | 150 | 52 |
| medecine | 131 | 200 | 69 |
| mathematiques | 4 | 100 | 96 |
| chimie | 1 | 100 | 99 |
| cuisine | 3 | 150 | 147 |
| commerce | 2 | 100 | 98 |
| zoologie | 5 | 100 | 95 |
| geographie | 1 | 100 | 99 |
| histoire | 0 | 100 | 100 |
| textile | 0 | 80 | 80 |
| architecture | 1 | 80 | 79 |
| arts_musique | 1 | 80 | 79 |
| philosophie | 0 | 60 | 60 |
| militaire | 1 | 60 | 59 |
| droit | 0 | 60 | 60 |
| meteo | 0 | 40 | 40 |
| **TOTAL** | **279** | **~1760** | **~1431** |

---

## Sprint plan — génération de données

### Phase 1 — Compléter les catégories prioritaires
IDs à utiliser : 371 → ~1760 (incrément +1 à chaque mot)

#### 1.1 — cuisine (147 mots manquants, objectif 150)
Thèmes : plats emblématiques · épices culinaires · techniques de cuisson · ustensiles · ingrédients de base · pâtisserie · boissons non-alcoolisées · conserves · sauces · céréales transformées

#### 1.2 — mathematiques (96 mots manquants, objectif 100)
Thèmes : arithmétique · algèbre · géométrie · trigonométrie · astronomie mathématique · chiffres · fractions · notation positionnelle · calcul infinitésimal (précurseurs arabes) · termes logiques

#### 1.3 — chimie (99 mots manquants, objectif 100)
Thèmes : alchimie opératoire · distillation · calcination · sublimation · métaux · sels · acides · bases · teinturerie · verrerie · céramique · alliages

#### 1.4 — commerce (98 mots manquants, objectif 100)
Thèmes : monnaies · mesures · contrats · routes commerciales · denrées · poids · taxes · douane · comptabilité · correspondance marchande · caravanes · foires

#### 1.5 — zoologie (95 mots manquants, objectif 100)
Thèmes : mammifères arabes · oiseaux · insectes · reptiles · poissons · animaux du désert · animaux coraniques · chasse fauconnerie · bétail · parasitologie

#### 1.6 — geographie (99 mots manquants, objectif 100)
Thèmes : reliefs · vents · mers · fleuves · villes · régions · types de terrain · navigation · orientation · cartographie · déserts · îles · péninsules

### Phase 2 — Nouvelles catégories
#### 2.1 — histoire (100 mots)
#### 2.2 — textile (80 mots)
#### 2.3 — architecture (79 mots manquants)
#### 2.4 — arts_musique (79 mots manquants)
#### 2.5 — philosophie (60 mots)
#### 2.6 — militaire (59 mots manquants)
#### 2.7 — droit (60 mots)
#### 2.8 — meteo (40 mots)

---

## Tâches app à venir

### v1.1 app — Interface
- [ ] Page de statistiques par catégorie (graphique barre)
- [ ] Mode « révision » : présenter les mots non appris en priorité
- [ ] Export PDF d'une catégorie
- [ ] Filtres combinés : catégorie + langue de recherche
- [ ] Compteur de streak quotidien

### v2.0 app — Architecture
- [ ] Migrer de DATA inline vers fetch() des fichiers JSON par catégorie
- [ ] Service Worker + cache offline
- [ ] PWA installable (manifest.json)
- [ ] Sync localStorage → IndexedDB pour >1000 mots

---

## Règles éditoriales (rappel pour continuation)

- **Arabe classique uniquement** — الفصحى (Coran, ḥadīths, Ibn Sīnā, Ibn al-Bayṭār, Lisan al-Arab)
- **Aucun dialecte** — pas d'arabe marocain/égyptien/levantin contemporain
- **Translitération académique** : ā ī ū · ʿ ʾ · ḥ ḫ ḍ ṭ ẓ ġ š
- **Sources autorisées** : Coran · Sunna · grammairiens arabes classiques · savants de l'ère abbasside
- **Contenu** : aucun terme inapproprié · aucune étymologie non vérifiée
- **Structure JSON** : respecter exactement le schéma (voir ci-dessous)

## Schéma JSON d'une entrée

```json
{
  "id": 371,
  "word_fr": "mot en français",
  "word_en": "word in English",
  "word_ar": "الكَلِمَة",
  "transliteration": "al-kalima",
  "meaning_fr": "Définition en français (1-2 phrases).",
  "meaning_en": "Definition in English (1-2 sentences).",
  "meaning_ar": "تعريف باللغة العربية (جملة أو جملتان).",
  "etymology": "Explication de l'étymologie avec sources.",
  "pathway": "arabe → espagnol → français",
  "pathway_steps": [
    {"lang": "arabe", "word": "الكَلِمَة", "date": "VIIe s."},
    {"lang": "espagnol", "word": "palabra", "date": "XIe s."},
    {"lang": "français", "word": "mot", "date": "XIIe s."}
  ],
  "category": "nom_de_categorie",
  "examples": {
    "fr": "Exemple d'usage en français.",
    "en": "Usage example in English.",
    "ar": "مثال على الاستخدام بالعربية."
  },
  "related_words": ["mot1", "mot2", "mot3"]
}
```
