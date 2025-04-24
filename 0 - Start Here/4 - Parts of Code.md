# Parts of Code

This chapter seeks to define statements, expressions, and operators. The second part of this chapter, 4.1, will cover the Boolean operators, which will form the building blocks of chapter 5.

## Comments 

Comments are sections of code that do not run. Comments are used for many reasons, but the main reason is to describe what a program does. Any line that starts with a comment will be ignored. My pseudocode will utilize the hashtag `#` to write comments:

```
# This line is commented out
This line is not
```

## Statements

A **statement** is a single piece of code that individually performs an action. Statements are the pieces of code that _actually_ perform something. For example, the last chapter covered variable manipulation: the act of assigning to a variable is considered a statement.

### Declarations

Declarations are a special kind of statement that defines a new element in code. Definitions include variable definitions, function definitions (covered in chapter 6), and class definitions (covered in chapter 8).

## Expressions

**Expressions** are non-runnable segments of code that can be used inside of a statement. The common expressions required to continue are operations and literals.

Operations typically involve a left-hand (LHS) and right-hand (RHS) side. The left-hand side is the value on the left, and the right-hand side is the value on the right. Both sides of the operator are called _operands_.

## Literals

**Literals** are expressions that represent an exact value. In the previous chapter, a list of datatypes was provided and the ways they are represented in code. That representation is called a literal. Some examples of literals include:
- `true` represents a boolean literal. Booleans can either be true or false.
- `"This is a string literal!"` represents a string literal. 
- `4` represents a numerical literal for 4. All languages specify literals in their own way, however most programming languages based on C (a lower-level language) use `f` for single-precision floats, and omit a letter for integers. If a decimal is provided, omitting a letter will result in a double-precision float.
- Collections are represented differently depending on the type of collection:
  - `[1, 2, 7, 7]` square brackets specify that a collection is an array or list. Any values within these brackets (separated by commas) will be initialized as data into the collection
  - `{"key": 2, "key2": 0}` curly braces define a dictionary--a collection that "maps" data with an input and output. The input, called a key, cannot repeat.
  - `(value1, value2)` parentheses represent tuples for the languages that support them. 
- `0b10010101` specifies a binary literal for the binary 10010101.
- `0xFF` specifies a hexadecimal (base-16) literal. Our number system only goes up to 9, so the letters A-F are used for the remaining 6 values. This literal contains the integer value 255.

## Arithmetic Operators

**Arithmetic** is the process of performing calculations on numbers. Most languages have the 4 basic operations of addition, subtraction, multiplication, and divison. The symbols for each are `+`, `-`, `*`, and `/`, respectively.

Most languages follow the order of operations, which specifies that multiplication and division are given equal precedence over addition and subtraction.

```
integer My_Num1 = 3 + 4
integer My_Num2 = 14 - 7
float My_Num3 = 3.5f * 2
integer My_Num4 = 21 / 3
integer Complicated_Number = 3 * (5 + 8 - 3) / 2
```

As you can see, the variables `My_Num1` through `My_Num4` all result in 7 (or 7.0f, for `My_Num3`). The variable `Complicated_Number` performs the addition and subtraction first due to being inside parentheses, resulting in 10. Since multiplication and division are on the same level of priority, they get evaluated left to right. 3 * 10 / 2 evaluates to 15, which is the value stored inside `Complicated_Number`.

There are two additional variants of division that can be confusing for new programmers, being integer divison and modulo.

**Integer division** is a special type of division that removes the decimal point after a number, called truncation. Truncation can be thought as rounding to the nearest integer _toward_ zero. For example, we want to truncate the decimal `4.75f`. Instead of rounding to the closest whole number (5), the number rounds down to `4`. For negative numbers, the number `-3.14` will instead round up to `-3`.

There is no fixed specification for integer division among languages. For example, Python utilizes the double slash (`//`). In C-based languages, integer division is specified when the second number in the expression is an integer value. The pseudocode example will utilize the double-slash method:

```
integer My_Number = 100f // 3.5f
```

Standard division results in approximately 28.517428, but integer division will round the result will be rounded down toward 0. This results in a value of `28` being stored into `My_Number`.

**Modulo** (`%`) performs integer division, but instead of taking the quotient, it takes the whole remainder. For example, the expression `5 % 2` will begin dividing. Traditional divison results in 2.5, however modulo recognizes that there is a decimal component. The operation multiplies the fractional component by the divisor, resulting in a final value of `1`.

Modulo is extremely useful in its ability to check whether a number is cleanly divisible by a certain value. Divsibility by 2 allows you to check whether a number is odd or even, which has its uses in programming and certain calculators.

## String Operations

