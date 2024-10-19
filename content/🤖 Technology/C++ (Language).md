2023-02-16
#technology #programming 

## Introduction
#### History

C++ is a descendant of [[C (Language)]] debuting in 1972.

The first compiler was Cfront, which would compile C++ to C source files which were then compiled to machine code.  This is long gone and C++ now compiles directly to machine code.

C++ 2.0 debuted in 1989, the language was then standardised by ISO in 1998. This was colloquially known as '*C++98*', the convention continues and the year of debut is used to name the version of C++ now.

Huge changes occurred in C++11, which begins the '*Modern C++ era*'. Changes now occur every three years, meaning the C++20 is the latest version and C++23 will be the next.

#### Standard Library

Every release of C++ includes what is called '*Standard Library*'. This is often called '*STL*', meaning '*Standard Template Library*', for its heavy use of a C++ language feature called templates. The library is also standardised by ISO.

The STL is similar to .NET's Framework Class Library or CoreFX. The architectural approach for the C++ language is to have powerful, low-level language features so more can be implemented in libraries instead of directly included in the language (I hate this). 

| STL | C++ | C# |
| --- | --- | --- |
| Language Support | `numeric_limits::max` | `int.MaxValue` |
| Concepts | `default_initializable` | `where T : new()` |
| Diagnostics | `exception` | `System.Exception` |
| Utilities | `tuple<int, float>` | `(int, float)` |
| Strings | `string` | `System.String` |
| Containers | `vector` | `List` |
| Iterators | `begin()` | `GetEnumerator()` |
| Ranges | `views::filter` | `Enumerable.Where` |
| Algorithms | `transform` | `Enumerable.Select` |
| Numerics | `accumulate` | `Enumerable.Aggregate` |
| Localisation | `toupper` | `Char.ToUpper` |
| I/O | `fstream` | `FileStream` |
| File system | `copy` | `File.Copy` |
| Regular expressions | `regex` | `Regex` |
| Atomic operations | `atomic++` | `Interlocked.Increment` |
| Threading | `thread` | `Thread` |

Some game programming environments do not use the STL, or at least minimise its use. EA has implemented their own version called EASTL. Unreal has many built-in similar types (`FString` vs. `string`) and functions (`MakeUnique` vs. `make_unique`). They do this to efficiently reimplement what would be language features in many other languages for the game environment.

#### Tools

The main tool is of course the compiler. There are several options these days, which are:

| Compiler | Cost | Open Source | Platforms |
| --- | --- | --- | --- |
| Microsoft Visual Studio | Free and Paid | No | Windows |
| GCC (GNU Compiler Collection) | Free | Yes | Windows, macOS, Linux |
| Clang | Free | Yes | Windows, macOS, Linux |
| Intel C++ | Free | No | Windows, macOS, Linux |

There are also many IDEs available with the usual combination of features: a text editor, compiler execution, interactive debugger, etc. Here are some popular options:

| IDE | Cost | Open Source | Platforms |
| --- | --- | --- | --- |
| Microsoft Visual Studio | Free and Paid | No | Windows |
| Apple Xcode | Free | No | macOS |
| JetBrains CLion | Paid | No | Windows, macOS, Linux |
| Microsoft Visual Studio Code | Free | Yes | Windows, macOS, Linux |

