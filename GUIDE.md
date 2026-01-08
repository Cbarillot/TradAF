# Guide d'utilisation du package TradAF

## Introduction

Le package TradAF (Traduction d'Ancien Français) est un outil LaTeX conçu pour créer des éditions bilingues comparatives de textes en ancien français avec leur traduction en français contemporain, accompagnées de notes de traduction catégorisées.

## Installation

1. Placez le fichier `tradaf.sty` dans le même répertoire que votre document LaTeX, ou installez-le dans votre arborescence texmf locale.

2. Assurez-vous d'avoir les packages LaTeX suivants installés :
   - `paracol` (pour les colonnes parallèles)
   - `marginnote` (pour les notes en marge)
   - `xcolor` (pour les couleurs)
   - `etoolbox` (pour la logique conditionnelle)
   - `geometry` (pour la mise en page)
   - `enumitem` (pour les listes)
   - `fontenc` (pour l'encodage des polices)

## Utilisation de base

### Structure minimale du document

```latex
\documentclass{article}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage[french]{babel}
\usepackage{tradaf}

\begin{document}

\begin{translation}

\oldfrench
Votre texte en ancien français

\modernfrench
Votre traduction en français moderne

\end{translation}

\end{document}
```

## Catégories de notes

Le package propose quatre catégories de notes, chacune avec sa couleur distinctive :

### 1. Lexique (Bleu)
Notes sur le vocabulaire, le sens des mots, l'étymologie.

```latex
\notelexique{Explication du vocabulaire}
```

### 2. Syntaxe (Magenta)
Notes sur la structure des phrases, l'ordre des mots.

```latex
\notesyntaxe{Explication de la syntaxe}
```

### 3. Morphologie (Vert)
Notes sur les formes grammaticales, conjugaisons, déclinaisons.

```latex
\notemorphologie{Explication morphologique}
```

### 4. Autres (Marron)
Notes diverses : contexte historique, références culturelles, etc.

```latex
\noteother{Note contextuelle ou culturelle}
```

## Filtrage des catégories

### Afficher toutes les catégories (par défaut)

```latex
\showallcategories
```

### Afficher uniquement certaines catégories

```latex
\showonlycategories{lexique,syntaxe}
```

### Masquer/Afficher individuellement

```latex
\showlexique        % Afficher les notes de lexique
\hidelexique        % Masquer les notes de lexique
\showsyntaxe        % Afficher les notes de syntaxe
\hidesyntaxe        % Masquer les notes de syntaxe
\showmorphologie    % Afficher les notes de morphologie
\hidemorphologie    % Masquer les notes de morphologie
\showothers         % Afficher les autres notes
\hideothers         % Masquer les autres notes
```

## Fonctionnalités avancées

### Numérotation des vers

Pour la poésie ou les textes versifiés :

```latex
\begin{translation}
\oldfrench
\verseline Premier vers en ancien français\\
\verseline Deuxième vers en ancien français\\

\modernfrench
\verseline Premier vers traduit\\
\verseline Deuxième vers traduit\\
\end{translation}
```

### Sections de traduction

Organiser votre document en sections :

```latex
\begin{translationsection}{Titre de la section}
% Votre contenu de traduction ici
\end{translationsection}
```

Cette commande :
- Crée un titre de section
- Réinitialise automatiquement les compteurs de vers et de notes

## Exemple complet

```latex
\documentclass[12pt,a4paper]{article}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage[french]{babel}
\usepackage{tradaf}

\title{La Chanson de Roland\\Édition bilingue}
\author{Éditeur}
\date{\today}

\begin{document}

\maketitle

\begin{translationsection}{Laisse I}

\begin{translation}

\oldfrench
\verseline Carles li reis\notelexique{«reis» : forme ancienne de «roi», du latin \textit{rex}}, nostre emperere magnes\notelexique{«magnes» signifie «grand»},\\
\verseline Set anz tuz pleins ad estét en Espaigne\notesyntaxe{Inversion sujet-verbe} :\\
\verseline Tresqu'en la mer cunquist la tere altaigne\notemorphologie{«cunquist» : passé simple}.\\

\modernfrench
\verseline Charles le roi, notre grand empereur,\\
\verseline Sept ans entiers a été en Espagne :\\
\verseline Jusqu'à la mer il conquit la terre altière.\\

\end{translation}

\end{translationsection}

\end{document}
```

## Personnalisation

### Modifier les couleurs des catégories

Vous pouvez redéfinir les couleurs dans votre préambule :

```latex
\definecolor{lexiquecolor}{RGB}{0,102,204}      % Bleu par défaut
\definecolor{syntaxecolor}{RGB}{204,0,102}      % Magenta par défaut
\definecolor{morphologiecolor}{RGB}{0,153,51}   % Vert par défaut
\definecolor{otherscolor}{RGB}{153,76,0}        % Marron par défaut
```

### Ajuster la mise en page

Le package définit automatiquement une mise en page avec de larges marges pour les notes. Vous pouvez la modifier :

```latex
\geometry{
  left=2cm,
  right=6cm,        % Large marge pour les notes
  top=2cm,
  bottom=2cm,
  marginparwidth=5cm,
  marginparsep=0.5cm
}
```

## Conseils d'utilisation

1. **Placement des notes** : Placez les commandes de notes immédiatement après le mot ou la phrase concernée.

2. **Notes multiples** : Vous pouvez ajouter plusieurs notes de différentes catégories au même endroit.

3. **Versions différentes** : Utilisez le filtrage pour créer différentes versions de votre document (version pour étudiants, version pour chercheurs, etc.).

4. **Marges** : Assurez-vous que vos marges sont suffisamment larges pour accueillir les notes. La configuration par défaut prévoit 6 cm pour la marge droite.

5. **Compilation** : Compilez avec `pdflatex` pour de meilleurs résultats.

## Dépannage

### Les notes débordent de la page

Augmentez la largeur de la marge droite :

```latex
\geometry{right=7cm, marginparwidth=6cm}
```

### Les colonnes ne sont pas alignées

Assurez-vous que vos blocs `\oldfrench` et `\modernfrench` sont bien équilibrés.

### Erreur de compilation

Vérifiez que tous les packages requis sont installés, en particulier `paracol` et `marginnote`.

## Support

Pour des questions ou des suggestions, consultez le dépôt GitHub du projet : https://github.com/Cbarillot/TradAF
