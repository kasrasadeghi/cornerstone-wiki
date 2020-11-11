| Texp Parser |
\-------------/

TODO restructure
- need to separate the Texp Parser and the discussion of representations

# The Parsing Problem

Parsers solve the problems of language representation, which comes with the
problems of ambiguity and precedence.  A tree representation solves all three,
so the Cornerstone framework is built around a tree representation, the Texp.

background:
- [Texp](texp.md)

# Representation

Texps have two representations: the parenthetical representation (paren-rep) and
the indentation representation (tab-rep).  Here are some examples of the same
texps represented in either representation.

example 1:
```
(a (b c d) e)
=>
a
  b
    c
    d
  e
```

example 2:
```
(say "hello world")
=>
say
  "hello world"
```

example 3:
```
      (a) == a

  (a (b)) == (a b)

(a (b) c) == (a b c)
```


differences:
- paren-rep
  - does not allow unquoted spaces
  - easier to parse
    - a substring of paren-rep at the boundaries of an expression is a subtexp
- tab-rep
  - vertically expansive
  - harder to parse for a compiler

# Tags: The Ambiguity Problem

Ambiguity in a language comes from two sources: alternation and repetition.
Alternation is deciding what type of expression something is, and repetition is
deciding how many of an expression are all grouped as the same thing.  For
example, the arguments for a function call may be other function calls or a
binary operation like plus.  To decide between them, you only have to parse the
tag which appears at the beginning of the representation.

The Texp representation uses inner node values to disambiguate between
alternative structures for the parsed subtree.  When given any subtree, reading
the tag allows for both the human parser and the programmed parser to understand
what the rest of the subtree is.

see:
- [Texp](texp.md)
  about: See section "Tags" for more

In the following example, both the human and the parser only need to read the
first word after the '(' to know what the Texp at that level is supposed to
represent.

```
; parenthetical representation
(+ (call foo (args 5 6)) (+ 10 11))
```

see:
- [Grammar](texp-grammar.md)
  about: how grammars use tags to disambiguate
- [Matcher](matcher.md)
- [S-expression](sexp.md)
  about: S-expressions vs Texps. The Human Parsing Problem is a specifically
  interesting section.


# Tree Structuring: The Precedence Problem

Expressions in a language are organized into hierarchical groups in order to
determine the order of operations.  The order of operations in binary
expressions is specifically called _precedence_.  Because our representations
are representations of trees, the language designers can rely on the structuring
of the trees themselves to resolve precedence.

see:
- [Factor](factorcode.org)
  about: an interesting example of a non-hierarchical, _concatenative_
  programming language
