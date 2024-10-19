2023-04-28
#CompSci #syntax 

Metasyntax used to make a formal description of a formal language, usually a programming language. It is an extension of the basic Backus-Naur form notation.

Language to describe languages.

Developed by [[Niklaus Wirth]] incorporating aspects of his own [[Wirth syntax notation]]. The extension was defined to overcome some of the limitations in the base format, such as being able to easily define repetitions, which was possible in BNF, but cumbersome. 

EBNF consists of [[Terminal & Non-Terminal symbols#Terminal Symbol|terminal symbols]] and production rules which allow us to combine terminal symbols. It defines production rules where sequences of symbols (terminal or non-terminal) are assigned to a non-terminal symbol.

Functionally, terminals are our smallest element in a grammar, they are the atom upon which complex structures are built. In a grammatical context, they are termed tokens.

```
digit excluding zero = "1" | "2" | "3"
digit = "0" | digit excluding zero 
```

Here `digit` may be one of the terminal symbols 0, 1, 2, or 3, thus, it is a non-terminal symbol. Note how `digit excluding zero` is defined only with terminal symbols, but `digit` uses terminal and non-terminal symbols.




---
# References

https://en.wikipedia.org/wiki/Extended_Backus%E2%80%93Naur_form

https://tomassetti.me/ebnf/

