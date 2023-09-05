# Expressions and Assignment Statements

Computers are above all else, good at calculating. With the idea of a variable to hold onto information, we can learn how to do calculations with the information to be able to produce new results. To start out, let's get a very important term defined.

---

## Literal

In Chapter 1 Section 1, we referred to the idea of a **`String` literal**, which is where we use the double quotes with text to define a `String` within a program (we used it then in the context of the `print` method). A `String` literal is just the `String`-specific version of the idea of a **literal**, which can be more broadly defined as anywhere where we write out a value explicitly.

Let's look at this code sample from `NotesLiteral1.java`:

```java
int wholeNumberVariable = 10;
double decimalNumberVariable = -3.957;
boolean booleanVariable = true;
```

The integer, double, and boolean variable lines are all from Chapter 1 Section 2. There is a lot to unpack from this file, but let's look specifically at the values along the right side. `10`, `-3.957`, `true`, and `"Hello, World!"` are examples of literals, since we are _literally_ writing the value out explicitly.

In this section, we want to understand the whole code segment above, not just the literals, so let's explore the first important idea at work here: declaration.

---

## Declaration

In Java, we refer to the idea of **variable declaration**, where we clearly create a variable and assign memory to be able to store information.

Let's look at this code sample from `NotesDeclaration1.java`:

```java
int wholeNumberVariable;
double decimalNumberVariable;
boolean booleanVariable;
```

These are the same variable from the code sample we went over with literals, but this time just stripped down to the declaration aspect. Variable declaration has two distinct parts:

1. A data type
2. A variable name

In the above example, out data types were the primitive types we learned about in Chapter 1 Section 2, specifically `int` as an integer value (a whole number), `double` as a double-precision floating-point value (a fraction/decimal), and `boolean` as a boolean value (a 0/1 or true/false). This portion tells Java how much memory to reserve for the new variable, as each type needs different amounts of memory.

The second portion of each is the variable name. This is not something the computer cares about in the background, but will be useful to the programmer as its the way to reference and otherwise access that place in memory this variable will have. As an example, anytime I want to work with the integer `wholeNumberVariable` value, I'll just have to write `wholeNumberVariable` in my code.

---

## Initialization

In Java, we refer to the idea of **variable initialization**, where we assign a variable a value to store in memory for the first time. This can be done in two different ways. The first is what we have seen in past code samples, where a variable is declared _and_ initialized in the same line.

Let's look at this code sample from `NotesInitialization1.java`:

```java
int wholeNumberVariable = 10;
double decimalNumberVariable = 4.56;
boolean booleanVariable = true;
```

Initialization is a special case of **variable assignment** which we'll discuss next. Throughout a program, a variable can be assigned different values, and the first time a variable is assigned a value we refer to it as initialization. Assignment is handled by the equals sign operator `=`, which will take the value written to the right of it, and assign it to be stored by what is written to the left of it.

Let's break down what happens in the first line of our sample above:

1. `int wholeNumberVariable` declares the `wholeNumberVariable` variable as type `int`, so it is now ready to be used.
2. `wholeNumberVariable = 10` is an initialization assignment, where we read to the right of the equals sign, `10`, and assign that value to the left of the equals sign, `wholeNumberVariable`, so now `wholeNumberVariable` represents the integer `10` for our purposes.

The second way initialization can be done is in two lines. It accomplishes the same thing, and is not often used, but for the example we had above, it would look like this sample from `NotesInitialization2.java` instead:

```java
int wholeNumberVariable;
wholeNumberVariable = 10;
double decimalNumberVariable;
decimalNumberVariable = 4.56;
boolean booleanVariable;
booleanVariable = true;
```

As you might be able to tell, this is not used as often because it is much more _verbose_: it requires more code to accomplish the same thing. That being said, sometimes it is necessary with the design of a program and so it is an option.

---

## Assignment

While we've gone over initialization as a special form of assignment, **variable assignment** is a powerful tool where we can set or reset the value of a variable throughout a program.

Let's look at this code sample from `NotesAssignment1.java`:

```java
int wholeNumberVariable = 10;
wholeNumberVariable = 15;
wholeNumberVariable = 5;
```

In this sample, the first line is nothing new to us, just declaring the variable `wholeNumberVariable` as an `int` and then assigning it the value `10` to store in memory. The second line is an assignment statement using the equals sign, also similar to what we saw in the sample from `NotesInitialization2.java` earlier, but this time something different is happening in the background. Due to `wholeNumberVariable` already having stored the value `10` from earlier, this assignment in the second line overwrites the previously stored value and forces it to store `15` in memory where it had been storing `10`. The third line does this again and erases the `15` to store `5` instead. It is very important to understand that the program does not remember the previous values, so once they are overwritten, they are lost to the computer forever, so be careful when doing computations not to overwrite an important value!

