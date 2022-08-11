<h1> User manual </h1>

[⌂](README.md) ›

Table of Contents
- [Create text snippet](#create-text-snippet)

## Store a text block as a snippet
Create an immutable text block, called a snippet, to make sure that all its appearances are identical.
```latex
\newsnippet{\⟨macro name⟩}{⟨text⟩}
```
- **⟨macro name⟩**: name of the text module
- **⟨text⟩**: words displayed for each appearance
- throws ERROR if ⟨macro name⟩ has already been defined

Examples
- Definition in the preample
    ```latex
    \newsnippet{\collabs}{Max, Peter, Dan and Tom}
    \newsnippet{\diffiable}{%
        The function is continuous partial diffiable, \\
        so it is diffiable.
    }
    ```
- Usage in the document
    ```latex
    Fortunately, \collabs* helped me finish the project.
    
    $$ f(x)=e^x $$
    \diffiable*
    ```
Variations
- **newsnippet**  
    Create a new snippet. **Recommended**
    ```latex
    \newsnippet{\⟨macro name⟩}{⟨text⟩}
    ```
- **renewsnippet**  
    Explicitly replace an existing macro.
    ```latex
    \renewsnippet{\⟨macro name⟩}{⟨text⟩}
    ```
- **providesnippet**  
    Only creates the snippet if no macro with the same name exists. Never overrides.
    ```latex
    \providesnippet{\⟨macro name⟩}{⟨text⟩}
    ```
- **declaresnippet**  
    Will always create and override the snippet, irrespective of any previous definitions.  
    This should be used sparingly!  
    `\declaremathsymbol{\⟨macro name⟩}{⟨text⟩}`  


## Store a mathematical expression as a snippet
Create an immutable mathematical expression block, called a math snippet, to make sure that all its appearances are identical.

```latex
\newmathsymbol{\⟨macro name⟩}{⟨math expression⟩}
```
- **⟨macro name⟩**: name of the mathematical symbol or variable
- **⟨math expression⟩**: mathematical term that is displayed
- throws ERROR if ⟨macro name⟩ has already been defined

Examples
- Definition in the preample
    ```latex
    \newmathsymbol{\Rmax}{R_\mathrm{max}}
    \newmathsymbol{\bfg}{\left|\underline{H}\right|_\mathrm{dB}} % Betragsfrequenzgang
    ```
- Usage in the document
    ```latex
    The resistor \Rmax* has the characteristic value $\Rmax = \qty{10}{\kilo\ohm}$.
    Let us consider the amount \bfg*.
    ```

Variations
- **newmathsymbol**  
    Create a new math snippet. **Recommended**
    ```latex
    \newmathsymbol{\⟨macro name⟩}{⟨math expression⟩}
    ```
- **renewmathsymbol**  
    Explicitly replace an existing macro.
    ```latex
    \renewmathsymbol{\⟨macro name⟩}{⟨math expression⟩}
    ```
- **providemathsymbol**  
    Only creates the math snippet if no macro with the same name exists. Never overrides.
    ```latex
    \providemathsymbol{\⟨macro name⟩}{⟨math expression⟩}
    ```
- **declaremathsymbol**  
    Will always create and override the math snippet, irrespective of any previous definitions.  
    This should be used sparingly!  
    `\declaremathsymbol{\⟨macro name⟩}{⟨math expression⟩}`  