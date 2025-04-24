# Programs

Programs are computer applications that perform a task. A program can be very simple, such as a calculator, or very complicated, such as a game like Terraria. Programs are written with code, which are instructions that dictate how a program operates. Computers take very simple instructions, so we use programming languages that are easy for humans to understand.

| Key concepts in this chapter
| -
| [Code](#k-code)
| [Binary](#k-binary)
| [Programming Languages](#k-languages)
| [Abstraction](#k-abstraction)
| [Interpretation](#k-interpretation)
| [Compilation](#k-compilation)

## Code

<span id="k-code">**Code** is an umbrella term for instructions for a computer</span>. Code relies on the idea of logic and operations, similar to mathematics. It is made up of rules and keywords that dictate how a program operates. Machine code is the complicated code that computers read.

### Binary

<span id="k-binary">Machine code is written in **binary**, which is a number system with only two values--0 and 1</span>. The numbers `01001000 01100101 01101100 01101100 01101111` look like nonsense to us humans, but this is exactly what a computer reads. This reads `Hello`, by the way.

## Programming Languages

<span id="k-languages">**Programming languages** are the interface between the human developer, and the computer's binary instructions</span>. You can technically write machine code, but it's much easier to write in a programming language.

Most programming languages are designed to be simple for humans, called "high-level." High-level languages include Python, C#, and JavaScript, just to name a few. Each of these languages have their own use cases:

- Python is typically used for data processing and calculations.
- C# is used to write programs, and has a use case in game development.
- JavaScript is used to provide functionality and interactibility to websites.

That's not to say that these languages _have_ to be used to for these instances. Online games are often written in JavaScript, and Python is used for many computer applications. It's just that these languages are commonly used for those applications.

There also exists languages that are harder for humans to understand, but easier for computers. These are called "low-level" languages. This includes assembly, which is directly equivalent to machine code.

### Pseudocode

Pseudocode is example code that doesn't necessarily resemble any programming languages. For instance, say you want a program that calculates the sum of two numbers. The pseudocode for this program would look like:

```
Take number one
Take number two
Add number one and number two
```

Everyone images pseudocode differently. What's important is that it is a simplification of real code. The rest of this unit will utilize a variant of pseudocode that acts as a blend between C# and Python. Unit 1 will introduce C#, and hopefully the transition into C# is eased with this pseudocode.

## Abstraction

<span id="k-abstraction">**Abstraction** is a common word in programming that refers to generalization or simplification of something more complicated</span>. All programming languages provide a layer of abstraction over the complicated machine code, and pseudocode is a further abstraction that is extremely easy for humans to understand.

## Conversion to Machine Code

I've tried to stress the importance of the idea of computers operating on a set of difficult-to-understand instructions. Programming languages fill this gap, but what bridges machine code to languages? There's two answers, and each language opts for one of these ways.

### Interpretation

<span id="interpretation">**Interpretation** is a method of converting languages to machine code as the program runs</span>. Interpreted code is useful as a layer of abstraction. Languages like Python benefit from this abstraction. Some other examples of interpreted languages include JavaScript and PHP, which are both common in web development.

### Compilation

<span id="k-compilation">Compiled languages, on the other hand, are directly converted into machine code before running</span>. Code must go through a building (compilation) step before being able to be ran. This provides the benefit of being mostly standalone, at the cost of being unable to see what the code actually looks like.

### Both?

Some languages, like C# and Java, actually do both. They are compiled into simple languages that can be quickly interpreted. Chapter 2 will go into more detail about this.