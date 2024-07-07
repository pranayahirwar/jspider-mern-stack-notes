Q. How to take input from user in JS?

A. Use `prompt()` function which is not part of JavaScript it's a part of ***Web-API*** to take input from user in browser in Javascript.

```javascript
prompt()
prompt(message)
prompt(message, defaultValue)
```

**Parameters**

`message` (Optional)
A string of text to display to the user. Can be omitted if there is nothing to show in the prompt window.

`defaultValue` (Optional)
A string containing the default value displayed in the text input field.

`Return value`
A string containing the text entered by the user, or `null`.

---

Q. How to change datatype from string to number, why because return value of above `prompt()` function is either STRING or NULL?

A. Using Number(VarNameORValueToBeConvertedToNumber)

```javascript
// We get NaN when JS compiler can't convert any given datatype to valid Number
Number("any string"); // Expected Output: NaN
```
