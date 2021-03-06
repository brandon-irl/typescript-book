## Equality

One thing to be careful about in JavaScript is the difference between `==` and `===`. As JavaScript tries to
be resilient against programming errors `==` tries to do type coercion between two variables e.g. converts a
string to a number so that you can compare with a number as shown below:

```js
console.log(5 == "5"); // true   , TS Error
console.log(5 === "5"); // false , TS Error
```

However the choices JavaScript makes are not always ideal. For example in the below example the first statement is false
because `""` and `"0"` are both strings and are clearly not equal. However in the second case both `0` and the
empty string (`""`) are falsy (i.e. behave like `false`) and are therefore equal with respect to `==`. Both statements
are false when you use `===`.

```js
console.log("" == "0"); // false
console.log(0 == ""); // true

console.log("" === "0"); // false
console.log(0 === ""); // false
```

> Note that `string == number` and `string === number` are both compile time errors in TypeScript, so you don't normally need to worry about this.

Similar to `==` vs. `===`, there is `!=` vs. `!==`

So ProTip: Always use `===` and `!==` except for null checks, which we cover later.
