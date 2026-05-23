# 🔢 Number Data Type

---

## ☕ Numbers in Java

Java separates numbers into distinct types based on size and precision:

| Category | Types |
|---|---|
| **Whole Numbers** | `byte`, `short`, `int`, `long` |
| **Decimal Numbers** | `float`, `double` |

---

## 🌐 Numbers in JavaScript

> In JavaScript, **both whole numbers and decimal numbers** fall under a single `Number` data type — stored as a **64-bit floating point (IEEE 754)** value.

```js
let age  = 35;
let pi   = 3.142;
let data = -100;

console.log(typeof age);  // "number"
console.log(typeof pi);   // "number"
console.log(typeof data); // "number"
```

### ⚠️ The Floating Point Precision Problem

Because decimals are converted to binary internally, JavaScript can only store an **approximate** value:

```js
console.log(0.1 + 0.2);           // 0.30000000000000004  ⚠️ Not exactly 0.3
console.log((0.1 + 0.2) === 0.3); // false
```

> `0.1 + 0.2` loses precision because decimals cannot always be represented exactly in binary.

---

## 🟰 Equality Operators — `=` vs `==` vs `===`

| Operator | Name | Purpose |
|---|---|---|
| `=` | Assignment | Assigns a value to a variable |
| `==` | Loose Equality | Compares **value only** (type coercion applied) |
| `===` | Strict Equality | Compares **value AND type** (always preferred in JS) |

> In JavaScript, always prefer `===` over `==` to avoid unexpected type coercion bugs.

---

## 🔬 What is `Number.EPSILON`?

> `Number.EPSILON` is the **smallest possible difference** between `1` and the next representable decimal number in JavaScript. It is used to safely compare decimal values that may suffer from floating point imprecision.

```js
console.log(Number.EPSILON);          // 2.220446049250313e-16
console.log(1 + Number.EPSILON);      // 1.0000000000000002
console.log(1 + Number.EPSILON / 2);  // 1  (difference too small to register)
```

### ✅ The Correct Way to Compare Decimal Numbers in JS

```js
Math.abs(a - b) < Number.EPSILON
```

> `Math.abs()` converts any negative result to a positive number, so the comparison always works regardless of which value is larger.

---

## 📏 `Number.MAX_SAFE_INTEGER` — The 64-bit Limit

JavaScript's `Number` type can only **safely** represent integers up to a certain size. Beyond this, precision is lost:

```js
console.log(Number.MAX_SAFE_INTEGER);     // 9007199254740991  ✅
console.log(Number.MAX_SAFE_INTEGER + 1); // 9007199254740992  ⚠️
console.log(Number.MAX_SAFE_INTEGER + 2); // 9007199254740992  ⚠️ (same as +1 — precision lost!)
console.log(Number.MAX_SAFE_INTEGER + 3); // 9007199254740994  ⚠️
```

> Once you exceed `MAX_SAFE_INTEGER`, JavaScript can no longer guarantee accurate integer representation. For numbers this large, use **`BigInt`** instead.

---

## ♾️ Special Number Values

### Infinity & Negative Infinity

```js
console.log(10 / 0);  //  Infinity
console.log(-10 / 0); // -Infinity
```

### `NaN` — Not a Number

```js
console.log(0 / 0);       // NaN  (indeterminate form)
console.log("5" - 5);     // 0    ✅ (JS coerces "5" to a number)
console.log("5" - 2);     // 3    ✅ (JS coerces "5" to a number)
console.log("abc" - 2);   // NaN  ⚠️ ("abc" cannot be converted to a number)
```

### 🤯 Quirky `NaN` Facts

```js
console.log(typeof NaN); // "number"  ⚠️ NaN is ironically of type Number!
console.log(NaN === NaN); // false    ⚠️ NaN is not equal to itself — unique in JS
```

> `NaN` is the **only value in JavaScript that is not equal to itself**. To reliably check for `NaN`, use `Number.isNaN(value)` instead of `=== NaN`.
