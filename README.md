# snippet - A LaTeX package to unify repeated text

Define phrases or expressions to insert them later in different places. This ensures that all appearances are identical.

- [User manual](User%20manual.md)
- [Code documentation](Code%20documentation.md)
- [Source code](snippet.sty)

## Installation

Add file **from External URL**  
- Create a `./sty` subfolder and add the external file `snippet.sty` using the following url. _Overleaf_ supports this as well.
```
https://raw.githubusercontent.com/Yetenol/LaTeX.snippet/main/snippet.sty
```

Add file **manually**  
- Create a `./sty` subfolder and add the file [`snippet.sty`](snippet.sty)

## Usage

**Use package** in the preamble
```latex
\usepackage{sty/snippet}
```

## Package information

- TeX Format:        `LaTeX2e`
- Required location: `./sty/snippet.sty`

# Inspiration

- [listofsymbols](https://texdoc.org/serve/listofsymbols/0)
- [nomencl](https://texdoc.org/serve/nomencl/0)