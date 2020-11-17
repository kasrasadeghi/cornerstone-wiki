| The Deeper Access Problem |
\---------------------------/
- created: oct 23

This is one problem that we face when using passes as the foundation for
meta-programming.

Description
-----------

The tricky part with this comes where the library may not know something is
wrong or may have to reduplicate computation to prevent errors that already
exist within the rest of the compiler.  Libraries have to be able to run a set
of passes on a piece of code within an environment in order to query certain
information.  For example, a library has to check whether two things are the
same type, but type inference does not happen until later in the compiler.  It
needs to be able to run all of the passes until type inference and then use the
type environment with its members translated back to how they appear in the
current pass.

Solutions
---------

Here are some solutions to this problem:
- run those passes for the compiler and cache the results (lazy approach)
  - k: might be hard to reason about

TODO
- eager:
  - run composable piece
- lazy:
  - register a hook that catches error messages before they propagate back up tow
  the user
  - k: very flexible, but also very spaghetti
