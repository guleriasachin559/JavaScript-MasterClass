# 🗂️ Data Types in JavaScript

---

## ❓ What is a Data Type?

> A **data type** describes what kind of value you can store in memory using JavaScript.

---

## 📊 Types of Data Types

JavaScript data types are divided into **two** main categories:

```
                        Data Types
                            │
          ┌─────────────────┴──────────────────┐
          │                                    │
  Primitive (7)                        Non-Primitive
          │                                    │
  1. Number                            1. Object
  2. String                            2. Array
  3. Boolean                           3. Function
  4. Null
  5. Undefined
  6. BigInt
  7. Symbol
```

---

## 🔢 Primitive Data Types — Quick Reference

| # | Type | Description |
|---|---|---|
| 1 | **Number** | Whole numbers and decimals |
| 2 | **String** | A series of characters — `'jatin'` or `"jatin"` (both valid) |
| 3 | **Boolean** | `true` or `false` |
| 4 | **Null** | Intentional absence of a value |
| 5 | **Undefined** | Variable declared but not assigned |
| 6 | **BigInt** | Very large integers beyond the `Number` limit |
| 7 | **Symbol** | A unique and immutable identifier |

---

## 💻 Examples of Data Types

```js
let name          = 'Jatin';              // String
let age           = 35;                   // Number
let PI            = 3.142;               // Number
let isActive      = true;                // Boolean
let user          = null;                // Null
let data          = undefined;           // Undefined
let accountNumber = 234234234234234n;    // BigInt
let userId        = Symbol("a");         // Symbol

console.log(name);          // Jatin
console.log(age);           // 35
console.log(PI);            // 3.142
console.log(isActive);      // true
console.log(user);          // null  ⚠️ typeof returns "object" — a known JS bug
console.log(data);          // undefined
console.log(accountNumber); // 234234234234234n
console.log(userId);        // Symbol(a)
```

---

## 🔍 What is `typeof`?

> The `typeof` operator is used to find out the **data type** of a value at runtime.

```js
console.log(typeof name);   // "string"
console.log(typeof age);    // "number"
```

---

## 📦 Non-Primitive (Reference) Types

Unlike primitive types, reference types are stored in **heap memory** and accessed by reference.

### 🔷 Array

```js
let marks = [78, 88, 79, 66];

console.log(marks);         // [78, 88, 79, 66]
console.log(typeof marks);  // "object"
```

### 🔷 Object

```js
let userData = { name: "Katrina" };

console.log(userData);       // { name: 'Katrina' }
console.log(userData.name);  // Katrina
console.log(typeof userData); // "object"
```

### 🔷 Function

```js
function greet() {
    console.log("Hello!");
}

console.log(typeof greet); // "function"
```
