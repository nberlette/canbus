---
description: Created by Landon Harris (lharri73).
---

# 🆚 VSCode Extension

![](https://img.shields.io/visual-studio-marketplace/v/lharri73.dbc?style=flat-square)

This extension provides basic syntax highlighting, bracket completion, code snippets, and syntax / parser errors for the Vector DBC file format.&#x20;

This is created to work with version 2 of the [Vector DBC file format](https://bitbucket.org/tobylorenz/vector\_dbc/src/master/).

Although DBC files are often programmatically generated, it can be useful to more easily read the DBC file itself in a plaintext format. Syntax highlighting is handled locally through VSCode's integrated TextMates language parsing engine, using PCRE regular expressions to match syntax.

### Syntax Highlighting

![](https://raw.github.com/bmwcd/DBC-Language-Syntax/master/res/syntax.png)

### Lexicographic and Parser Errors

![](https://raw.github.com/bmwcd/DBC-Language-Syntax/master/res/errors.gif)

### Commonly Used Snippets

![](https://raw.github.com/bmwcd/DBC-Language-Syntax/master/res/snippets.gif)

### Supported keywords

```
  - BA
  - BA_DEF
  - BA_DEF_DEF
  - BA_DEF_DEF_REL
  - BA_DEF_REL
  - BA_REL
  - BO
  - BO_TX_BU
  - BS
  - BU
  - BU_SG_REL
  - CM
  - EV
  - NS
  - SG
  - SGTYPE
  - SIG_GROUP
  - VAL
  - VAL_TABLE
  - VERSION
```

### Known Issues

1. Attribute definitions that wrap lines may not be highlighted on the following lines.
2. Multiplexed Signals are currently not recognized

### Todo

```
  - Make lexer and parser errors more useful
  - Add checks that prevent crashing when signals don't exist
  - Include debugging (invalid offset, start bit, min, max, etc)
  - Hover box to show all related fields as a hint
```

### License

```
  GNU General Public License v2.0 only
```
