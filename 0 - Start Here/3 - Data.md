# Data

A common feature in all programming languages is the ability to read and write information stored inside memory. We call this information "data," and data can take the form of many different types. When data is stored in a program, it is stored in something called a variable.

| Key concepts in this chapter
| -
| [Types](#k-datatypes)
| [Binary (again)](#k-binary)
| [Common Datatypes](#k-bool)
| [Variables](#k-variable)

## Types

<span id="k-datatypes">**Datatypes** are classifications given to data based on what the data will be used for</span>. Not all languages are strict about what type something is, but most are. This strictness is to avoid strange results surrounding the data. For example, what does subtracting the number 1 from the text "Hello" mean? To a human, that's absolute nonsense, but a computer will let that happen.

### Binary

Touched on in the previous chapter was binary. <span id="k-binary">As a refresher, **binary** is a number system where there are 2 values per digit--called a bit (base-2)</span>. Humans typically use decimal (base-10) utilizing the digits 0-9. Computers use binary for a few reasons, but the main reason is due to logic.

Datatypes are an abstraction of this binary to the programmer. A programmer does not need to know what the machine reads, but as humans we need a distinction so we don't perform erroneous operations on data.

Datatypes try to fit within multiples of 8 bits, called a byte. A byte can represent 256 unique decimal values. 

> **Challenge Question**: Why would binary be easier for computers?

<details>
<summary>Answer</summary>
Binary is easier for computers due to stability. When a circuit only has 2 possible values (low or high voltage), there is no nuance. If a circuit has a low amount of voltage, then it's safe to assume the value is a 0. If the circuit has some non-low amount, the value is probably a 1.

Let's introduce a third value. Instead of detecting (almost) no power vs. high power, we also have to detect "medium" power. Where does the threshold lie? Each circuit will have its own variation in voltage, so a large fluctuation may make a value bounce between 0 and 1, or 1 and 2.

This issue is exasperated for each additional digit. With base-4, a fluctuation may bounce a value between 3 different values! This is avoiding the problem of logic, which further complicates things.
</details>

## Common Datatypes

The following is a compilation of the most common datatypes in programming. Most languages share these types, 

### Booleans

<span id="k-bool">**Boolean** values have two possible values: true or false</span>. Bools are commonly used in logic, for example "if value is true, do this." Boolean expressions are like mathematical equations that will evaluate to true or false. Examples include checking if a value is equal to some ohter value, or inequalities.

### Strings

<span id="k-str">**Strings** represent text values</span>. Most languages denote strings by using quotation marks (`""`). Anything contained within the quotation marks is regarded as text. Strings are commonly used for displaying some message to the screen. Strings do not have maximum value per se, but languages tend to impose a maximum length per string, typically 65535.

Examples: `"Name"`, `"Hello, world"`, `""` (empty string)

<span id="char">**Chars** exist in some languages as an individual character in a string, and are 1-2 bytes in length</span>. This means that a string can be thought of as a grouping of chars. In languages that make the distinction between chars and strings, chars are represented by single quotation marks (`''`).

Examples: `'a'`, `'T'`

### Integers

<span id="k-int">**Integers** are whole numbers, and can be positive or negative</span>. Integers are very common in mathematics and counting. Most languages reserve 4 bytes for each integer, which gives 2.14 billion possible values in each direction. The first bit is reserved for the sign.

Examples: `4`, `0`, `-213525`

### Floats

<span id="k-float">**Floating point numbers** have the ability to store fractional components</span>. The "point" refers to the decimal point, being able to store both very large and very small numbers. The precision of a float remains constant, "floating" around the decimal depending on where the precision is needed most. Single-precision floats take 4 bytes, while double-precision floats take 8 bytes.

Examples: `0.0`, `-3.14`, `5.53432`

### Collections

Collections are a way of storing related data together. In some languages, all of the data must be of the same datatype. There are many, _many_ types of collections in languages. The most common ones are as follows:

- <span id="k-array">**Arrays** are collections with a predetermined size</span>. The size of an array can be changed by creating a new array, and replacing the existing one in memory. Data can be put in the array by directly changing the data in a given position (called an **index**).
  - Example: `[3, -5, 0, 0]`
- <span id="k-list">**Lists** are like arrays without a predetermined size</span>. New data can be put into the list by appending it, or by changing the value at a given index.
- <span id="k-dict">**Dictionaries** are collections similar to lists, but instead of taking in a numerical value for position, they can take in any value</span>. <span id="k-mapping">Linking two pieces of data in this way is called a **mapping**</span>.
  - Example: `{"Name": "Scotty", "Age": 20}`
- Although not technically a collection, a tuple is an individual mapping between data. Tuples can contain more than 2 related pieces of data. 
  - Example: `("Name", "Scotty")`

### Absence of data

<span id="k-null">Lastly, it's important to know what the absence of a value is. Each language has their own way of naming this, but the most common one is **null**</span>. What's important to know is that null is _not_ equivalent to other, seemingly empty values. For example, an empty string is represented as `""`, and this is not equal to a value of null. Null represents data that has not been filled in, and most operations will cause an error.

> **Challenge Question**: What other types of data do you think would be useful to store in a program?

<details>
<summary>Answer:</summary>
Some languages have additional types, such as signed and unsigned numerical types. Chapter 8 will cover the concept of objects--types with user-defined data.
</details>

## Variables

Each program has memory that is specifically used to store its data. An individual section of memory that stores data is called a **variable**. A good way to think of variables is as a bucket. Each bucket has a name we give it in code, such as `my_num` or `value`. In most languages, the bucket also has a type associated with it. That means if you have a variable `my_num` that only takes in integers, it will cause an error when trying to put a string into it.

**Initializing** is the process of reserving memory for a variable. Initialization involves giving the variable a name (called an **identifier**), a data type, and sometimes a starting value. Variables do not exist before initializing them, so trying to access a variable before it is defined will cause an error. The act of giving a variable a value is called **assignment**.

When you see a variable in code, imagine that you are literally replacing every instance of the variable with the provided value.

## Pseudocode Examples

Let's put this into some pseudocode. The below example initializes a variable `My_Integer` with an integer datatype, and assigns it a value of 5.

```
integer My_Integer = 5
```

In nearly all languages, assignment is performed with the single equals sign (`=`). The value on the right is provided to the variable on the left side of the equals sign. Variables can be reassigned after they have been initialized, and do not require providing a datatype, like so:

```
string My_String = "Hello"

My_String = "Reassignment is easy!"
```

Finally, variables can be assigned the value of other variables. To do this, the name of the variable is provided, without quotes. The value can be imagined as being "copied" from the first line (the assignment into `String_1`) into the second line (the reading of `String_1` into `String_2`):

```
string String_1 = "Value"

string String_2 = String_1
```

Now, `String_2` contains the text `"Value"`.

<!--Styles for summary hover tag.-->
<style>
summary:hover {
  font-weight: bold;
  cursor: pointer;
}
</style>