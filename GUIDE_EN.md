# TradAF Package User Guide

## Introduction

The TradAF package (Translation of Old French) is a LaTeX tool designed to create comparative bilingual editions of Old French texts with their contemporary French translations, accompanied by categorized translation notes.

## Installation

1. Place the `tradaf.sty` file in the same directory as your LaTeX document, or install it in your local texmf tree.

2. Ensure you have the following LaTeX packages installed:
   - `paracol` (for parallel columns)
   - `marginnote` (for margin notes)
   - `xcolor` (for colors)
   - `etoolbox` (for conditional logic)
   - `geometry` (for page layout)
   - `enumitem` (for lists)
   - `fontenc` (for font encoding)

## Basic Usage

### Minimal Document Structure

```latex
\documentclass{article}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage[french]{babel}
\usepackage{tradaf}

\begin{document}

\begin{translation}

\oldfrench
Your Old French text

\modernfrench
Your modern French translation

\end{translation}

\end{document}
```

## Note Categories

The package offers four categories of notes, each with its distinctive color:

### 1. Lexique/Vocabulary (Blue)
Notes on vocabulary, word meanings, etymology.

```latex
\notelexique{Vocabulary explanation}
```

### 2. Syntaxe/Syntax (Magenta)
Notes on sentence structure, word order.

```latex
\notesyntaxe{Syntax explanation}
```

### 3. Morphologie/Morphology (Green)
Notes on grammatical forms, conjugations, declensions.

```latex
\notemorphologie{Morphological explanation}
```

### 4. Autres/Others (Brown)
Miscellaneous notes: historical context, cultural references, etc.

```latex
\noteother{Contextual or cultural note}
```

## Category Filtering

### Show All Categories (default)

```latex
\showallcategories
```

### Show Only Specific Categories

```latex
\showonlycategories{lexique,syntaxe}
```

### Hide/Show Individually

```latex
\showlexique        % Show vocabulary notes
\hidelexique        % Hide vocabulary notes
\showsyntaxe        % Show syntax notes
\hidesyntaxe        % Hide syntax notes
\showmorphologie    % Show morphology notes
\hidemorphologie    % Hide morphology notes
\showothers         % Show other notes
\hideothers         % Hide other notes
```

## Advanced Features

### Verse Numbering

For poetry or versified texts:

```latex
\begin{translation}
\oldfrench
\verseline First verse in Old French\\
\verseline Second verse in Old French\\

\modernfrench
\verseline First translated verse\\
\verseline Second translated verse\\
\end{translation}
```

### Translation Sections

Organize your document into sections:

```latex
\begin{translationsection}{Section Title}
% Your translation content here
\end{translationsection}
```

This command:
- Creates a section title
- Automatically resets verse and note counters

## Complete Example

```latex
\documentclass[12pt,a4paper]{article}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage[french]{babel}
\usepackage{tradaf}

\title{The Song of Roland\\Bilingual Edition}
\author{Editor}
\date{\today}

\begin{document}

\maketitle

\begin{translationsection}{Laisse I}

\begin{translation}

\oldfrench
\verseline Carles li reis\notelexique{«reis»: old form of «roi» (king), from Latin \textit{rex}}, nostre emperere magnes\notelexique{«magnes» means «great»},\\
\verseline Set anz tuz pleins ad estét en Espaigne\notesyntaxe{Subject-verb inversion} :\\
\verseline Tresqu'en la mer cunquist la tere altaigne\notemorphologie{«cunquist»: simple past}.\\

\modernfrench
\verseline Charles the king, our great emperor,\\
\verseline Seven full years he has been in Spain:\\
\verseline To the sea he conquered the proud land.\\

\end{translation}

\end{translationsection}

\end{document}
```

## Customization

### Modify Category Colors

You can redefine colors in your preamble:

```latex
\definecolor{lexiquecolor}{RGB}{0,102,204}      % Blue (default)
\definecolor{syntaxecolor}{RGB}{204,0,102}      % Magenta (default)
\definecolor{morphologiecolor}{RGB}{0,153,51}   % Green (default)
\definecolor{otherscolor}{RGB}{153,76,0}        % Brown (default)
```

### Adjust Page Layout

The package automatically defines a layout with wide margins for notes. You can modify it:

```latex
\geometry{
  left=2cm,
  right=6cm,        % Wide margin for notes
  top=2cm,
  bottom=2cm,
  marginparwidth=5cm,
  marginparsep=0.5cm
}
```

## Usage Tips

1. **Note Placement**: Place note commands immediately after the relevant word or phrase.

2. **Multiple Notes**: You can add multiple notes of different categories at the same location.

3. **Different Versions**: Use filtering to create different versions of your document (student version, researcher version, etc.).

4. **Margins**: Ensure your margins are wide enough to accommodate notes. The default configuration provides 6cm for the right margin.

5. **Compilation**: Compile with `pdflatex` for best results.

## Troubleshooting

### Notes Overflow the Page

Increase the right margin width:

```latex
\geometry{right=7cm, marginparwidth=6cm}
```

### Columns Are Not Aligned

Make sure your `\oldfrench` and `\modernfrench` blocks are well balanced.

### Compilation Error

Check that all required packages are installed, especially `paracol` and `marginnote`.

## Support

For questions or suggestions, visit the project's GitHub repository: https://github.com/Cbarillot/TradAF
