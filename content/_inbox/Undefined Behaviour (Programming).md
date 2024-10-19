2023-02-16
#programming 

> Behaviour, upon use of a non portable or erroneous program construct or of erroneous data, for which this International Standard imposes no requirements [^1]

> Undefined behavior doesn’t just have an unpredictable result: the standard explicitly permits the program to do _anything at all_. [^1]

> C and C++ have hundreds of rules for avoiding undefined behavior. They’re mostly common sense: don’t access memory you shouldn’t, don’t let arithmetic operations overflow, don’t divide by zero, and so on. But the compiler does not enforce these rules; it has no obligation to detect even blatant violations. [^1]

> The occasional strange message or crash may be a quality issue, but inadvertent undefined behavior has also been a major cause of security flaws since the 1988 Morris Worm used a variation of the technique shown earlier to propagate from one computer to another on the early Internet. [^1]

---
# References

[^1]: [[Programming Rust, 2nd Edition]], Preface