# Create a phrase of text

Create an immutable phrase stored in a macro, to make sure that all its appearances throughout the document are identical.
```latex
\newphrase{\⟨macro name⟩}{⟨text⟩}
```
- `⟨macro name⟩`: name of the phrase be created
- `⟨text⟩`: words to be printed
- throws ERROR if ⟨macro name⟩ has already been defined
- prints the content using **text mode** (instead if math mode)

## Examples

Definition in the preample
```latex
\newphrase{\staff}{Max, Peter, Dan and Tom}
\newphrase{\diffiable}{%
    The function is continuous partial diffiable, \\
    so it is diffiable.
}
```

Usage in the document
```latex
Fortunately, \staff* helped me finish the project.

$$ f(x)=e^x $$
\diffiable*
```

## Variations

### newphrase  

Define a new phrase. **Recommended**
```latex
\newphrase{\⟨macro name⟩}{⟨text⟩}
```

### renewphrase  

Replace an existing macro with the phrase.
```latex
\renewphrase{\⟨macro name⟩}{⟨text⟩}
```

### providephrase  

Ensure the availability of the macro. Define a new phrase unless a macro with the same name already exists. Never overrides.
```latex
\providephrase{\⟨macro name⟩}{⟨text⟩}
```

### declarephrase  

Force define a phrase, irrespective of any previous definitions. This should be used sparingly!  
`\declarephrase{\⟨macro name⟩}{⟨text⟩}`  


# Create an expression of mathematical content

Create an immutable expression stored in a macro, to make sure that all its appearances throughout the document are identical.

```latex
\newexpression{\⟨macro name⟩}{⟨math content⟩}
```
- `⟨macro name⟩`: name of the mathematical symbol or variable
- `⟨math content⟩`: mathematical term that is displayed
- throws ERROR if ⟨macro name⟩ has already been defined
- prints the content using **math mode**

## Examples

Definition in the preample
```latex
\newexpression{\Rmax}{R_\mathrm{max}}
\newexpression{\bfg}{\left|\underline{H}\right|_\mathrm{dB}} % Betragsfrequenzgang
```

Usage in the document
```latex
The resistor \Rmax* has the characteristic value $\Rmax = \qty{10}{\kilo\ohm}$.
Let us consider the amount \bfg*.
```

## Variations

### newexpression  

Define a new expression. **Recommended**
```latex
\newexpression{\⟨macro name⟩}{⟨math content⟩}
```

### renewexpression  

Replace an existing macro with the expression.
```latex
\renewexpression{\⟨macro name⟩}{⟨math content⟩}
```

### provideexpression  

Ensure the availability of the macro. Define a new expression unless a macro with the same name already exists. Never overrides.
```latex
\provideexpression{\⟨macro name⟩}{⟨math content⟩}
```

### declareexpression  

Force define an expression, irrespective of any previous definitions. This should be used sparingly!  
`\declareexpression{\⟨macro name⟩}{⟨math content⟩}`  