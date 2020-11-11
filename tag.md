


```
; parenthetical representation
(+ (call foo (args 5 6)) (+ 10 11))

; tabbed representation
+
  call
    foo
    args
      5
      6
  +
    10
    11

; with annotations

; we know that '+' is a binary operator and requires two children that are
; expressions
+
  ; we know this expression is a call
  ; we don't need to parse until a matched parenthesis to know that the current
  ; Texp is a "call" and we expression the name of a function and some arguments
  call
    foo
    ; because functions in general may have an arbitrary number of arguments, we
    ; must group them under an "args"
    args
      5
      6
  ; we know this expression is a plus
  +
    10
    11
```
