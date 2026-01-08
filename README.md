# TradAF - Comparative Old French Translation Package

TradAF is a LaTeX package designed for creating comparative translations between Old French (Ancien Français) texts and their contemporary French translations, with categorized translation notes displayed in the margin.

## Features

- **Parallel text layout**: Original Old French text alongside contemporary French translation
- **Categorized margin notes**: Translation notes organized by category
  - **Lexique** (Vocabulary): Notes about word meanings and etymology
  - **Syntaxe** (Syntax): Notes about sentence structure and word order
  - **Morphologie** (Morphology): Notes about grammatical forms
  - **Autres** (Others): Miscellaneous notes (historical context, cultural references, etc.)
- **Category filtering**: Show or hide specific categories of notes
- **Color-coded notes**: Each category has a distinct color for easy identification
- **Verse numbering**: Optional line numbering for poetry

## Installation

1. Download `tradaf.sty` and place it in your LaTeX project directory, or install it in your local texmf tree.

2. Include the package in your LaTeX document:
```latex
\usepackage{tradaf}
```

## Quick Start

Here's a minimal example:

```latex
\documentclass{article}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{tradaf}

\begin{document}

\begin{translation}

\oldfrench
Carles li reis\notelexique{«reis» : forme ancienne de «roi»}

\modernfrench
Charles le roi

\end{translation}

\end{document}
```

## Usage

### Basic Structure

Use the `translation` environment to create parallel text:

```latex
\begin{translation}

\oldfrench
% Your Old French text here
% Add notes with \notelexique{}, \notesyntaxe{}, etc.

\modernfrench
% Your contemporary French translation here

\end{translation}
```

### Adding Notes

Add categorized notes inline with your text:

```latex
\notelexique{Vocabulary note}
\notesyntaxe{Syntax note}
\notemorphologie{Morphology note}
\noteother{Other note}
```

Notes appear in the margin with a numbered reference and are color-coded by category.

### Filtering Categories

Control which categories of notes are displayed:

```latex
% Show all categories (default)
\showallcategories

% Show only specific categories
\showonlycategories{lexique,syntaxe}

% Show/hide individual categories
\showlexique
\hidelexique
\showsyntaxe
\hidesyntaxe
\showmorphologie
\hidemorphologie
\showothers
\hideothers
```

### Line Numbering

For poetry or verse, add line numbers:

```latex
\begin{translation}
\oldfrench
\verseline First line of verse\\
\verseline Second line of verse\\

\modernfrench
\verseline First line of translation\\
\verseline Second line of translation\\
\end{translation}
```

Reset the counter with `\resetverseline` if needed.

### Translation Sections

Organize your document into sections:

```latex
\begin{translationsection}{Title of Section}
% Translation content here
\end{translationsection}
```

This automatically resets verse and note counters for each section.

## Color Scheme

The package uses the following color scheme for categories:

- **Lexique**: Blue (RGB: 0,102,204)
- **Syntaxe**: Magenta (RGB: 204,0,102)
- **Morphologie**: Green (RGB: 0,153,51)
- **Autres**: Brown (RGB: 153,76,0)

## Complete Example

See `example.tex` for a comprehensive demonstration of all features, including:
- Multiple translation sections
- All four categories of notes
- Category filtering examples
- Both verse and prose examples
- Usage instructions

To compile the example:

```bash
pdflatex example.tex
```

## Requirements

The package requires the following LaTeX packages (automatically loaded):
- `paracol` - for parallel columns
- `marginnote` - for margin notes
- `xcolor` - for color coding
- `etoolbox` - for toggles and conditional logic
- `geometry` - for page layout
- `enumitem` - for customized lists
- `fontenc` - for font encoding

## Tips

1. **Wide margins**: The package sets wide right margins (6cm) for notes. Adjust if needed by modifying the geometry settings in `tradaf.sty`.

2. **Note placement**: Notes appear at the position where the command is placed in the text. Place them close to the relevant word or phrase.

3. **Multiple notes**: You can add multiple notes of different categories at the same location.

4. **Selective compilation**: Use category filtering to create different versions of your document for different audiences (e.g., students might see only lexique notes, while researchers see all categories).

## License

This package is provided as-is for academic and educational use.

## Contributing

Contributions, bug reports, and feature requests are welcome on the GitHub repository.