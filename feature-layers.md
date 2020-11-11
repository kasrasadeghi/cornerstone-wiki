| feature layers |
\----------------/
- desc: This is an overview of the set of features that comprise a developer
  ecosystem.
- created: oct 21

- features:
  - in language
    - layer 1. in compiler
  - not in language
    - layer 2. in compiler
    - layer 3. not in compiler

In Language Features
---

define "contract":
- the visible interface that one can depend on
- if any element of the contract changes, things depending on it might break

In-language features include syntax, type systems, module systems, name
resolution, and often the standard library and a runtime.  The runtime may
include semantics for concurrency e.g. lightweight threads, OS interaction, and
garbage collection. These features change the semantics and representation of
the language and are often part of the contract that the users of the language
expect, and is often outlined in the specification for a language.

in-language features (layer 1):
- syntax
- type systems
- module systems
- name resolution
- standard library
- runtime
  - concurrency
  - OS interface
  - garbage collection

Compiler-specific Features
---

Features and tools that exist outside of the language can be separated into
features still within the compiler and features of tools around it.  Features
within the compiler include error messaging, intermediate object construction,
optimizations, interfaces with meta-programming systems and build systems, debug
information, and other unspecified language behaviour.  These are often called
"compiler-dependent" or "compiler-specific" features, though in many cases there
is a reference implementation that sets conventions that many follow.

compiler-specific features (layer 2):
- error messages
- intermediate objects
- optimizations
- repl
- unspecified language behaviour
  - meta-programming interfaces
  - build system interface
  - debug information

Non-Compiler Tools
---

There are a variety of tools that surround a compiler, including linters,
editors with syntax highlighting, build systems, package managers, package
repositories, version control systems, testing systems, interactive shells, and
so much more.  These tools are often reliant in some way on the semantics of the
compiler.  For example, linters and syntax highlighting often rely on lexical
information and type information in order to diagnose issues and communicate the
concerns of the compilers back to the developer in a more efficient context.
These tools need to be integrated with parts of the compiler.  As another
example, debuggers often rely on the debug information that a specific compiler
provides.

non-compiler-tools (layer 3):
- linters
- editors
- build systems
- version control systems
- testing systems
- interactive shells
- debuggers

Features of the tools around a compiler often interact with compiler-specific
features and depend on language specification, although often they are language
agnostic.  Recently, some languages have adopted a Language Server Protocol to
interface between the compiler and out-of-compiler tooling, providing things
like semantic navigation (i.e. "go-to-definition") and references.
