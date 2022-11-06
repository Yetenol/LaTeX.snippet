<h1> User manual </h1>

[⌂](README.md) ›

Table of Contents
- [Store a text block as a snippet](#store-a-text-block-as-a-snippet)
- [Store a mathematical expression as a snippet](#store-a-mathematical-expression-as-a-snippet)

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
    `\declaresnippet{\⟨macro name⟩}{⟨text⟩}`  


## Store a mathematical expression as a snippet
Create an immutable mathematical expression block, called a math snippet, to make sure that all its appearances are identical.

```latex
\newexpression{\⟨macro name⟩}{⟨math expression⟩}
```
- **⟨macro name⟩**: name of the mathematical symbol or variable
- **⟨math expression⟩**: mathematical term that is displayed
- throws ERROR if ⟨macro name⟩ has already been defined

Examples
- Definition in the preample
    ```latex
    \newexpression{\Rmax}{R_\mathrm{max}}
    \newexpression{\bfg}{\left|\underline{H}\right|_\mathrm{dB}} % Betragsfrequenzgang
    ```
- Usage in the document
    ```latex
    The resistor \Rmax* has the characteristic value $\Rmax = \qty{10}{\kilo\ohm}$.
    Let us consider the amount \bfg*.
    ```

Variations
- **newexpression**  
    Create a new math snippet. **Recommended**
    ```latex
    \newexpression{\⟨macro name⟩}{⟨math expression⟩}
    ```
- **renewexpression**  
    Explicitly replace an existing macro.
    ```latex
    \renewexpression{\⟨macro name⟩}{⟨math expression⟩}
    ```
- **provideexpression**  
    Only creates the math snippet if no macro with the same name exists. Never overrides.
    ```latex
    \provideexpression{\⟨macro name⟩}{⟨math expression⟩}
    ```
- **declareexpression**  
    Will always create and override the math snippet, irrespective of any previous definitions.  
    This should be used sparingly!  
    `\declareexpression{\⟨macro name⟩}{⟨math expression⟩}`  