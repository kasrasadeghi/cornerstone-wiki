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

The parser must verify not only the structure of the input string, but by
construction, it also verifies the structure of the first tree.  To support
the parsing problem in generality,
