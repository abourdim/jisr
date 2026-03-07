# Prompt de continuation — Jisr (جِسْر) · Nouvelle conversation

Copie ce prompt en intégralité pour démarrer une nouvelle conversation et continuer exactement là où on s'est arrêtés.

---

## Contexte du projet

Tu travailles sur **Jisr (جِسْر)** — une application web d'étymologie arabe standalone (zéro dépendances, un seul fichier HTML).

L'app affiche des mots français/anglais d'origine arabe avec :
- leur étymologie détaillée
- leur parcours linguistique (pathway)
- leur définition trilingue (fr · en · ar)
- des exemples trilingues
- un quiz interactif
- un système de favoris/appris/historique

## État actuel — v1.0 livrée

- **279 mots** en production dans `jisr-v1.0.html`
- Dernier ID utilisé : **370**
- Prochain ID à utiliser : **371**
- Architecture : fichiers JSON par catégorie dans `data/`

### Fichiers livrés

```
jisr-v1.0.html          ← app standalone (DATA inline, 279 mots)
data/index.json         ← manifeste catégories
data/astronomie.json    ← 31 mots  (IDs 19–49)
data/botanique.json     ← 98 mots  (IDs 7, 17, 80–109, 301–370)
data/medecine.json      ← 131 mots (IDs 13, 50–79, 201–300)
data/mathematiques.json ← 4 mots   (IDs 2, 3, 8, 16)
data/chimie.json        ← 1 mot    (ID 1)
data/cuisine.json       ← 3 mots   (IDs 4, 5, 6)
data/commerce.json      ← 2 mots   (IDs 10, 12)
data/zoologie.json      ← 5 mots   (IDs 14, 80–83)
data/geographie.json    ← 1 mot    (ID 17)
data/militaire.json     ← 1 mot    (ID 11)
data/architecture.json  ← 1 mot    (ID 15)
data/arts_musique.json  ← 1 mot    (ID 9)
```

## Travail restant — ROADMAP

| Catégorie | Actuel | Objectif | À générer |
|-----------|--------|----------|-----------|
| cuisine | 3 | 150 | **147** |
| mathematiques | 4 | 100 | **96** |
| chimie | 1 | 100 | **99** |
| commerce | 2 | 100 | **98** |
| zoologie | 5 | 100 | **95** |
| geographie | 1 | 100 | **99** |
| astronomie | 31 | 150 | **119** |
| botanique | 98 | 150 | **52** |
| medecine | 131 | 200 | **69** |
| histoire | 0 | 100 | **100** |
| textile | 0 | 80 | **80** |
| architecture | 1 | 80 | **79** |
| arts_musique | 1 | 80 | **79** |
| philosophie | 0 | 60 | **60** |
| militaire | 1 | 60 | **59** |
| droit | 0 | 60 | **60** |
| meteo | 0 | 40 | **40** |
| **TOTAL** | **279** | **~1760** | **~1431** |

## Ordre de génération suggéré

1. **cuisine** — 147 mots (IDs 371–517)
2. **mathematiques** — 96 mots (IDs 518–613)
3. **chimie** — 99 mots (IDs 614–712)
4. **commerce** — 98 mots (IDs 713–810)
5. **zoologie** — 95 mots (IDs 811–905)
6. **geographie** — 99 mots (IDs 906–1004)
7. **histoire** — 100 mots (IDs 1005–1104)
8. **textile** — 80 mots (IDs 1105–1184)
9. **architecture** — 79 mots (IDs 1185–1263)
10. **arts_musique** — 79 mots (IDs 1264–1342)
11. **philosophie** — 60 mots (IDs 1343–1402)
12. **militaire** — 59 mots (IDs 1403–1461)
13. **droit** — 60 mots (IDs 1462–1521)
14. **meteo** — 40 mots (IDs 1522–1561)
15. **astronomie** complétion — 119 mots (IDs 1562–1680)
16. **botanique** complétion — 52 mots (IDs 1681–1732)
17. **medecine** complétion — 69 mots (IDs 1733–1801)

## Schéma JSON obligatoire

Chaque entrée doit respecter **exactement** ce schéma :

```json
{
  "id": 371,
  "word_fr": "mot en français",
  "word_en": "word in English",
  "word_ar": "الكَلِمَة بالشكل",
  "transliteration": "al-kalima",
  "meaning_fr": "Définition complète en français (1-2 phrases).",
  "meaning_en": "Full definition in English (1-2 sentences).",
  "meaning_ar": "تعريف كامل باللغة العربية الفصحى (جملة أو جملتان).",
  "etymology": "Explication détaillée de l'étymologie avec sources arabes classiques.",
  "pathway": "arabe → espagnol médiéval → français",
  "pathway_steps": [
    {"lang": "arabe", "word": "الكَلِمَة", "date": "VIIe s."},
    {"lang": "espagnol médiéval", "word": "palabra", "date": "XIe s."},
    {"lang": "français", "word": "mot", "date": "XIIe s."}
  ],
  "category": "nom_de_categorie",
  "examples": {
    "fr": "Exemple d'usage concret en français.",
    "en": "Concrete usage example in English.",
    "ar": "مثال على الاستخدام بالعربية الفصحى."
  },
  "related_words": ["mot1", "mot2", "mot3"]
}
```

## Règles éditoriales STRICTES

1. **Arabe classique uniquement** — الفصحى
   - Sources : Coran · Sunna · Ibn Sīnā (القانون) · Ibn al-Bayṭār (الجامع) · Ibn al-ʿAwwām · Lisan al-Arab
   - Aucun dialecte (pas de darija, ʿāmmiyya, arabe égyptien/levantin contemporain)

2. **Translitération académique** :
   - Voyelles longues : ā ī ū
   - Emphases : ḥ ḫ ḍ ṭ ẓ ġ š
   - Hamza/ʿayn : ʾ ʿ
   - Exemple : al-kuḥl · zaʿfarān · ḥabbat al-sawdāʾ

3. **word_ar avec tashkīl** (diacritiques) autant que possible

4. **Étymologies vérifiées** — ne pas inventer de chaînes étymologiques

5. **Aucun contenu inapproprié**

6. **Mots prophétiques/coraniques** : noter la mention coranique ou hadith si applicable (ex: زنجبيل mentionné en سورة الإنسان: 17)

## Mode de travail

- Livrer par catégorie complète (un fichier JSON par phase)
- Format JSON valide uniquement (pas de markdown dans les blocs JSON)
- Attendre "go" entre chaque phase
- Après validation de chaque fichier JSON, intégrer dans jisr-v1.0.html et livrer une nouvelle version de l'app

## Pour démarrer

Réponds simplement : **"Prêt. Quelle catégorie en premier ?"**

Puis attends mon instruction. Je dirai **go** pour démarrer chaque phase.
