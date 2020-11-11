| Texp Grammars |
\---------------/

A Texp Grammar describes the possible lists of children a Texp of a certain type
of Texp can have.  A Texp Grammar is a grammar of trees, instead of a grammar of
string, thus it accepts or rejects a tree and not a string.

background:
- [Context-Free Grammars](cfg.md)
- [Tree Grammars](tree-grammar.md)

TODO

# Overview

A Texp Grammar is a set of productions.  Each production has a name and a rule.
A production name correlates to a non-terminal symbol in a string grammar, so
we'll call them _nonterminals_ from now on.  All nonterminals are capitalized.

Texp Grammars are themselves represented using Texps.

Conventionally non-leaf tags are represented with a keyword.
