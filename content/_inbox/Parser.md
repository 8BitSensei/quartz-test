2023-03-15
#CompSci 

Usually composed of a lexer/scanner/tokenizer and the proper parser. 

Some parsers do not depend on a lexer, these are called scannerless parsers.

The lexer scans the input and produces the matching tokens, the parser scans the tokens and produces the parsing result. The parser will typically combine the tokens produced by the lexer and group them. 

The definitions used by lexers or parsers are called *rules* or *productions*. 

> A lexer rule will specify that a sequence of digits correspond to a token of type _NUM_, while a parser rule will specify that a sequence of tokens of type _NUM, PLUS, NUM_ corresponds to an expression.



---
# References

https://tomassetti.me/parsing-in-csharp/

https://tomassetti.me/guide-parsing-algorithms-terminology/