# Type Conversion Vs Type Coercion & Typecasting

**Type Conversion**: Explicit conversion of one datatype to another datatype comes under 

**Type Coercion**: Implicit conversion of one datatype to another datatype comes under 

### Typecasting

Q. How to convert String to Number in JS?

A. There are several ways to convert a string to a number in JavaScript. Here they are, listed from most recommended to least recommended:

1. **Number function**: This is the most recommended way because it's explicit that you're converting a string to a number. If the string can't be converted, it returns `NaN`.

```javascript
let str = "123";
let num = Number(str); // 123
```

2. **Unary plus operator**: This is a quick and easy way to convert a string to a number. However, it can be less readable to people unfamiliar with the trick.

```javascript
let str = "123";
let num = +str; // 123
```

3. **parseInt function**: This is useful when you want to convert a string to an integer. It ignores any non-numeric characters (characters which are not number eg. a, A, z, Z, $, #) after the first number in the string. If the string can't be converted, it returns `NaN`.

```javascript
let str = "123.45";
let num = parseInt(str); // 123

let str = "123abc";
let num = parseInt(str); // 123
// `parseInt` starts parsing the string from the left. It successfully converts the characters '1', '2', and '3' into the number 123. However, when it encounters the character 'a', it stops parsing because 'a' can't be converted into a number. As a result, `parseInt` returns the number 123, effectively ignoring the 'abc' at the end of the string.

let str = "abc123";
let num = parseInt(str); // NaN
// If non-numeric characters are at beginning then it will return NaN
// In this case, tries to start parsing the string from the left, but it immediately encounters a character ('a') that can't be converted into a number. As a result, it returns `NaN`.
```

4. **parseFloat function**: This is useful when you want to convert a string to a floating-point number. It ignores any non-numeric characters after the first number in the string. If the string can't be converted, it returns `NaN`.

```javascript
let str = "123.45";
let num = parseFloat(str); // 123.45
```

5. **Multiplication by 1**: This is a trick similar to the unary plus operator, but it can be even less readable.

```javascript
let str = "123";
let num = str * 1; // 123
```

---

Q. How to convert Number to String in JS?

A. Ways to convert a number to a string in JavaScript in most to least recommended ways-

1. **String function**: This is the most straightforward way. It's explicit that you're converting a number to a string.

```javascript
let num = 123;
let str = String(num); // "123"
```

2. **toString method**: This method is called on a number and returns a string representation of the number.

```javascript
let num = 123;
let str = num.toString(); // "123"
```

3. **Template literals**: This is a more modern way to convert a number to a string. It's especially useful when you want to include a number inside a larger string.

```javascript
let num = 123;
let str = `${num}`; // "123"
```

4. **Concatenation with an empty string**: This is a quick and easy way to convert a number to a string, but it can be less readable to people unfamiliar with the trick.

```javascript
let num = 123;
let str = num + ''; // "123"
```
