| Passes > Macros |
\-----------------/
- created: oct 23

Ordering is nice
----------------

Passes provide one key benefit as the foundation for meta-programming: they are
ordered.  Ordering allows us to impose structure on the data structures between
and within passes.  Ordering allows for the semantics of a macro to be
unambiguous and clear.  Ordering allows for the clear propagation of error
messages and compiler information, and for the clear assessment of information
that will be available before a pass and the information provided by a specific
pass to the passes down the line.

First class, high quality libraries for DSLs
--------------------------------------------

Passes are also used _by the compiler_.  They already need to be written.
Having compiler writers and library writers use the same tools will allow for
high quality libraries that provide the exact same kinds of error messages and
ergonomics that the features within a language already have.  For example, error
messages for really important functions within a library can be specialized when
used in a certain way, because the library implements a pass that comes _before_
whatever part of the compiler generates that error message.

see:
- ["int" is in the Swift Standard Library](swift-int.md)
  about: swift's primitive integer type is actually a struct in the swift
  standard library

The Tricky Parts
----------------

There are some tricky parts that come with passes as meta-programming, but they
come as problems only because it becomes possible to even _have_ decent error
messages.  There are two main problems that come with interacting with the rest
of the compiler as a pass: accessing deeper computations and translating names.

Given a library that has a pass that needs to prevent some misleading error
message from deeper within the compiler and specialize that error case.  The
library might need to access or duplicate the computation that is only done
later on in compilation.  This is the Deeper Access problem.

This is discussed further below:

see:
- [Accessing Deeper Computation](deeper-access.md)
  about: the deeper access problem