Strings typically only have one operation--concatenation. **Concatenation** comes from Latin and literally means "to form a sequence." Concatenation is used to combine strings together, forming a new string formed where the other two strings left off. In most languages, it is performed with the addition (`+`) operator, but this is no standard addition. The string on the right-hand side will be joined to the end of the string on the left hand side. Here is an example:

```
string Joined_String = "Hello, " + "Bob!"
```

The result of this expression becomes `"Hello, Bob!"`. String concatenation is extremely useful for allowing variables to be mixed into strings. For example, let's suppose we want to greet someone else, or maybe use another greeting. We can put both of these in their own separate variables `Name` and `Greeting`, and join the strings together! We're very excited to meet this person, so let's include an exclamation mark:

```
string Name = "Alice"
string Greeting = "Hello, "
string Final_Greeting = Greeting + Name + "!"
```

Now, `Final_Greeting` contains the text `"Hello, Alice!"`. We have now greeted Alice using nothing but code!

> **Challenge Question**: What other functionality do you think strings need?

<details>
  <summary>Answer</summary>
  Strings benefit from operations that _format_ the data inside of one. A concept introduced in chapter 6 are functions--code that is defined once and able to be called 
</details>

## Boolean Operations

**Boolean Operations** are operations that result in booleans. Booleans are explored in chapters 4.1 and 5.

The list of boolean operators can be found [in chapter 4.1](4.1%20-%20Boolean%20Operations.md).

## Collections

Collections have a special operator that I will call **indexing**. Recall that the index is the position inside of a collection. 

The indexing operator is notated by providing the identifier of the variable, and then a set of square brackets `[]`. Any value provided within the square brackets will serve as an index to the collection.

When we want to retrieve an element from an array or list, we simply reference the collection with the indexing operator. Let's retrieve the first element:

```
array My_Nums = [1, 2, 3, 3]
integer Num_1 = My_Nums[1]
```

`Num_1` holds a value of 2. Wait, what? This is the bane of every new programmer, so I will highlight this: <span class="highlight">Indices start at 0</span>.

The reasoning relies on how memory operates. Think of the index as an offset to the first location in memory of the variable: An index of zero means no offset, aka the location of the first index in memory.

Alright, let's use another example. What value will `Num_1` receive?

```
array My_Nums = [1, 2, 3, 3]
integer Num1 = My_Nums[0]
```

The answer is 1, because an index at 0 is the first element in the array.

You can also index to assign a variable into an array or list. This is done in the exact same way as assigning, just by putting it on the left-hand side of the assignment:

```
array My_Nums = [1, 2, 3, 3]
My_Nums[0] = 50
```

We have now replaced the first index in `My_Nums` to a value of 50. The full array now reads `[50, 2, 3, 3]`.

> **Strengthen Your Understanding**: Why do indices start at 0?

<details>
<summary >Answer</summary>
In memory, collections are stored as raw numbers. Suppose we have a collection stored inside of memory represented as a string of hexadecimal (base-16) bytes. The beginning and end of this supposed collection is identified by a value of 0xFF (255 in decimal):

<pre>
[<span class="lime">0xA0</span>, <span class="lightred">0xFF</span>, <span class="lightblue">0x05</span>, <span class="lightblue">0xA0</span>, <span class="lightblue">0x31</span>, <span class="lightblue">0xF1</span>, <span class="lightred">0xFF</span>]
</pre>

I have taken the liberty to color code each of the "parts" of this supposed collection. The "bookends" of the array are notated in red, so anything between these should be regarded as data. The blue is the actual data a programmer will be able to access. The green byte is special--this points to the memory address of the first blue byte.

When you provide an index, you are telling the computer, "Retrieve the element at position `0xA0` + some index." When a value of 0 is provided, that is the first location in memory.

</details>

### Retrieval from Dictionaries

The last thing this monster of a chaper will cover is reading from dictionaries. Dictionaries utilize square brackets to access values, just like arrays and lists. Unlike those types of collections, dictionaries can take in more than integers, and also don't suffer from indices starting at zero.

Since we already covered arrays and lists, this example will cover both retrieval and assignment. We have a dictionary that represents ages. Connor and Scott both had their birthdays! Since their ages are similar, let's just set their ages :

```
dictionary Ages = {"Scott": 20, "Connor": 19}
Ages["Connor"] = Ages["Scott"]
Ages["Scott"] = Ages["Scott"] + 1
```

<!--Styles-->
<style>
summary:hover {
  font-weight: bold;
  cursor: pointer;
}
.lime {
    color: rgb(60, 176, 60);
}
.lightred {
    color:rgb(176, 101, 101);
}
.lightblue {
    color: rgb(115, 115, 205)
}
.highlight {
    background-color: #ffffa0;
    color: black;
    font-weight: bold;
    padding-left: 3px;
    padding-right: 3px;
}

</style>