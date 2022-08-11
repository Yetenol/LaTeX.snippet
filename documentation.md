<h1> Code documentation </h1>

[⌂](README.md) ›

Table of Contents
- [Naming convention](#naming-convention)
- [User macros](#user-macros)
  - [new snippet](#new-snippet)
  - [renew snippet](#renew-snippet)
  - [provide snippet](#provide-snippet)
  - [declare snippet](#declare-snippet)
  - [new math snippet](#new-math-snippet)
  - [renew math snippet](#renew-math-snippet)
  - [provide math snippet](#provide-math-snippet)
  - [declare math snippet](#declare-math-snippet)
- [Internal macros](#internal-macros)
  - [Render Snippet](#render-snippet)
  - [Throw Star Required](#throw-star-required)
  - [Warn Deprecated](#warn-deprecated)
- [Internal constants](#internal-constants)
  - [package Name](#package-name)
- [Deprecated macros](#deprecated-macros)

# Naming convention

- **User macros**  
    `\⟨all lower case⟩`
- **Internal macros**  
    `\⟨Upper Camel Case⟩@⟨namespace⟩`
- **Internal variables**  
    `\⟨lower Camel Case⟩@⟨namespace⟩`

# User macros
User macros are accessible everywhere within the project.

## new snippet
```latex
\newsnippet{\⟨macro name⟩}{⟨text⟩}
```
- Create a custom snippet to use math expressions repeatedly
- **@param** #1 ⟨macro name⟩: name of the mathematical macro or variable
- **@param** #2 ⟨math expression⟩: mathematical term that is printed
- **@throws** ERROR if ⟨macro name⟩ has already been defined

## renew snippet
```latex
\renewsnippet{\⟨macro name⟩}{⟨text⟩}
```
- Analog to `\newsnippet`, but explicitly replaces an existing macro.
- **@throws** ERROR if ⟨macro name⟩ has not previously been defined

## provide snippet
```latex
\providesnippet{\⟨macro name⟩}{⟨text⟩}
```
- Analog to `\newsnippet`, but only creates the macro if it has not been defined yet. Never overrides.

## declare snippet
`\declaresnippet{\⟨macro name⟩}{⟨text⟩}`
- Analog to `\newsnippet`, but will always create the new definition, irrespective of any existing ⟨macro name⟩ with the same name
- this should be used sparingly


## new math snippet
```latex
\newmathsnippet{\⟨macro name⟩}{⟨math expression⟩}
```
- Create a custom snippet to use math expressions repeatedly
- **@param** #1 ⟨macro name⟩: name of the mathematical macro or variable
- **@param** #2 ⟨math expression⟩: mathematical term that is printed
- **@throws** ERROR if ⟨macro name⟩ has already been defined

Implementation
- Ensures math mode for ⟨math expression⟩
- Calls `\newsnippet` 


## renew math snippet
```latex
\renewmathsnippet{\⟨macro name⟩}{⟨math expression⟩}
```
- Analog to `\newmathsnippet`, but explicitly replaces an existing macro.
- **@throws** ERROR if ⟨macro name⟩ has not previously been defined

## provide math snippet
```latex
\providemathsnippet{\⟨macro name⟩}{⟨math expression⟩}
```
- Analog to `\newmathsnippet`, but only creates the macro if it has not been defined yet. Never overrides.

## declare math snippet
`\declaremathsnippet{\⟨macro name⟩}{⟨math expression⟩}`
- Analog to `\newmathsnippet`, but will always create the new definition, irrespective of any existing ⟨macro name⟩ with the same name
- this should be used sparingly

# Internal macros

## Render Snippet
```latex
\RenderSnippet@spt{⟨snippet macro⟩}⟨is starred⟩{⟨text or expression⟩}
```
- **@param** #1 ⟨snippet macro⟩: macro that could get detokenized for a warning
- **@param** #2 ⟨is starred⟩: (boolean) is the starred versions of the snippet called?
- **@param** #3 ⟨text or expression⟩: content to be rendered

## Throw Star Required
```latex
\ThrowStarRequired@spt{⟨snippet macro⟩}
```
- **@param** #1 ⟨snippet macro⟩: macro blamed in warning prompt

## Warn Deprecated
```latex
\WarnDeprecated@spt{⟨correct macro⟩}{⟨deprecated macro⟩}
```
- **@param** #1 ⟨correct macro⟩: up-to-date macro name
- **@param** #2 deprecated macro⟩: old macro name

# Internal constants

## package Name
```latex
\packageName@spt
```

# Deprecated macros

- `\newmathsymbol` → `\newmathsnippet`
- `\renewmathsymbol` → `\renewmathsnippet`
- `\providemathsymbol` → `\providemathsnippet`
- `\declaremathsymbol` → `\declaremathsnippet`