You can assign and re-assign values to a variable as many times as you would like. The only time we are restricted from assigning value is when we use the `final` keyword we saw in Chapter 1 Section 2 earlier. The `final` keyword locks a variable so that it's value cannot be changed, as a safety measure when it might be holding important information. Let's look at this sample from `NotesAssignment2.java`:

```java
final int wholeNumberVariable = 10;
wholeNumberVariable = 15;
```

In these notes, this looks like a perfectly normal segment of code, but opening the `NotesAssignment2.java` file reveals an error via a red underline at the second line of this code. When hovered, this red underline reveals the error as `The final local variable wholeNumberVariable cannot be assigned.`. The `final` keyword allows a variable to be initialized, that is assigned for the first time, and then locks it from being assigned to or overwritten further on in the code.

---

## Arithmetic Operations

One of the primary uses for computer programming is how proficiently they can do math, and lots of it, in short amounts of time. The most basic way for us to do this in Java is to use our arithmetic operators. Here are the 5 basic operators and the math operations they correlate to:

- `+` **Addition**
- `-` **Subtraction**
- `*` **Multiplication**
- `/` **Division** (note the forward slash, not back slash like our escape character from Chapter 1 Section 1)
- `%` **Remainder** - This is division of two numbers, like 19 divided by 4, except instead of the answer being 4 or 4.75, the answer is the remainder from the division or how much is left over, which in this example was 3 (you can take our 4 whole sets of 4, and then you are left with a remainder of 3 which we might incorporate into the division answer as 3/4 or 0.75).

These operations can be used on `int`- or `double`-type numbers, or a combination of the two, we just have to understand the behaviors associated with each one.

When doing any operation on two `int`-type values (whole numbers), the result provided by Java will be also be an `int`-type value, which includes a rounded division answer if necessary. For example:

- `5 + 3 = 8`
- `5 - 3 = 2`
- `5 * 3 = 15`
- `5 / 3 = 1` Note that the division answer is always rounded down to just the whole number that can be removed. We know that `5 / 3 = 1.67`, but we do not round up because we can only remove 3 once in its entirety.
- `5 % 3 = 2`

When doing any operation on two `double`-type values (fractional/decimal numbers), the result provided by Java will be also be a `double`-type value. For example:

- `5.2 + 3.4 = 8.6`
- `5.2 - 3.4 = 1.8`
- `5.2 * 3.4 = 17.68`
- `5.2 / 3.4 = 1.53`
- `5.2 % 3.4 = 1.8`

I said earlier that you could do arithmetic operations between an `int`-type and `double`-type value, so how does it decide what kind of answer to output, an `int` or a `double`? Due to it's higher complexity, the result between an `int` and a `double` will always be a `double`. For example:

- `5 + 3.2 = 8.2`
- `5 - 3.2 = 1.8`
- `5 * 3.2 = 16.0` Note that even though the answer is a whole number, it gives it as a decimal!
- `5 / 3.2 = 1.5625`
- `5 % 3.2 = 1.8`

It doesn't matter whether the `int` is first, or the `double` is first, it still gives the result as a `double` anyways:

- `5.2 + 3 = 8.2`
- `5.2 - 3 = 2.2`
- `5.2 * 3 = 15.6`
- `5.2 / 3 = 1.73`
- `5.2 % 3 = 2.2`

---

## Arithmetic Expressions

With our arithmetic operators ready, we can start to put them into an actual program. When we have the computer do an operation between two values, we refer to it as an **arithmetic expression**. One easy way to get this working in Java is that we can put arithmetic expressions in a print statement, and it will calculate the answer, and then print the result. Let's look at this sample from `NotesArithmetic1.java`:

```java
System.out.println(5 + 3.2);
System.out.println(5 - 3.2);
System.out.println(5 * 3.2);
System.out.println(5 / 3.2);
System.out.println(5 % 3.2);
```

Since we looked at these specific examples earlier, we can compare the printed results to our expectations of the calculation:

```
8.2
1.7999999999999998
16.0
1.5625
1.7999999999999998
```

Everything lines up with our expectations, except the subtraction and remainder answer. It's very close to what we expect, but the decimal is very long and seemingly random. When we introduced the idea of a double-precision floating-point value in Chapter 1 Section 2, we mentioned that this was really just a really good approximation of precise values, and here we can see that it can't store the number `1.8` and instead stores a very close approximation to it as `1.7999999999999998` instead.

It is really important to recognize and understand that there is an order that the computer worked through `System.out.println(5 + 3.2)`. It first resolved/calculated what was inside of the print statement by finding `8.2` as the answer to `5 + 3.2`, _then_ it printed the resulting value. This order holds up when we do something similar with variable assignment, like this sample from `NotesArithmetic2.java`:

```java
int wholeNumberVariable = 5 * 3;
double decimalNumberVariable = 5.2 / 3.4;
```

---

## Compound Statements and Order of Operations

