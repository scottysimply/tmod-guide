# Functions

When a program increases in complexity, you may notice that you repeat yourself to write the same thing multiple times. Functions allow code to be reused despite only being written once.

## What is a Function?

Functions are similar to variables in that they are assigned names, formally called a **label** (or identifier). When a function's behavior is necessary, a function can be ran by **calling** it. Calling a function requires appending open and closed parentheses `()` to the end of its label. Let's see an example of calling functions:

```
# calls the function 'PerformAnAction'
PerformsAnAction()
# calls the function 'Exit'
Exit()
```

When functions are called, control will move from where the function was called _to_ where the function is defined at. We will define our own functions later in this chapter. For now, think of functions as moving whatever code they run _to_ where the function was called. We refer to the place where a function was called as a **call site**.

Suppose we need to compute 5 + 3 many times in our program. We then make a function `Add5And3()` to allow us to compute this all over our program:

```
Add5And3()
Add5And3()
Add5And3()
```

There's an issue here. The output is stuck in the function! Thankfully, functions can output values, called returning.

### Returning Values From a Function

**Returning** is the process in which a function outputs a value. When a function returns a value, the call site goes from being a _statement_--standalone fragments of code--to an _expression_; expressions must have some action done to them. For the example with adding 5 and 3, let's now use a "fixed" version of the function that returns the value.

```
integer Probably8 = Add5And3Fixed()
```

Hooray! We can now generate the value 8 by calling the function `Add5And3Fixed()`. I've had a change of heart, though. I want to be able to compute 5 + 3, and 8 + 5. Maybe some other values too. Arguments (not the verbal kind) solve this problem.

### Arguments

**Arguments** are values that a function takes in as input. When a function takes in an argument, the value is put inside of the parentheses. Multiple arguments can be specified by separating them with commas. Let's assume that we fixed our function, and it will now return both of our arguments added together. Calling it is as follows:

```
integer Probably8 = Sum(5, 3)
integer Probably13 = Sum(8, 5)

# nothing is stopping us from calling a function as a parameter
integer Probably34 = Sum(13, Sum(13, 8))
```

As you can see, we have now reduced our function from something specific (computing 5 + 3) to something that can compute all sorts of sums. This is an example of _abstraction_. As a refresher, abstraction is when a complicated or narrow topic is turned into something generic. In this case, the functionality of adding 5 anad 3 was abstracted into the ability to sum any two numbers.

Now that return values and arguments have been summed up, let's write some functions!

## Function Structure

```
func Return_Type Identifier(...params)
{

}
```

This is what it looks like when a function is defined. Let's break down everything going on here:
- `func` is a keyword that this psuedocode will use to specify when a function is being defined. Not all languages use a keyword for this, but mine will for readability.
- Functions create their own level of scope to keep code separated from the rest of the program.
- `Return_Type` is the datatype of what the function returns. A function can return an integer, string, even collections such as lists and arrays. **Void** specifies that the function will return no value.
- `Identifier` is the name of the function. Immediately following the name of the function are parentheses, and this is where any arguments will go.
- `...params` specifies the **parameters** for this function. Parameters are local variables that receive arguments when the function is called. Here are some valid parameters:
  - `integer My_Int`
  - `array Array`
  - `bool Flag`

A function's `signature` is a combination of its name, parameters, and rarely the return type. Two functions are not allowed to share the same signature, even if the return type is different.

> **Challenge Question**: Why can't two functions share the same signature?

<details>

</details>

The `return` keyword is used to stop executing the rest of a function. A value can be returned by putting a valid literal or expression immediately following `return`.

## Writing Functions

Now that the structure of a function has been highlighted, we can write our own! Let's start by writing a function that calculates the sum of two numbers, and returns it:

```
func integer Sum(integer Num_1, integer Num_2)
{
    return Num_1 + Num_2
}

integer Result = Sum(8, 5)
```

With the sum example above, this is what the function we called look like. Hopefully some pieces are coming together. Let's try another function that adds a space before and after a string:

```
func string Pad(string String)
{
    return " " + String + " "
}
```

String functions are very useful for formatting strings. 

## Input and Output
**Input and Output (I/O)** is the way of introducing interactivity in a program. Most languages have two built-in functions that handle textual I/O:

- `input()` is a function that tells the program to read text from a console.
- `output()` is a function that writes text to a console.

Slight problem, this is a guide! There's no console to showcase input or output. Thankfully, I've taken the liberty to display a virtual console. A set of inputs and outputs will have a less than symbol (<) and greater than symbol (>) denoting them, respectively:

<p class="c-hd">Virtual Console</p>
<pre class="c">
< This is an input
< This is also an input
> This is an output
< This is another line of input
> This is the last output
</pre>

Let's write some code that can utilize this! We'll start by showing examples of output.

### Output

The first program is basic, but this is the entry point for almost all programmers: Output the string `"Hello, world!"`:

```
output("Hello, world!")
```

<p class="c-hd">Virtual Console</p>
<pre class="c">
> Hello, world!
</pre>

Notice that a string outputted in the console is not double quoted. Quotation marks only exist in the programming language.

The next program will calculate the product 3 * 7, and output it to the console:

```
output(3 * 7)
```

<p class="c-hd">Virtual Console</p>
<pre class="c">
> 21
</pre>

As you can see, output can take in more than just strings. The result of the expression `3 * 7` is an integer, but the function was still able to execute. The last program will further increase complexity:

```
array My_Numbers = [5.5, -3.0, 12.23, 3.14]
output(My_Numbers)
output("The first element is " + My_Numbers[0])
```

<p class="c-hd">Virtual Console</p>
<pre class="c">
> [5.5, -3.0, 12.23, 3.14]
> The first element is 5.5
</pre>

That last line is a little bit tricky. The argument provided to the second output call utilizes string concatenation

### Input



## Conversions

<style>
.c-hd {
    margin-bottom: 0px;
    
}
.c {
    color: rgb(21, 162, 49);
}

</style>