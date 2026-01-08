# Notes de Traduction - Cligès v. 2345-2497

## Description

Ce document décrit l'organisation des notes de traduction pour le roman de Cligès (v. 2345-2497) de Chrétien de Troyes, intégré dans le fichier LaTeX `Cliges_v2345-2497.tex` utilisant le package `tradaf`.

## Structure des Notes

Les notes de traduction sont organisées en **quatre catégories principales**, chacune identifiée par une couleur distincte dans le document PDF final :

### 1. Lexique (Bleu)
**Commande LaTeX** : `\notelexique{...}`  
**Couleur** : Bleu (RGB: 0,102,204)

Notes concernant :
- Le vocabulaire et le sens des mots
- Les faux amis entre l'ancien français et le français moderne
- Les gloses et définitions (issues du DECT ou du glossaire de l'édition)
- L'étymologie des termes
- Les expressions idiomatiques

**Exemples** :
- `enor, s.m. : « marque de respect et d'estime, faveur » (DECT)`
- `sale, s.f., faux ami qui désigne aussi bien une pièce [...] que le palais`
- `vasselage : ensemble des qualités qui font d'un homme un bon vassal`

### 2. Syntaxe (Magenta)
**Commande LaTeX** : `\notesyntaxe{...}`  
**Couleur** : Magenta (RGB: 204,0,102)

Notes concernant :
- L'ordre des mots et la structure des phrases
- Les propositions subordonnées (complétives, relatives, circonstancielles)
- Les compléments d'objet et autres fonctions syntaxiques
- Les constructions particulières de l'ancien français

**Exemples** :
- `li rois Artus est le sujet de promist dont le COD est la complétive...`
- `Rétablir un ordre des mots fluide et conforme à la phrase moderne`
- `Les deux relatives introduites par ou ont toutes deux pour antécédent Bretaigne`

### 3. Morphologie (Vert)
**Commande LaTeX** : `\notemorphologie{...}`  
**Couleur** : Vert (RGB: 0,153,51)

Notes concernant :
- Les formes verbales (temps, modes, personnes)
- Les déclinaisons et cas (CS/CR, CSFS, CRPM, etc.)
- Les formes grammaticales particulières
- Les conjugaisons et variations morphologiques

**Exemples** :
- `iert : futur P3 estre`
- `pot : PS3 pooir`
- `graindre : comparatif de supériorité CSFS de grand`
- `ert : indicatif impft. estre (P3 forme étymologique)`

### 4. Autres (Marron)
**Commande LaTeX** : `\noteother{...}`  
**Couleur** : Marron (RGB: 153,76,0)

Notes concernant :
- Le contexte historique et culturel
- Les conventions littéraires
- Les références intertextuelles
- Les commentaires du narrateur
- Les variations manuscrites

**Exemples** :
- `Le 'don contraignant' est une convention littéraire arthurienne`
- `Illustration de la 'fin'amor' où le désir de la dame prime`
- `Les vers entre crochets sont absents du manuscrit A (Guiot)`

## Sources des Notes

Les notes proviennent de trois sources principales :

### 1. Tableau CSV
Le fichier `Tableau de Traduction Juxtalinéaire et d'Analyse Philologique du Roman de Cligès - Table 1.csv` contient :
- **Colonne 1** : Texte en ancien français (vers séparés par " / ")
- **Colonne 2** : Traduction en français contemporain
- **Colonne 3** : Notes de traduction générales
- **Colonne 4** : Informations de syntaxe ou morphologie

### 2. Notes Détaillées Originales
Le fichier `Cliges_v2345-2497.tex` original contenait des notes détaillées organisées par numéro de vers (v. 2345, v. 2346--2350, etc.), comprenant :
- Des explications lexicales approfondies
- Des analyses syntaxiques détaillées
- Des observations morphologiques
- Des remarques sur les traductions possibles

### 3. Catégorisation Automatique
Un algorithme a été utilisé pour catégoriser automatiquement les notes selon leur contenu :
- Détection de mots-clés spécifiques à chaque catégorie
- Priorisation : Morphologie > Syntaxe > Lexique > Autres
- Vérification manuelle pour les cas ambigus

## Intégration dans le Document

### Layout Parallèle
Le document utilise l'environnement `translation` du package `tradaf` pour créer deux colonnes :
- **Colonne gauche** : Texte en ancien français (en italique)
- **Colonne droite** : Traduction en français contemporain

### Notes Marginales
Les notes apparaissent dans la marge droite avec :
- Un numéro de référence dans le texte
- La catégorie en petites capitales
- Le texte de la note en couleur

### Organisation par Section
Chaque groupe de vers forme une section (`translationsection`) avec :
- Un titre indiquant la plage de vers (ex: "v. 2345--2350")
- Réinitialisation de la numérotation des vers
- Réinitialisation de la numérotation des notes

## Utilisation

### Compilation
```bash
pdflatex Cliges_v2345-2497.tex
```

### Filtrage des Catégories
Le package `tradaf` permet de filtrer les catégories de notes affichées :

```latex
% Afficher toutes les catégories
\showallcategories

% Afficher uniquement lexique et syntaxe
\showonlycategories{lexique,syntaxe}

% Masquer la morphologie
\hidemorphologie
```

## Abréviations Utilisées

- **CS/CR** : Cas sujet / Cas régime
- **F/M** : Féminin / Masculin
- **S/P** : Singulier / Pluriel
- **CRA** : Cas régime absolu
- **PS** : Passé simple
- **IP** : Présent de l'indicatif
- **P1-P6** : Personnes grammaticales (1ère à 6ème)
- **PPS/PPC** : Pronom personnel sujet / complément
- **DECT** : Dictionnaire Électronique de Chrétien de Troyes
- **gl** : Glose du glossaire de l'édition au programme

## Références

- **Édition** : Laurence Harf-Lancner, Paris, Champion, Champion Classiques Moyen Âge, 2006
- **DECT** : http://zeus.atilf.fr/dect/
- **Grammaire** : Claude Buridant, *Grammaire nouvelle de l'ancien français*, Paris, Sedes, 2000

## Remarques Techniques

### Échappement du Texte
Les notes extraites du fichier original ont été nettoyées pour éviter les conflits LaTeX :
- Suppression des commandes `\textit{}`, `\textbf{}`, etc. dans les notes
- Conversion des symboles mathématiques (`\Rightarrow` → `=>`)
- Limitation de la longueur des notes à 250 caractères maximum

### Mapping Vers-Note
Les notes détaillées sont associées au premier vers de leur plage :
- v. 2345 : note attachée au vers 2345
- v. 2349--2350 : note attachée au vers 2349
- Les notes du CSV sont ajoutées à la fin de chaque groupe de vers

## Contact

Pour toute question sur la structure des notes ou le processus de catégorisation, consulter le dépôt GitHub du projet TradAF.