Many static analysers, known as 'linters', and dynamic analysers are available. The [Clang sanitizers suite](https://clang.llvm.org/docs/index.html) is free, open source, and has [Unreal support](https://docs.unrealengine.com/4.27/en-US/ProductionPipelines/BuildTools/UnrealBuildTool/BuildConfiguration/). Commercial tools such as [Coverity SAST](https://www.synopsys.com/software-integrity/security-testing/static-analysis-sast.html) are also available. [Clang format](https://clang.llvm.org/docs/ClangFormat.html) and many IDEs can enforce style guides and automatically reformat code.

#### Documentation
## Primitive Types and Literals

The C++ standard is available for [purchase](https://www.iso.org/standard/68564.html), but almost no C++ developers actually buy it. A [draft version](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/n4659.pdf) is available for free and will be nearly identical, but it is extremely long and technical so it is also only a reference of last resort. Instead of the standard itself, most developers read reference sites such as [cppreference.com](https://en.cppreference.com/w/) just as they would read Microsoft Docs (a.k.a. MSDN) for C# reference.

#### Types

Beginning with integers, they can be defined with 6 parts which can be used together and permeated.

`signed`: Signed types are positive and negative values, defaults to `long`. This is equivalent to `int` on its own.
`unsigned`: Unsigned types store only positive values, defaults to `long`.

`short`:  Short types store only 16-bits of data
`long`: Long types store 32-bits of data
`long long`: Long Long types store 64-bits of value

There is also a 32-bit or 64-bit unsigned integer `size_t` depending on the CPU being compiled for.

There are for 8-bit types.

`bool`:  Equivalent to C# `bool`
`char`:  Equivalent to C# `sbyte`
`signed char`:  Equivalent to C# `sbyte`
`unsigned char`:  Equivalent to C# `byte`

There are types named with `char` are due to their original usage for characters in ASCII strings.

We also have `float` and `double` as well as a high precision `long double`. There is no `decimal` type in C++ but some libraries provide similar functionality.

Given the uncertainty of size across CPU and OS, it's best practice to avoid many of these types and use specific sizes.  

#### Literals

Constants refer to fixed values that the program may not alter and they are called **literals.** 

**Bool Literals**:
The type `bool` can only store the values `0` or `1`, it only has two literals `true` for `1` and `flase` for `0`.

**Integer Literals**
An integer literal can be a [[Jargon dump#Decimal| decimal]], [[Jargon dump#Octal| octal]], or [[Jargon dump#Hexadecimal| hexadecimal]] constant. In C++ we use a prefix to specify the base (or [[Jargon dump#Radix|xradix]]) of an integer.

`0x...` or `0X...`: Hexadecimal
`0...`: Octal
`0b...` or `0B...`: Binary
No prefix for decimal

An integer literal can also have a suffix that is a combination of `U` or `L`, for [[Jargon dump#Unsigned Int|unsigned]], [[Jargon dump#Long Int|long]], and [[Jargon dump#Long Long Int|long long]], respectively. Some examples:

```
212         // Legal
215u        // Legal
0xFeeL      // Legal
078         // Illegal: 8 is not an octal digit
032UU       // Illegal: cannot repeat a suffix
85         // decimal
0213       // octal
0x4b       // hexadecimal
30         // int
30u        // unsigned int
30l        // long
30ul       // unsigned long
```

**Floating point Literals**:
Floating point values default to a `double` but there are prefixes and suffixes to modify a values radix and length.

`...f`: Declares the value a float
`...e`: Declares the value a double

`...p`: Declares the a hexadecimal

**Character literals**:

*Something, something, something....*


## Variables and Initialisation
#### Declaration

Basic declaration works the same as in C# with a `type` and then the `variable name`, with a `;` representing the end of the statement.

``` C++
int x;
```

We can also declare multiple variables in-line.

``` C++
int x, y, z;
```

#### Initialisation

The most basic way to initialise a variable is the recognisable standard.

``` C++
int x = y;
```

There are also some other ways to initialise in C++ that we don't see in C#, for example default Initialisation.

``` C++
int x{}; // x is filled with zeroes, so x == 0
int x{123};
int x(123);
```

These examples can all be combined.

``` C++
int a, b = 123, c{}, d{456}, e(789);
```

#### Type Deduction

Like in C# where we can simply type `var` instead of a type to save time, in C++ we can use `auto`, so that we can do the following with the same results as above.

``` C++
auto x = 123;
auto x{123};
auto x(123);
```

We can only use deduction when there is an initialiser, so the following isn't allowed.

``` C++
auto x;
auto x{};
```

Remember that `x` is just as strongly-typed as if `int` were explicitly specified. 

Another alternative approach but not used that often is the `decltype` operator. This resolves to the type of its parameter.

``` C++
int x;
decltype(x) y = 123; // y is an int
```

#### Identifiers

The rules for naming C++ identifiers are similar to the rules for C#, they must begin with a letter, underscore, or any non-digit Unicode character. After that, they contain any Unicode character except some strange ones.

There are some additional restrictions.

| Restriction | Example | Where |
| --- | --- | --- |
| All keywords | `int for` | All code |
| `operator` then an operator symbol | `operator+` | All code |
| `~` then a class name | `~MyClass` | All code |
| Any name beginning with double underscores | `int __x` | All code except the Standard Library |
| Any name beginning with an underscore then a capital letter | `int _X` | All code except the Standard Library |
| Any name beginning with an underscore | `int _x` | All code in the global namespace except the Standard Library |

There is no equivalent to C#’s “verbatim identifiers” (e.g. `int @for`) to work around the keyword restriction.

#### Pointers

C++ use pointers, we generally don't use pointers in C# unless 'unsafe' features are enabled. The syntax is so.

``` C++
int* x;
int * x;
int *x;
```

The placement of the asterisks is flexible, but when declaring multiple variables in line it works differently.

``` C++
int* x, y, z; // Only x is a pointer
int *x, *y, *z; // All are pointers
int *x, y, *z; // x and z are pointers but y is not
```


#### References

C++ has two kinds of references, 'lvalue' and 'rvalue'. For now just remember that that lvalues are like non-nullable pointers. this means we *must* initialise them when they are declared.

You can set an lvalue reference with `&` and an rvalue reference with `&&`, so you can do the following. 

``` C++
int x = 123;
int& y = x;
 
int&& z = 456;
```

## Functions

####  Declaration and Definition

We can discuss functions in C++ by splitting it into two parts. First the *function declaration* which states its signature without stating how it works.

``` C++ 
int Add(int a, int b);
```

Or you can write the *function definition* which contains the signature and the body.

``` C++
int Add(int a, int b)
{
    return a + b;
}
```

The reason C+ has a declaration and a definition is to do with how it's compiled. But for now just know that C++ is compiled from top to bottom in a source file. A function definition or declaration makes it available to be referenced by code further down in the file.

``` C++ 
int Add(int a, int b);
 
int three = Add(2, 1);
 
int Add(int a, int b)
{
    return a + b;
}
```

In the above it doesn't matter that we're using the function before it's defined, the compiler trusts that we'll add it eventually. If we don't, then we'll get an error.

A function signature in C++ can declare parameters without names. We might need to use this in certain situations where a specific signature is needed but the parameter isn't needed in the body.

``` C++
int Add(int a, int)
{
    return a + 1;
}
```

#### Automatic Return Types

C++ variables can be declared with an `auto` type, similar to `var` in C#. We can use this as a return type on functions. This means the return type is figured out at compile time.

``` C++
auto Add(int a, int b)
{
    return a + b;
}
```

#### Default Arguments

As in C# default arguments are allowed as long as there aren't any non-defaulted arguments after the first one. In C++ though if your declaration and definition are split and the function signature has the parameter in both, the default arguments from the declaration are used.

``` C++
// Function declaration states the default argument values
void SpawnPlayer(Vector3 position, float speed=0.0f);
 
// Function definition omits them
void SpawnPlayer(Vector3 position, float speed)
{
    // ...
}
```

#### Overloading

As in C#, functions may be overloaded in the sense that more than one function may have the same name. When the function is called, the compiler figures out which of these identically-named functions should actually be called.

``` C++
// Get the player's score given their ID
int GetPlayerScore(int playerId);
 
// Get the local player's score
int GetPlayerScore();
 
// Get the score of the player at a given position
int GetPlayerScore(Vector3 position);
```

#### Ref, Out and In Arguments

In C#, arguments can be declared with the `ref`, `in`, and `out` keywords. Each of these change the argument to be a pointer to the passed value. In C++, these keywords don’t exist. Instead, we use some conventions.

**Alternative to `ref`** - the parameter passed *may* be modified by the method.

``` C++ 
// Use an lvalue reference, which is like a non-nullable pointer
void MovePlayer(Player& player, Vector3 offset)
{
    player.position += offset;
}
```

**Alternative to `in`** - the parameter passed *cannot* be modified by the method.

``` C++
// Use a constant lvalue reference
// `const` means it can't be changed
void PrintPlayerName(const Player& player)
{
    DebugLog(player.name);
}
```

**Alternative to `out`** - the parameter passed *must* be modified by the method.

``` C++
// Just use return values
ReallyBigMatrix ComputeMatrix()
{
    ReallyBigMatrix matrix;
    // ...math goes here...
    return matrix
}

// Use lvalue reference arguments
void ComputeMatrix(ReallyBigMatrix& mat1, ReallyBigMatrix& mat2)
{
    mat1 = /* math for mat1 */;
    mat2 = /* math for mat2 */;
}

// Pack the outputs into a return value
tuple<ReallyBigMatrix, ReallyBigMatrix> ComputeMatrix()
{
    return make_tuple(/* math for mat1 */, /* math for mat2 */);
}
```

#### Static Variables

Local variables within functions may be declared `static`. Similar to `static` fields of classes and structs in C#, this means that the variable has only one instance. A `static` C++ local variable has only one instance across all calls to the function.

``` C++
int GetNextId()
{
    static int id = 0;
    id++;
    return id;
}
 
GetNextId(); // 1
GetNextId(); // 2
GetNextId(); // 3
```

#### Constexpr

Finally for today, functions may be marked with `constexpr`. This means that the function can be evaluated at compile time.

``` C++
constexpr int GetSquareOfSumUpTo(int n)
{
    int sum = 0;
    for (int i = 0; i < n; ++i)
    {
        sum += i;
    }
    return sum * sum;
}
```

This function can then be evaluated at compile time in order to generate a constant.

``` C++
DebugLog(GetSquareOfSumUpTo(5000));
 
// equivalent to...
 
DebugLog(1020530960);
```

The function can also be evaluated at runtime, such as when its parameters are dependent on runtime values.

``` C++
int n = file.ReadInt();
DebugLog(GetSquareOfSumUpTo(n));
```

This means that normal C++ can be reused for both compile time and runtime work. Though, some features like `static` local variables and `goto` aren’t allowed even in C++20.

## Build Model

#### Compiling and Linking

With C# we compile all our source files (`.cs`) into an assembly such as `.exe` or  a library `.dll`. With C++ we compile or *translation units* (id est source code files with `.cpp`, `.cxx`, `.cc`, `.C`, or `.c++` extensions) into object files (`.obj` or `.o`) and then link them together into an executable (`.exe`), *static library* (`.lib` or `.a`), or *dynamic library* (`.dll` or `.so`).

So, for example `.cpp` -> **Compiler** ->  `.obj` -> **Linker** -> `.exe`.

First, **what is an object file?** This is known as an “intermediate” file since it’s neither the source code nor an output file like an executable. The C++ language standard doesn’t say anything about what the format of this file is. In practice, it’s a binary file that is specific to a particular version of a particular compiler configured with particular settings. If the compiler, version, or settings change, all the code needs to be rebuilt.

Second, **what is the difference between a static library and a dynamic library?** A dynamic library is very similar to a dynamic library in C#. It’s a library of machine code, just like an executable. However, it can be loaded and unloaded by an executable or other dynamic library at runtime. A static library, on the other hand, can only be loaded at *compile time* and can never be unloaded. In this way, it functions more like just another object file.

Because static libraries are available at build time, the linker builds them directly into the resulting executable. This means there’s no need to distribute a separate dynamic library file to end users, no need to open it from the file system separately, and no possibily of overriding its location.

Critically for performance, all calls into functions in the static library are just normal function calls. This means there’s no indirection through a pointer that is set at runtime when a dynamic library is loaded. It also means that the linker can perform “link time optimizations” such as inlining these functions.

The main downsides stem from needing the static libraries to be present at compile time. This makes them unsuitable for tasks such as loading user-created plugins. Perhaps most importantly for large projects, they must be linked in every build even if just one small source file was changed. Link times grow proportionally and can hinder rapid iteration. As a result, sometimes dynamic libraries will be used in development builds and static libraries will be used in release builds.

#### Header Files and the Preprocessor

In C# we add `using` directives to reference code in other files.  C++ has a similar 'module' system added in C++20 which can be covered later, traditionally header files are used.

Header files (`.h`, `.hpp`, `.hxx`, `.hh`, `.H`, `.h++` or no extension) are by far the most common way for code in one file to reference code in another file. These are *simply C++ source code files that are intended to be copy-and-pasted into another C++ source code file.* This copy-and-paste operation is performed by the preprocessor.

C++ uses a preprocessor directive called `#include` to copy and paste a header file's contents another file (`.h`) or a translation unit (`.cpp`).

``` C++
// math.h
int Add(int a, int b);
 
 
// math.cpp
#include "math.h"
int Add(int a, int b)
{
    return a + b;
}
```

In the above the preprocessor will search the same directory as `math.cpp` for `math.h`. If it finds it, it reads its contents and replace the `#include` directive with them. Otherwise, it searches the configured "include paths" and the STL, if `math.h` isn't found the compiler produces an error.

Your header file can have a function declaration (remember this is just the signature) of a function which is defined in another `.cpp` file. The Linker will see that the function is an unsatisfied dependency, so if it finds the definition in another `.cpp` it will use that.

We can also use an include like this, it will just search the STL and other header files provided by the compiler.

``` C++
#include <math.h>
```

We can also specify paths.

``` C++
#include "utils/math.h"
#include <nlohmann/json.hpp>
```

#### ODR and Include Guards

ODR stands for what C++ calls "one definition rule". This says that there may be **only one definition of something in a translation unit**. This includes variables and functions, which presents us some problems as our codebase grows. 

To work around this, we add what’s called an “include guard” to our header files. There are two basic forms this can take, but both make use of the preprocessor.

``` C++
#if (!defined MATH_H)
#define MATH_H
 
int Add(int a, int b);
float PI = 3.14f;
 
#endif
```

This makes use of the `#if`, `#define`, and `#endif` directives, which are similar to their C# counterparts. The only real difference in this case is the use of `!defined MATH_H` in C++ instead of just `!MATH_H` in C#. One variant of this is to make use of a C++-only `#ifndef MATH_H` as a sort of shorthand for `#if (!defined MATH_H)`.

``` C++
#ifndef MATH_H
#define MATH_H
 
int Add(int a, int b);
float PI = 3.14f;
 
#endif
```

In either case, we choose a naming convention and apply our file name to it to generate a unique identifier for the file. To avoid needing to come up with unique names, all common compilers offer the non-standard `#pragma once` directive.

``` C++
#pragma once
 
int Add(int a, int b);
float PI = 3.14f;
```

#### Inline

The above will still cause a linker error, the reason for the linker error is that, by default, we can’t have duplicate definitions of `PI` at link time either. If we want to do that, we need to add the `inline` keyword to `PI` to tell the compiler that multiple definitions should be allowed.

It may seem strange that `inline` is a keyword applied to variables. The historical reason for this is that it was originally a hint to the compiler that it should inline _functions_ but, like the `register` keyword, this was non-binding and virtually always ignored. It’s come to mean “multiple definitions are allowed” instead, so it can now be applied to both variables and functions.

This is often avoided though because any change to the function will require recompiling all of the translation units that include it, directly or indirectly, which may take quite a while in a big codebase.

#### Linkage

Linkage allows a `.cpp` file to reference an external variable from another `.cpp` (not defined in a `.h` file, so we're not using the `#include` keyword here) that has *external linkage*.

We can do this using the `extern` keyword.

``` C++
// user.cpp
extern float SQRT2; // SQRT2 is defined in math.cpp
 
float GetDiagonalOfSquare(float widthOrHeight)
{
    return SQRT2 * widthOrHeight;
}
```

When `user.cpp` is compiled it notes in the `user.obj` that `SQRT2` is an unsatisfied dependency, then when  it compiles `math.cpp` it notes that `SQRT2` is available for linking. Later on (in the translation process) it sees the note in the `user.obj` stating `SQRT2` needs to be satisfied and goes to find the definition, which it finds noted as available in `math.obj` and links them. 

Note that external linkage is the default, so we don't need to apply the `extern` keyword to the definition in `math.cpp`. To the prevent this behaviour add the `static` keyword to the definition of `SQRT2`, this changes the linkage to internal only.

Both `extern` and `static` can be used with functions.

## Control Flow

#### If and Else
Just like in C#

``` C++
if (someBool)
{
    // ... execute this if someBool is true
}
else
{
    // ... execute this if someBool is false
}
```

An extra feature allows us to initialise a variable scoped to the if statement and check a condition, it's similar to the first statement in a `for` loop, so for example.

``` C++
if (ResultCode code = DoSomethingThatCouldFail(); code == FAILURE)
{
    // ... execute this if DoSomethingThatCouldFail returned FAILURE
}
```

#### Goto and Labels
C++ like C# has a `goto` statement which can skip the code forward to a labeled section.

``` C++
void DoLotsOfThingsThatMightFail()
{
    if (!DoThingA())
    {
        goto handleFailure;
    }
    if (!DoThingB())
    {
        goto handleFailure;
    }
    if (!DoThingC())
    {
        goto handleFailure;
    }
 
    handleFailure:
        DebugLog("Critical operation failed. Aborting program.");
        exit(1);
}
```

One thing to note is you *can't* skip variable Initialisations but you *can* skip their definition.

``` C++
void Bad()
{
    goto myLabel;
    int x = 1; // Un-skippable initialization
    myLabel:
    DebugLog(x);
}
 
void Ok()
{
    goto myLabel;
    int x; // No initialization. Can be skipped.
    myLabel:
    DebugLog(x); // Using uninitialized variable
}
```

#### Switch
Switch cases work similarly to C#

``` C++
switch (someVal)
{
    case 1:
        DebugLog("someVal is one");
        break;
    case 2:
        DebugLog("someVal is two");
        break;
    case 3:
        DebugLog("someVal is three");
        break;
    default:
        DebugLog("Unhandled value");
        break;
}
```

There are a few differences to note, if the case *is not empty* you can emit the `break` and it will fall through to the next case. An important point is that if you want to declare variables you have to use curly braces.

``` C++
switch (someVal)
{
    case 1:
    {
        int points = CalculatePoints();
        DebugLog(points);
        break;
    }
    case 2:
        DebugLog("someVal is two");
        break;
    case 3:
        DebugLog("someVal is three");
        break;
}
```

Unlike C#, a `switch` **can only be used on integer and enumeration types**. An chain of `if` and `else` is needed to handle anything else.


#### Ternary
The ternary operator is similar to C# version.

``` C++
int damage = hasQuadDamage ? weapon.Damage * 4 : weapon.Damage;
```

which is equivalent to

``` C++
int damage;
if (hasQuadDamage)
    damage = weapon.Damage * 4;
else
    damage = weapon.Damage;
```

In C++ we have more freedom with what we put into the `?` and `:`, for example we can call methods or throw exceptions.

#### While, Do-While, Break, and Continue
`While` and `do-while` are essentially the same as in C#

``` C++
while (NotAtTarget())
{
    MoveTowardTarget();
}
 
do
{
    MoveTowardTarget()
} while (NotAtTarget());
```

break and continue also work in the same way

``` C++
int index = 0;
int winnerIndex = -1;
while (index < numPlayers)
{
    // Dead players can't be the winner
    // Skip the rest of the loop body by using `continue`
    if (GetPlayer(index).Health <= 0)
    {
        index++;
        continue;
    }
 
    // Found the winner if they have at least 100 points
    // No need to keep searching, so use `break` to end the loop
    if (GetPlayer(index).Points >= 100)
    {
        winnerIndex = index;
        break;
    }
}
if (winnerIndex < 0)
{
    DebugLog("no winner yet");
}
else
{
    DebugLog("Player", index, "won");
}
```

#### For
The regular three-part `for` loop is basically the same

``` C++
for (int i = 0; i < numBullets; ++i)
{
    SpawnBullet();
}
```

C++ has a variant `for` loop which takes the place of C#s `foreach`. It's called the *range-based for loop* and it's denoted by a colon.

``` C++
int totalScore = 0;
for (int score : scores)
{
    totalScore += score;
}
```

#### Return
The typical version is just like in C#

``` C++
int CalculateScore(int numKills, int numDeaths)
{
    return numKills*10 - numDeaths*2;
}
```

There's also a return type which allows us to pass parameters to the constructor of the return type

``` C++
CircleStats GetCircleInfo(float radius)
{
    return { 2*PI*radius, PI*radius*radius };
}
```

## Pointers, Arrays, and Strings

#### Pointers
The basic syntax for pointers in C++ is `<type>* <name>;` so `int* p;` for example. A pointer *points* to a place in memory, an integer-pointer, or float-pointer are types in their own write, so we can't just set a pointer to any other type, we can't do `p = 123;`, if we want set it we need to get the memory location of the value with the `&` operator. So `p = &x;`, now this will reference the same place in memory as `x`. Notice that we don't use the `*` symbol when we're setting the value, `p` is already a pointer type, we don't have to continue using the asterisk after  it's been defined. But, if we want to get the value of a pointer we use the `*` symbol with it, so `*p == 123` would evaluate to true. Note that this is *not the same operator as the one we used when we defined `p`*, this is now called a *dereferenced pointer*, and will give us the value of the memory space it points to.

``` C++
int x = 123;
 
// Declare a pointer type: int* is a "pointer to an int"
// Get the address of x with &x
int* p = &x;
 
// Dereference the pointer to get its value
DebugLog(*p); // 123
 
// Dereference and assign the pointer to set its value
*p = 456;
DebugLog(x); // 456
 
// x->y is a convenient shorthand for (*x).y
Player* p = &localPlayer;
p->Health = 100;
```

We can also (and hopefully I will never have to use this) have a *double-pointer*, which is a pointer which points to the memory location of the first pointer.

``` C++
 int var = 789;

 // pointer for var

 int *ptr2;

 // double pointer for ptr2

 int **ptr1;

 // storing address of var in ptr2

 ptr2 = &var;

 // Storing address of ptr2 in ptr1

 ptr1 = &ptr2;
```

#### Arrays
Unlike in C#, arrays are not an object that’s “managed” and subject to garbage collection. They are instead simply a fixed-size contiguous allocation of the same type of data.

``` C++
// Declare an array of 3 int elements
// The elements of the array are uninitialized
int a[3];
 
// Initialize the first element of the array by writing to it
a[0] = 123;
 
// Read the first element of the array
DebugLog(a[0]); // 123
```

When we create an array variable, it’s just like we individually created its elements via variables. This means that there is no overhead for an array. It is literally just its elements. **It doesn’t even have an integer keeping track of its length like the `Length` field in C#.**

There is also no bounds-checking on indexes into the array, just like indexing into a pointer in C# or C++. It’s very important to be careful not to read beyond the beginning or end of the array as there’s usually no way to know what data will be read or overwritten.

The lines blur even more because we can implicitly convert arrays into pointers

``` C++
int a[3];
a[0] = 123;
 
// Implicitly convert the int[3] array to an int*
// We get a pointer to the first element
int* p = a;
DebugLog(*p); // 123
 
// Indexing into pointers works just like in C#
DebugLog(p[0]); // 123
```

The opposite does not work though: we can’t write `int b[3] = p`.

#### Pointers to Arrays and Arrays of Pointers

#### Strings
In C# we have managed `System.String` objects that are garbage-collected. In C++, we essentially have null-terminated arrays of characters.

``` C++
// The string literal "hello" has type const char[6]
// Its contents are the characters 'h', 'e', 'l', 'l', 'o', 0
const char hello[] = "hello";
 
// Like any other array, it's implicitly converted a pointer
const char* p = hello;
for (int i = 0; i < 6; ++i)
{
    DebugLog(p[i]); // h, e, l, l, o, <NUL>
}
```

#### Pointer Arithmetic


#### Function Pointers
tl;dr you can have a pointer to a function

---
# References
