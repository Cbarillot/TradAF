# Compilation Guide for Cligès Document

## Quick Start

To compile the `Cliges_v2345-2497.tex` document, you need two files in the same directory:

1. **Cliges_v2345-2497.tex** - The main document
2. **tradaf.sty** - The custom LaTeX package (included in this repository)

## Compilation Steps

### On Your Local Machine

1. Ensure both files are in the same directory
2. Run: `pdflatex Cliges_v2345-2497.tex`
3. The output will be `Cliges_v2345-2497.pdf`

### On Overleaf

1. Create a new project or open an existing one
2. **Upload both files**:
   - `Cliges_v2345-2497.tex`
   - `tradaf.sty` ⚠️ **This is required!**
3. Set `Cliges_v2345-2497.tex` as the main document
4. Click "Recompile"

## Troubleshooting

### Error: "File `tradaf.sty' not found"

**Cause**: The `tradaf.sty` file is not in the same directory as your `.tex` file.

**Solution**:
- **On Overleaf**: Make sure you've uploaded `tradaf.sty` to your project. Check the file list on the left sidebar.
- **On local machine**: Copy `tradaf.sty` to the same folder as `Cliges_v2345-2497.tex`

### Required LaTeX Packages

The `tradaf.sty` package automatically loads these packages (they must be installed in your LaTeX distribution):
- `paracol` - for parallel columns
- `marginnote` - for margin notes
- `xcolor` - for color coding
- `etoolbox` - for toggles and conditional logic
- `geometry` - for page layout
- `enumitem` - for customized lists
- `fontenc` - for font encoding

Most LaTeX distributions (TeX Live, MiKTeX) include these packages by default.

## Files in This Repository

- **Cliges_v2345-2497.tex** - Main document with Old French and modern translation
- **tradaf.sty** - Custom LaTeX package for parallel translation layout
- **example.tex** - Example usage of the tradaf package
- **template.tex** - Template for creating new translation documents
- **NT1.md** - Documentation of translation note categories
- **README.md** - Package documentation

## Additional Examples

See `example.tex` for more examples of using the tradaf package features.

Compile it with:
```bash
pdflatex example.tex
```

## Support

For issues with:
- **tradaf.sty package**: See README.md for detailed usage instructions
- **Translation notes**: See NT1.md for note categorization system
- **Technical details**: See TRANSFORMATION_SUMMARY.md
