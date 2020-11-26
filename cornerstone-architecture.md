| Cornerstone Architecture |
\--------------------------/

background:
- [Tree Grammar](tree-grammar.md)

A compiler can be thought of as a parser, a series of passes, and a generator,
all of which are composed in sequence.  The parser takes a string and creates a
tree.  The passes are operators that transform the tree.  The generator takes
the resultant tree and creates a string.  The input of the parser should be an
element of the input language which can be verified by its corresponding string
grammar, and the output of the generator is an element of the output language
which can be verified using another corresponding string grammar.

```
        parser             pass*             generator
text ------------> tree ---------->* tree ---------------> output
```

The parser must verify not only the structure of the input string, but by
construction, it also verifies the structure of the first tree.  The structure
of the input and output of each pass must also be checked in order to maintain
invariants about structure and to aid maintenance and refactoring in catching
errors early.  To support the parsing problem in generality, Cornerstone
separates the construction of trees with the verification of their structure.

The construction of trees is a problem of tree expression and representation,
the validation of tree structure is a problem solved by imposing a set of
hierarchical rules about the expectations of relationships of nodes in the tree.
Cornerstone solves the expression problem with Texps, or Tree Expressions, and
it solves the structural validation problem with the Matcher.

The separation simplifies the language specific section of the grammar to merely
describe the structure of the trees and not the syntactic features of the
language.  The tree expressions, the representations of the tree expressions,
the parser for those representations, and the tree structure validation process
form the foundation of the Cornerstone project.

the construction and representation of tree expressions:
- [Texp](texp.md)
  about: tree expressions
- [Representation](representation.md)
  about: texp representations
- [Parser](parser.md)
  about: the paren-rep parser
- [Matcher](matcher.md)
  about: the structural validator
