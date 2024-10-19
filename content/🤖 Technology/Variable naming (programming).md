2023-02-21
#programming #cleanCode

#### Use Intention-Revealing Names

> The name of a variable, function, or class, should answer all the big questions. It should tell you why it exists, what it does, and how it is used. If a name requires a comment, then the name does not reveal its intent.

> The problem isn’t the simplicity of the code but the implicity of the code (to coin a phrase): the degree to which the context is not explicit in the code itself.

Variable names should be explanatory, reducing the *implicity* of the code and making its meaning explicit.

#### Avoid disinformation

> We should avoid words whose entrenched meanings vary from our intended meaning. For example, hp, aix, and sco would be poor variable names because they are the names of Unix platforms or variants.

> It’s probably better not to encode the container type into the name.

We do this all the time, so think of it as a goal to strive for.

> Beware of using names which vary in small ways

> Spelling similar concepts similarly is information. Using inconsistent spellings is disinformation.

Avoid variables having similar names, this is confusing and can cause mistakes. The exception to this is if these variables *are* closely related, in which case their similar names may give us this information.

#### Make Meaningful Distinctions

If names must be different (because a variable or class already exists with that name), then they should also mean something else. 

> Noise words are another meaningless distinction. Imagine that you have a `Product` class. If you have another called `ProductInfo` or `ProductData`, you have made the names different without making them mean anything different. `Info` and `Data` are indistinct noise words like `a, an`, and `the`.

> Noise words are redundant. The word variable should never appear in a variable name. The word table should never appear in a table name. How is NameString better than Name? Would a Name ever be a floating point number? If so, it breaks an earlier rule about disinformation. Imagine finding one class named Customer and another named CustomerObject. What should you understand as the distinction? Which one will represent the best path to a customer’s payment history?


#### Use Searchable Names

Another reason to not use single letter or numeric variables is that they become unsearchable. If a programmer wants to search a codebase for a certain topic or function, intelligible variable names become important indices to anyone new to the codebase.

The only exception to this rule should be for local variables in small functions e.g. the *i* variable in a *for* loop.

> The length of a name should correspond to the size of its scope

#### Avoid Encodings

Avoid encoding the type in a variable name, in the modern world it's largely redundant and just adds an extra layer of mental processing. There is also the risk someone will forget to change the variable name if the type is ever changed!

The author provides a begrudging exemption for Factories, so that a variable may be named `ShapeFactory`. But somehow prefers not to adorn Interface names with an `I` prefix! What a weird stance.

#### Class Names

> Classes and objects should have noun or noun phrase names like `Customer`, `WikiPage`, `Account`, and `AddressParser`. Avoid words like `Manager`, `Processor`, `Data`, or `Info` in the name of a class. A class name should not be a verb.

This whole section seems like nonsense. How is an `AddressParser` less a 'verb' than a Manager? Maybe the main point is that the head word in the former is a noun, where as the latter is lacking any noun, a manager of what? 

#### Method Names

Method names should be verbs or verb phrases. Accessors and mutators should be named for their value and prefixed with `get` or `set`.

#### Pick one name for a concept

Pick a single word for a concept, such as retrieving data and stick to it throughout the codebase. This avoids confusion between terms like `fetch`, `retrieve`, and `get`, following this rule, if you encounter these terms in a codebase you know they are distinct concepts (albeit probably similar), and you know which you need to use. likewise, it would be confusing to have multiple classes containing the terms `controller`, `manager`, and `driver` in a codebase all covering a single context.

#### Solution Domain names

It is often more appropriate to use solution domain names that problem domain names, most programmers will recognise the names of patterns or algorithms. But most will not be familiar with a specific problem domain, so lean on the common language programmers share in common to avoid developers having to Google the meaning of terms.



---
# References

[[Clean Code: A Handbook of Agile Software Craftmanship]]., Martin, C, Robert.