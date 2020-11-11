| Lexer-Parser |
\--------------/

background:
- [Texp Overview](texp.md)
- [Parser](texp.md)
- [Parser technical documentation](parser-tech.md)

As the problem of parsing Texps is not significantly more complicated than a
matched parenthesis parser, i.e. it is very simple, so a separate lexer is not
needed in order to simplify the parsing process.  Instead the parser stores
lexical information that is relevant for error messaging and pretty-printing in
a separate data store during parse-time.  Because the parser lexes as well, we
sometimes call it a lexer-parser, especially when refering to it as the program
that accumulates lexical information.

The lexer-parser stores the coordinates of 4 different types of lexemes: opening
parentheses, closing parentheses, atoms, and comments.  The spans of each lexeme
depend on their type: parentheses are a single character long, comments are
until the end of the line, atoms are until the next special character.  Note
that whitespace is considered insignificant; only visual information is
recorded.

see:
- [Lexer-Parser technical](lexer-parser-tech.md)
- [Concrete Texps](concrete-texp.md)
