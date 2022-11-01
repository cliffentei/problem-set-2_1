# Problem Set 2.1
## Types, Values, and Operators

1. What is a _unary operator_? Give an example of one.

A *unary* operator is an operator that only takes in one value. An example of an *unary* operator is the **typeof** operator.

2. What is a _binary operator_? Give an example of one.

A *binary* operator is an operator that utilize two values. An example of a *binary* operator is the **minus** operator.

3. When do we use the _ternary operator_? Use a code snippet to illustrate below.

*Ternary*, or _conditional_ operators can be used in place of an if-else statement. For example:
```
console.log(true ? 1 : 2);
// → 1
```

Where true is the condition, 1 is the truthy expression and 2 is the falsy experssion. 

4. What is the difference between using the _strict_ and _non-strict_ equality operators?

_Strict_ equality operators (===) check whether its two operands are equal, returning a boolean result **BUT** always considers operands of different types to be different. _Non-strict_ equality operators (==) simply check whether its two operands are equal, returning a boolean result with type conversion being applicable.

5. What are the seven JavaScript data types? Which of these are considered _primitive_?

- The seven JavaScript data types are:
  - Number
  - String
  - Boolean
  - NULL
  - Undefined
  - Symbol
  - Bigint  
  and Object (the only non-_primitve_ data type)

6. What does the code below return?

```javascript
  typeof 'i love marcy lab';
  ```

This code will return string, as 'i love marcy lab' is a string.

7. What does the code below return?

```javascript
  typeof true;
  ```

This code will return boolean, as true and false constitute the boolean data type.

8. What does the code below return?

```javascript
  typeof (10**9);
  ```

This code will return number, as type of `(10**9)` doubles as 10^9, which will return a number value. 

9. What does the following code return? **Why**?

```javascript
  typeof null;
  ```

This code will return object, as the value null on its own represents the intentional absence of any object value.

10. What does it mean to be _truthy_ or _falsy_? What six values are _falsy_?

_Truthy_ values are values that evaluate to True in a boolean context, and _falsy_ values are values that evaluate to False in a boolean context. Six values that are _falsy_ are:
- Falsy
- 0
- -0
- null
- undefined
- NaN

11. Evaluate the following expressions using JavaScripts implicit coercion rules. For each example, in one sentence, explain what coercions were applied and why:

  * `8 * null` The output will be 0, as coercion turns null into 0, making 8 * 0 which ='s 0.
  * `"5" - 1` The output will be 4, as coercion turns "5" into a number, making 5 - 1 which ='s 4.
  * `"5" + 1` The output will be "51", as coercion allows for the concatenation of "5" and 1, turning 1 into the string, "1", making "5" + "1" which ='s "51".
  * `true + false` The output will be 1, as coerncion turns true into 1, and false into 0, making 1 + 0 which ='s 1.
  * `"i am" + undefined` The output will be "i amundefined", as coercion turns undefined into a string, making "i am" + "undefined".
  * `5 + undefined` The output will be NaN, as undefined will turn into NaN, making 5 + NaN which ='s NaN.


12. What will each line of the following code return?
   ```javascript
   (false && undefined);
   ```
   *false* (false is falsy, undefined is falsy, false && false don't check out as true.)

   ```javascript
   (false || undefined);
   ```
   *undefined* (the || operator returns the value to its left when that can be converted to true and will return the value on its right otherwise, in this case, undefined because false and undefined don't return to true)
   ```javascript
   (undefined || false); 
   ```
   *false* (the || operator returns the value to its left when that can be converted to true and will return the value on its right otherwise, in this case, false)
   ```javascript
   ((false && undefined) || (false || undefined));
   ```
   *undefined* (false && undefined) = false, (false || undefined) = undefined; false || undefined = undefined.
   ```javascript
   ((false || undefined) || (false && undefined));
   ```
   *false* (false || undefined) = undefined, (false && undefined) = false; undefined || false = false.
   ```javascript
   ((false && undefined) && (false || undefined));
   ```
   *false* (false && undefined) = false, (false || undefined) = undefined; false && undefined = false.
   ```javascript
   ((false || undefined) && (false && undefined));
   ```
   *undefined* (false || undefined) = undefined, (false && undefined) = false; undefined && false = undefined.
   ```javascript
   ('a' || (false && undefined) || '');
   ```
   *"a"* (false && undefined) = false, "a" || false = "a"; "a" || "" = "a".
   ```javascript
   ((false && undefined) || 'a' || '');
   ```
   *"a"* (false && undefined) = false, false || "a" = "a"; "a" || "" = "a"
   ```javascript
   ('a' && (false || undefined) && '');
   ```
   *undefined* (false || undefined) = undefined, "a" && undefined = undefined; undefined && "" = undefined
   ```javascript
   ((false || undefined) && 'a' && '');
   ```
   *undefined* (false || undefined) = undefined, undefined && "a" = undefined; undefined && "" = undefined
