<h1> Code documentation </h1>

[⌂](README.md) ›

Table of Contents
- [Dependencies](#dependencies)
- [Naming convention](#naming-convention)
- [User macros](#user-macros)
  - [new phrase](#new-phrase)
  - [renew phrase](#renew-phrase)
  - [provide phrase](#provide-phrase)
  - [declare phrase](#declare-phrase)
  - [new expression](#new-expression)
  - [renew expression](#renew-expression)
  - [provide expression](#provide-expression)
  - [declare expression](#declare-expression)
- [Internal macros](#internal-macros)
  - [Render Phrase](#render-phrase)
  - [Link Deprecated Macro](#link-deprecated-macro)
  - [Throw Star Required](#throw-star-required)
  - [Warn Deprecated](#warn-deprecated)
- [Internal constants](#internal-constants)
  - [package Name](#package-name)
- [Deprecated macros](#deprecated-macros)

# Dependencies
| Package | Usage                                                      | Used macros           |
| ------- | ---------------------------------------------------------- | --------------------- |
| xparse  | create macros with stars, optional and mandatory arguments | `\NewDocumentCommand` |

# Naming convention

- **User macros**  
    `\⟨all lower case⟩`
- **Internal macros**  
    `\⟨Upper Camel Case⟩@⟨namespace⟩`
- **Internal variables**  
    `\⟨lower Camel Case⟩@⟨namespace⟩`

# User macros
User macros are accessible everywhere within the project.

## new phrase
```latex
\newphrase{\⟨macro name⟩}{⟨text⟩}
```
- Create a macro to use text repeatedly
- **@param** #1 ⟨macro name⟩: name of the macro to be created
- **@param** #2 ⟨text⟩: words to be printed
- **@throws** ERROR if ⟨macro name⟩ has already been defined

## renew phrase
```latex
\renewphrase{\⟨macro name⟩}{⟨text⟩}
```
- Analog to `\newphrase`, but explicitly replaces an existing macro.
- **@throws** ERROR if ⟨macro name⟩ has not previously been defined

## provide phrase
```latex
\providephrase{\⟨macro name⟩}{⟨text⟩}
```
- Analog to `\newphrase`, but only creates the macro if it has not been defined yet. Never overrides.

## declare phrase
`\declarephrase{\⟨macro name⟩}{⟨text⟩}`
- Analog to `\newphrase`, but will always create the new definition, irrespective of any existing ⟨macro name⟩ with the same name
- this should be used sparingly


## new expression
```latex
\newexpression{\⟨macro name⟩}{⟨math content⟩}
```
- Create a macro to use math expressions repeatedly
- **@param** #1 ⟨macro name⟩: name of macro to be created
- **@param** #2 ⟨math content⟩: mathematical term to be printed
- **@throws** ERROR if ⟨macro name⟩ has already been defined

Implementation
- Ensures math mode for ⟨math content⟩
- Calls `\newphrase` 


## renew expression
```latex
\renewexpression{\⟨macro name⟩}{⟨math content⟩}
```
- Analog to `\newexpression`, but explicitly replaces an existing macro.
- **@throws** ERROR if ⟨macro name⟩ has not previously been defined

## provide expression
```latex
\provideexpression{\⟨macro name⟩}{⟨math content⟩}
```
- Analog to `\newexpression`, but only creates the macro if it has not been defined yet. Never overrides.

## declare expression
`\declareexpression{\⟨macro name⟩}{⟨math content⟩}`
- Analog to `\newexpression`, but will always create the new definition, irrespective of any existing ⟨macro name⟩ with the same name
- this should be used sparingly

# Internal macros

## Render Phrase
```latex
\RenderSnippet@spt{⟨content⟩}{⟨blame macro⟩}⟨is starred⟩
```
- **@param** #1 ⟨content⟩: content to be rendered
- **@param** #2 ⟨blame macro⟩: macro used to create the phrase or expression
- **@param** #3 ⟨is starred⟩: (boolean) is the star-variant of the blamed macro called?
- **@throws** *Star required* if used in text mode with the non-star-variant.
- displays the content of the phrase or expression

## Link Deprecated Macro
```latex
\LinkDeprecatedMacro@spt{⟨correct macro⟩}{⟨deprecated macro⟩}
```
- **@param** #1 ⟨correct macro⟩: up-to-date macro name
- **@param** #2 ⟨deprecated macro⟩: old macro name
- **@warns** that the deprecated macro should be replaced
- deprecated macros will call the up-to-date equivalents

## Throw Star Required
```latex
\ThrowStarRequired@spt{⟨blame macro⟩}
```
- **@param** #1 ⟨blame macro⟩: macro blamed in warning prompt

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

- `\newexpression` is used for `\newmathsymbol` or `\newmathsnippet`
- `\renewexpression` is used for `\renewmathsymbol` or `\renewmathsnippet`
- `\provideexpression` is used for `\providemathsymbol` or `\providemathsnippet`
- `\declareexpression` is used for `\declaremathsymbol` or `\declaremathsnippet`