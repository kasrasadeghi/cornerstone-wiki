# wiki root
- created: oct 18

The Cornerstone project's premise is to focus on the problems that lie in the
ecosystem of programming languages and thus deliberately minimizing the
complexity of the programming language.  The ecosystem of a programming language
is composed of many tools that integrate and interact with each other.  The
fundamental tool for a programming language is a compiler, and thus the focus of
the project is the eponymous Cornerstone Compiler Framework.

see:
- [Feature Layers](feature-layers.md)
  about: the layers of features in an ecosystem
- [Meta Conversations and the Programmer-Computer Dialogue](meta-conversation.md)
  about: the relationship between language complexity, discussions, and
  meta-discussions

Cornerstone tackles many of the problems in developing, designing, and
maintaining a compiler, and it's designed to minimize the reduplication of
effort in using pieces of the compiler to create other tools in the ecosystem.

Cornerstone investigates the trade-off between features _in_ a language and
features _around_ it, primarily reducing the complexity and minimizing features
within a language to benefit the tooling around the language.  Features that are
minimized with languages created with Cornerstone include the complexity of the
syntax of the language and a restriction for the framework itself to use
low-level language features that exist or can be emulated in other systems
programming languages.

Cornerstone focuses on error messages and other forms of powerful communication
from inside the compiler to the developer.

see:
- [Error Messaging Primacy](error-messages.md)


- update: oct 23

Syntax is the discussion of the problem of language representation.  Cornerstone
handles representation in generality with Texps (see: [Texp](texp.md)), akin to
S-expressions in the Lisp family of languages.
