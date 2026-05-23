# 🔢 `BigInt` and `Symbol` in JavaScript

---

## 📏 Why `BigInt` Exists — The `Number` Limit

JavaScript's `Number` type is a **64-bit floating point**, which means it can only **safely** represent integers up to:

```
Maximum Safe Integer = 2⁵³ - 1 = 9007199254740991
```

```js
let data = Number.MAX_SAFE_INTEGER;

console.log(data);     // 9007199254740991  ✅
console.log(data + 1); // 9007199254740992  ⚠️
console.log(data + 2); // 9007199254740992  ⚠️ — same as +1! Precision is lost.
```

> Beyond `MAX_SAFE_INTEGER`, JavaScript can no longer guarantee accurate results. This is exactly the problem `BigInt` solves.

---

## 🔢 Creating a `BigInt`

There are two ways to create a `BigInt` value:

```js
let transactionId = 12312312312312313n; // Append 'n' to the number literal
let x = BigInt(100);                    // Use the BigInt() constructor

console.log(transactionId); // 12312312312312313n
console.log(typeof x);      // "bigint"
console.log(x);             // 100n
```

---

## ⚠️ Mixing `BigInt` with Regular Numbers

> You **cannot** directly mix `BigInt` and regular `Number` types in arithmetic — you must convert explicitly first.

```js
let no1 = 100;
let no2 = 100n;

console.log(no1 + no2);          // ❌ TypeError: Cannot mix BigInt and other types
console.log(BigInt(no1) + no2);  // ✅ 200n — convert no1 to BigInt first
```

---

## ➗ BigInt Division — Always Returns a Whole Number

> All mathematical operations (`+`, `-`, `*`, `/`) on `BigInt` return whole numbers — decimals are truncated, not rounded.

```js
let no1 = 10n;
let no2 = 3n;

console.log(no1 / no2); // 3n  ← not 3.333...n (decimal is dropped)
```

---

## 🟰 Comparing `BigInt` with Regular Numbers

```js
let no1 = 100n;
let no2 = 100;

console.log(no1 == no2);  // true  ✅ — loose equality (value only, type ignored)
console.log(no1 === no2); // false ❌ — strict equality (different types: bigint vs number)
```

---

## 🛠️ VS Code Tip — Code Runner Extension

> Install the **"Code Runner"** extension in VS Code to run JavaScript (and other languages) directly from the editor with a single click. A ▶ run button will appear in the top-right corner of your editor.

---

## 🔑 `Symbol` — Guaranteed Unique Identifiers

### 🆔 What is a UUID?

> **UUID (Universal Unique Identifier)** is an alphanumeric ID guaranteed to be unique every time it is generated. For example, every Git commit has a unique commit ID — that is the same concept in action.

### `Symbol` in JavaScript

> A `Symbol` is JavaScript's built-in way of creating a **guaranteed unique** value — even if two Symbols are created with the same description, they are never equal.

```js
let userIdOne = Symbol("userId");
let userIdTwo = Symbol("userId");

console.log(userIdOne);             // Symbol(userId)
console.log(userIdOne === userIdTwo); // false ❌ — every Symbol is always unique
```

> This makes `Symbol` ideal for use as unique property keys in objects, preventing accidental key collisions.