Just like in our math classes, the computer follows an order of operations when doing math (and many other things). Just like in math where we have operations that share the same priority and are just covered from left to right, our computers do the same thing. When a computer prioritizes its operations, we refer to it as **operator precedence**. Here is the operator precedence for the Java programming language:

1. Grouping (in the form of parentheses `()`)
2. Multiplication (`*`), Division (`/`), Remainder (`%`)
3. Addition (`+`), Subtraction (`-`)
4. Assignment (`=`)

Just like our traditional order of operations, we have operations that share the same priority (like 2 and 3), and when they are both present they are done left-to-right (that is, the operation most to the left is done first and the operation most to the right is done last).

A **compound expression** is one that uses multiple operations. You may notice that our variable assignment from `NotesArithmetic2.java` would technically be a compound expression, as the equals sign (`=`) counts as one of our operations. We can put together much larger compound expressions that use many operations. Let's look at this example from `NotesArithmetic3.java`:

```java
int wholeNumberVariable = 3 + 4 * 2 / (4 - 5) - 4 % 3;
System.out.println(wholeNumberVariable);
```

To build a mutual understanding of our operator precedence, here is how Java would work through this example:

```java
int wholeNumberVariable = 3 + 4 * 2 / (4 - 5) - 4 % 3       // Original
int wholeNumberVariable = 3 + 4 * 2 / (-1) - 4 % 3          // Do what's in parentheses/grouping first (4 - 5) = (-1)
int wholeNumberVariable = 3 + 8 / (-1) - 4 % 3              // Multiplication came first from left to right 4 * 2 = 8
int wholeNumberVariable = 3 + (-8) - 4 % 3                  // Division comes next from left to right 8 / (-1) = (-8)
int wholeNumberVariable = 3 + (-8) - 1                      // Remainder comes next from left to right 4 % 3 = 1
                                                            // (4 divided by 3 leaves a remainder of 1)
int wholeNumberVariable = (-5) - 1                          // Addition came first from left to right 3 + (-8) = (-5)
int wholeNumberVariable = (-6)                              // Subtraction is our last operation (-5) - 1 = (-6)
int wholeNumberVariable = (-6)                              // Now we use the assignment operation = to save our
                                                            // number -6 to the variable
```

We can test if we did this correctly by running the `NotesArithmetic3.java` file and checking what value it prints out:

```
-6
```

Throughout the year we will be adding our future operations to this operator precedence list to keep an accurate priority list.

---

## Arithmetic Problems

Just like math, either by hand or by a calculator, we can run into issues sometimes. One classic example plays a role in our Java programming as well: division by zero. We learn in math classes that we can't divide by 0, and calculators will produce some sort of error when we do it. Java is no different and produces an **ArithmeticException**. Let's look at this sample from `NotesArithmetic4.java`:

```java
int wholeNumberVariable = 5 / 0;
```

Note that when just writing the code out, Java doesn't notice this being an issue. This is because this is known as a **RuntimeException**, meaning it is brought out when a program is run. When we run this program, this is what is produced:

```
Exception in thread "main" java.lang.ArithmeticException: / by zero
        at NotesArithmetic4.main(NotesArithmetic4.java:3)
```

We will be discussing more exceptions and errors throughout the year, and they might yield similar results like this when run. This note contains a lot of useful information:

- `java.lang.ArithmeticException: / by zero` - This is an `ArithmeticException`, with the cause being division by 0
- `at NotesArithmetic4.main(NotesArithmetic4.java:3)` - This happens in the `main` method in the `NotesArithmetic4.java` file at line 3.

Please use these messages to help find your problem when you get them!

---

## Final Notes

Taking our very first example from `NotesLiteral1.java`, the whole file looks like this:

```java
public class NotesLiteral1 {
    public static void main (String[] args){
        int wholeNumberVariable = 10;
        double decimalNumberVariable = -3.957;
        boolean booleanVariable = true;
    }  
}
```

We only honed in on the middle line with our variables initially, but every piece of this file is important to the program running and doing what we want. Taking a look at our second example from `NotesDeclaration1.java`, that whole file looks like this:

```java
public class NotesDeclaration1 {
    public static void main (String[] args){
        int wholeNumberVariable;
        double decimalNumberVariable;
        boolean booleanVariable;
    }  
}
```

Comparing the first two lines of code from both files should feel extremely similar, with only a slight variation. All of our Java files for the foreseeable future will have this structure. The first line is `public class NameOfFileHere{`, where you'll notice that in both examples, it utilizes the name of the file without the `.java` extension. The second line is identical in both cases as `public static void main (String[] args){`.

Throughout the year we will end up unpacking these lines and better understand how they work to better use them to our advantage. For the time being though, we will let Visual Studio Code autofill those lines when we create a Java file and understand that it's on the third line where we put our code using things like our variable statements.

---

## Assignment

Now that you have gone through the notes for this section, you can check out the `assignment.md` and `Assignment.java` files to try a short assignment using this material.
