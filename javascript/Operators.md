# Operators in JavaScript

Q. What is Operators?

A. Operators are special *symbols*, which use to *perform operations* on it's *operands* or variables or values passed to these operators.

> [!info]
> Operator always return some value after performing operations on it's operands.
> Unary, Binary, Ternary Operator all return some values.
> 
> Examples:
> 
> 1. `10 + 20` Addition operator sum of it's operand on it's left and right which is `30`
> 2. if A=10 then `let B = A++` which is Unary Operator returns value of a before modification hence `B=10` not 11 (which is updated value of A variable)

### Different types of Operator categorized into
1. [Arithmetic Operator](ArithmeticOperator.md)  
2. [Unary Operator](UnaryOperator.md)       
3. [Operator Overloading](OperatorOverloading.md) 


---
### Programming Questions

1. Write a function to add two numbers
```javascript
function addTwoNumbers(a, b) {
	return a + b
}
console.log(addTwoNumbers(10, 20))
```

2. Write a function to add N number of arguments passed to a function
```javascript
function addNNumbers(...variableNumberArgs) {
  let total = 0;
  for (let i = 0; i < variableNumberArgs.length; i++) {
    total += variableNumberArgs[i];
  }
  return total;
}
console.log(addNNumbers(1, 2, 3, 4, 5));
```