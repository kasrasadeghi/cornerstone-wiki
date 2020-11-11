| S-expression |
\--------------/

# S-expressions and Subtree Parsing

The S-expression is a parenthetical representation of a tree of nodes.  The
nodes in S-expressions are a disjunction, either an _atom_ or a _list_.  An atom
carry a symbol, while a list carries many other S-expressions.  The inner nodes
of the S-expression trees do not have a value, thus to understand what a subtree
represents it is necessary to dive into the S-expression or to look at the
surrounding context.

example:
```lisp
; add the following bindings to the environment {a -> 5, b -> 6}
(let ((a 5) (b 6)))

; the subtree ((a 5) (b 6)) is meaningless without the surrounding list
; with the 'let' atom as its first child
```

# Subtree Disambiguation

In contrast, a Texp is not a disjunctive tree.  Every node in the tree has a
value.  For leaf nodes, these values are often names or values.  Some examples
of names are function or variables names.  Some examples of values are integer
and string literals.  The difference with S-expressions lies in the inner
nodes.

Inner nodes in a Texp still have string values and they serve to identify and
disambiguate the kind of subtree it is.  We called the string values of inner
nodes _tags_.  Tags can be thought of as the "type" of a subtree.

example:
```texp
(+ (+ a b) 10)
```

# Human Parsing Problem
