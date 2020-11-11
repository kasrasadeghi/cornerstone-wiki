| Texp |
\------/

A Texp is a tree of strings, thus it has a value that is a string and optionally
has a list of Texps that are its children.

Texps solve the problem of language structure.  A language that represent itself
as a string is often parsed as a tree of strings, a structure that compilers
operate on frequently.  In compiler literature, abstract and concrete parse
trees are often string trees.  As a compiler framework, Cornerstone makes a
large number of assumptions about the representation of string trees to simplify
working with them and modifying them, as Cornerstone must operates on a set of
languages and not a single language.

There is a further restricting set of simplifying assumptions made by Texp
Grammars and the Matcher.

see:
- [Texp Grammars](texp-grammar.md)
- [Matcher](matcher.md)

# Parser

I recommend reading about the Texp Parser for more intuition about the
parenthetical Texp representation that's used in the rest of this document.

see:
- [Texp Parser](parser.md)
  about: the parsing of different representations of Texps

# S-expressions

The parenthetical Texp representation is similar to S-expressions.  For those
familiar, see a comparison with S-expressions below.  The key difference is that
Texps are not a disjunctive type and thus the internal nodes of a Texp hold a
string value.

see:
- [S-expression](sexp.md)

# Tags

Texps are a string tree.  In every tree, there are inner and leaf nodes.  The
string value of inner nodes in a Texp are used to _tag_ the subtree with a
specific type of subtree, so we call them _tags_.  Leaf nodes represent values
in languages, such and string and integer literals.

```
(+ (call foo (args 5 6)) (+ 7 8))
```

See the above discussion of the Parser and the comparison with S-expressions for
more information.

TODO continue tags

# Subtexp and Texp Composition

TODO composition

# Allocation

Wasting space for the potential allocation of children in Texps that are
leaf nodes is seen as an optimization problem.

see:
- [Texp Allocator](allocator.md)
