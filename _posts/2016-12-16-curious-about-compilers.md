---
layout: post
title:  "Curious about compilers"
date:   2016-12-16
categories: compilers
---


I have always been curious about compilers & transpilers. Let's dig into them.

The three primary stages:

* Parsing
* Transformation
* Code Generation

**Parsing**, take raw code and create a structure of the code in memory.

* Lexical analysis - take the code apart and create tokens - use a lexer/tokenizer

* Syntactic analysis - relates describe tokens and relate then to each other - resulting in a AST (abstract syntax tree). An AST - a deeply nested object that is easy to work with.

**Transformation**, takes the in memory structure of the code and do something with it.

**Code generation**, takes the transformed structure and create new code from it.
