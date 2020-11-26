| (complexity growth) | implies (staged compilation) |
\----------------------------------------------------/

> "Here at the end of Moore's Law, software is the hard part too"
> - Chris Lattner, in an interview with Lex Fridman about the future of computing
> - link: https://youtu.be/nWTvXbQHwWs?t=9650

part 1: (complexity growth) | implies meta-programming
---

As the complexity of software systems grows, I do not believe that programmers
will be more productive because their languages are more expressive.  I believe
that they will be more productive because their tools are more powerful.  For a
period of time, it was sufficient to keep increasing abstractions for languages
as Dennard scaling made the abstractions of tomorrow just as fast as the code of
today.  The increase of abstractions made it possible to organize larger amounts
of software with less code, as less was assumed about its intent and more of the
code's analysis available at runtime.  I believe the future of abstraction is
based on staged compilation, where the analysis and definition of code does not
happen at runtime, but at compile-time, to create domain specific languages
(DSLs) that address specific problems and to have these DSLs integrate with each
other.  When you restrict the possible things you can say to the computer, it
can give better error messages when something goes wrong.

part 2: meta-programming | implies (need for better error messaging)
---

To achieve this future, DSLs have to be as easy to write as the libraries we
have today.  Somewhat imprecisely, meta-programming can be seen as the features
a language has for contructing domain specific languages.  Meta-programming
systems are often treated as second-class citizens of the programming ecosystem
to the native compiler, with second-class error messages, debugging
capabilities, and tooling integration (see: [Thoughts on Lisp]).

part 3: (better error messaging) | implies (pass > macros)
---

Instead of making meta-programming within the programming language
easier, I intend to focus on making the compiler for the language accessible and
easier to write, maintain, and modify.  Thus instead of using the language to
make domain-specific languages, users will use the exact same tools as compiler
writers to make domain-specific languages.  This ties back to the central idea
of Cornerstone: instead of focusing on making the language more powerful, make
the tools around it, like those used to make the compiler, more powerful.  The
fundamental focus that Cornerstone focuses on is error messaging and providing a
powerful feedback loop to the compiler developer.

One way to extend a compiler is to add more passes [Dimensions of Compiler
Extension].  Passes provide one key benefit: they're ordered.  Cornerstone
explores passes as the foundation for meta-programming [Passes > Macros].

see:
- [Dimensions of Compiler Extension](dimension.md)
  about: passes vs other kinds of compiler extension
- [Passes > Macros](passes-over-macros.md)
- [Error Messaging and Feedback Loops](error-messaging.md)
- [Thoughts on Lisp](lisp.md)
