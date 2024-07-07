# Arithmetic Operators

Arithmetic operators operation or solution or evaluation happens from LEFT -> RIGHT
1. `+`
2. `-`
5. `*`
3. `/`
4. `%`

`Math.trunc()` method to remove decimal value.

---
**How to remove last one, two or three ... digits from a number?**

```javascript
let n=1234;

// To remove last one digit
console.log(Math.trunc(n / 10))
// Expected Output: 123

// To remove last two digit
console.log(Math.trunc(n / 100))
// Expected Output: 12

// To remove last three digit
console.log(Math.trunc(n / 1000))
// Expected Output: 1

```

**How to get last one, two, ... digits from a number?**

```javascript
let n=1234;

// To remove last one digit
console.log(Math.trunc(n % 10))
// Expected Output: 4

// To remove last two digit
console.log(Math.trunc(n % 100))
// Expected Output: 34

// To remove last three digit
console.log(Math.trunc(n % 1000))
// Expected Output: 234

```

---
To write addition in short we can write `a += 1` do you think this is correct `a=+1` or `a =+ 1`?

Ans: Yes we can write, it seems wrong but, try to see this `a = -1` || `a=-1`, similarly we are representing +ve value of 1 above.
