# Operator Overloading

Q. What is Operator Overloading?

A. Change in behavior or operation of **operator** based on it's **operands datatype** is known as Operator Overloading. JS don't give access to users to overloading operators like other programming language Python, C++, instead JS has pre-overloaded some operator (like `+`) which will behave differently based on it's operands.

## Concatenation

Joining or combining (not summation or addition) of two or more operands is known as concatenation.
It is performed using `+` operator.

> [!TIP]
> To perform concatenation at least one operand should be of STRING DATATYPE.
> After concatenation result or returned value will be STRING DATATYPE

How concatenation decision made based on different datatypes of operands
- number + number : `+` operator will work as addition operator
- number + string : `+` operator will work as concatenation operator
- string + number : `+` operator will work as concatenation operator
- string + string : `+` operator will work as concatenation operator

Arithmetic operators operation (solution or evaluation) happens from LEFT -> RIGHT
Eg: `1 + 2 + "Hi" + 4 + "Hello"` -> `"3Hi4Hello"`
Remember: return value of concatenation operation is in STRING.
