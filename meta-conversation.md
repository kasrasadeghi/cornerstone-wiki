| Meta Conversation |
\-------------------/

This document discusses the complexity of meta-programming and how that is
affected by the complexity of the non-meta-programming aspects of a language.

# Programming is Discussion

We can see programming as a conversation between the programmer and the
programming environment, and this analogy serves as a frame for the rest of this
document.  Conversations are inherently bidirectional.  In the context of
programming, a programmer writes code and gives it to the compiler, and the
compiler tries to compile it and gives results back.  These results come in many
forms. Some examples include error messages during compilation, a program that
can be debugged, or an optimized program that can be profiled for release.  As
opposed to investigating the flexibility and expressiveness of the source code's
language given to the compiler, this project investigates how the compiler and
the rest of the tooling ecosystem may communicate back to the developer.  The
Cornerstone Project focuses on this direction of communication.

Compilers are the primitive for communication with the machine as they are the
program that gives semantics to language.  They also serve as a kind of
primitive for all of the rest of the tools in the programming ecosystem.  Debug
information, syntax highlighting, type information, all come from either the
compiler or reimplemented sections of the compiler.

# Language Complexity

Given the analogy of conversations, we may think of natural languages and
discussions between humans.  When people discuss the language that they are
speaking, they speak of "grammar".  This is a _meta-discussion_. As English
speakers, we may speak of "English grammar".  When comparing a natural language
to others, one may notice that some languages do not contain features that
others do, such as word order; gendered verbs, adjectives, or nouns; agreement;
or case.  Languages that have less restrictions have a simpler grammar, and thus
it is easier to have meta-discussions.  When the complexity of the language
grows, so too does the complexity of meta-discussions.

see:
- [English vs Farsi: Anecdotes of Natural Languages](english-vs-farsi.md)

In the context of programming, when meta-discussions about a program are too
complicated, the compiler and the environment cannot provide helpful errors.  It
may require too many assumptions about the program, too much computation, or may
be too difficult to decide between several ambiguous cases that exist within the
current problematic context.

The Cornerstone Compiler Framework focuses on giving power to the user by giving
meta-programming users the same tools that compiler developers have.
Meta-programs are exceedingly difficult to verify or analyze.  So Cornerstone
makes a lot of simplifying assumptions about the languages one might build using
a compiler framework, many of which stem from the representation of those
languages.

see:
- [Texp](texp.md)
  about: the representation and structure of programs in Cornerstone
- [Backbone](backbone.md)
  about: the example language implemented using Cornerstone, with simple design
  at its forefront

# Design a Modular Compiler

TODO modular compiler from compiler-to-programmer direction of conversation
