# Logic

Logic is a set of rules that a program will follow. Programs use logic to change **control**, which is where the program will go to next. Programmers utilize **control structures** to modify the flow of control.

This chapter is split into two parts: Chapter 5 will cover scope and branching, while 5.1 will cover two types of loops.

## Scope

```
Outer scope
{
    Inner scope
    {
        Innermost scope
        {

        }
    }
}
```

**Scope** is the layer of nesting, or complexity, of a set of lines in a program. The important thing to know about scope is that variables defined in an outer scope can freely pass in and out of an inner scope. Variables defined in an inner scope can not pass out of outer scope.

Programmers do two things to clarify the level of nesting.
1. **They use curly brackets**. Curly brackets tell the computer where a scope ends and begins.
2. **They create indentation**. Indenting helps the human tell where scope ends and begins. If the curly brackets are vertical with each other, then that helps clarify the beginning of scope.

Here is an example of a variable being allowed to enter a lower scope:

```
string My_Name = "Scott"

{
    # perfectly fine
    My_Name = "Johan"
}
```

The following code will cause an error, due to trying to access the variable `Your_Name` out of scope:

```
{
    string Your_Name = "Alice"
}

# Error: Out of scope
Your_Name = "Ali"
```

## If statements

```
if (expression)
{
    # navigated to if the expression is true
}
```

**If** is the standard statement used to move control. If statements take an expression inside parentheses, and defines a new level of scope. _If_ the expression evaluates to true, then control will jump to being inside of the new scope. Otherwise, the scope will be ignored. Here is an example of both:

```
integer My_Counter = 0

# evaluates to false
if (5 < 3)
{
    # adds 1 to counter
    My_Counter = My_Counter + 1
}

if (-3 < 10)
{
    # subtracts 1 from counter
    My_Counter = My_Counter - 1
}
```

What value does `My_Counter` hold? Well, let's start working through this code. The first expression evaluates to false, so the first layer of scope will be ignored. The second expression _does_ evaluate to true, so that layer of scope will run. `My_Counter` is assigned to itself (0) - 1, so the final value is **-1**.

Let's increase some complexity:

```
string Layer_of_Scope = "Outer scope"

if (true)
{
    boolean Continue = 5 > (3 - 1)
    Layer_of_Scope = "Middle scope"

    if (Continue)
    {
        Layer_of_Scope = "Innermost scope"
    }
}
```

Holy cow, what is even going on here? Let's work through the instructions step-by-step:
1. String `Layer_of_Scope` is assigned `"Outer scope"`.
2. An if statements checks for true. Is the boolean value of `true`, true? Of course it is. Let's go into the next scope:
3. A boolean variable called `Continue` is assigned the expression `5 > (3 - 1)`. To evaluate, we solve the parentheses first, which gives a value of 2. 5 is greater than 2, so `Continue` receives the value `true`.
4. `Layer_of_Scope` is assigned the value `"Middle scope"`.
5. A second if statement checks if the value held in `Continue` is true. It is! The next step is the last one, I promise.
6. Finally, `Layer_of_Scope` is assigned the value `"Innermost scope"`. That wasn't so bad!

In this program, control changed _twice_. Once when the first `if` statement evaluated to true, and a second time when the next `if` evaluated to true. Let's check out the next type of control flow:

### Else statements

```
if (expression)
{
    # navigated to if the expression is true
}
else
{
    # navigated to if the expression is false
}
```

**Else** statements are an extension of `if` statements. Else statements are navigated to when the expression associated with a given `if` statement evaluates to false. An else statement creates a new layer of scope, separate from the initial `if` statement. Check out the following code:

```
string My_Color = "Red"

if (false)
{
    My_Color = "Yellow"
}
else
{
    My_Color = "Blue"
}
```

What color is stored? Let's look at the `if` statement's expression: it is simply `false`. False will never be true, so we skip over the first scope, and instead move into the `else`'s scope. `My_Color` is then assigned `"Blue"`.

There is one more variant of an `if` statement, and that is the `else-if` statement:

### Else-if

```
if (expression)
{

}
else if (expression2)
{

}
```

**Else-if** is the final variant of an `if` statement that we will examine. Else-if statements are used when another condition should be checked. They evaluate another expression _if_ the first expression does not evaluate to true. Realistically, this is equivalent to the following code:

```
if (expression)
{

}
else
{
    if (expression2)
    {

    }
}
```

Most languages have an `else if` statement. For the languagese that don't, the above is what you have to use. Here's some example code that utilizes this statement:

```
integer X = 55
string Result = ""

if (X == 75)
{
    Result = "X is equal to 75"
}
else if (X < 75)
{
    Result = "X is less than 75"
}
else
{
    Result = "X is greater than 75"
}
```

This code assigns `Result` corresponding text depending on the evaluation of `X`'s value. In this instance, `X` is equal to 55, so the `if` statement evaluates to false. The `else if` statement evaluates to true since 55 is less than 75. You may have noticed that there is an additional `else` statement on the end, which I call chaining. The example above chains an `else` statement on the end, which is absolutely allowed!

> **Challenge Question**: Is there a limit to chaining?

<details>
    <summary>Answer</summary>
    Yes, there is. <code>if</code> statements have the following limits:<br/>
    <ul>
        <li>Each chain must start with an <code>if</code>.</li>
        <li>A chain may have 0 to many <code>else if</code> statements.</li>
        <li>A chain may end in 0 or 1 <code>else</code> statements.</li>
    </ul>
    As an example, this is allowed:
<pre>if (expression)
{
    # foo
}
else if (expression2)
{
    # bar
}
else if (expression3)
{
    # baz
}
else
{
    # biz
}</pre>
    But this is not:
<pre>
if (expression1)
{
    # foo
}
else
{
    # bar
}
else
{
    # baz
}
</pre>
</details>

## Additional Control Flow

<style>
summary:hover {
  font-weight: bold;
  cursor: pointer;
}
</style>