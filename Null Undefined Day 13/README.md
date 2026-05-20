# 🕳️ `null` and `undefined` in JavaScript

---

## ❓ What is `undefined`?

> `undefined` is JavaScript's way of saying **"this exists, but has no value yet."**

JavaScript **automatically** assigns `undefined` as the default value when:

### 1. A variable is declared but not assigned

```js
let username;
console.log(username); // undefined
```

### 2. An object property does not exist

```js
let person = { name: 'Jatin' };

console.log(typeof person);  // "object"
console.log(person.name);    // "Jatin"
console.log(person.age);     // undefined ← property doesn't exist
```

### 3. A function is called without passing an argument

```js
function greet(personName) {
    console.log(`Hello ${personName}, how are you?`);
}

greet('Katrina'); // Hello Katrina, how are you?
greet();          // Hello undefined, how are you? ← no argument passed
```

---

## 🔍 `typeof undefined`

```js
let username;
console.log(typeof username); // "undefined"
```

> The `typeof` an `undefined` value is `"undefined"` itself.

---

## ❌ What is `null`?

> `null` is a value that a **developer explicitly assigns** to indicate "no value" or "empty." It is intentional, unlike `undefined` which is assigned automatically by JavaScript.

```
JavaScript assigns  →  undefined  (automatic, no value yet)
Developer assigns   →  null       (intentional, explicitly empty)
```

```js
let user = null;
console.log(user); // null
```

> All **non-primitive data types** (objects, arrays, functions) have a default value of `null` when explicitly set to empty.

---

## ⚠️ The `typeof null` Bug

```js
let username; // undefined
let user = null;

console.log(typeof username); // "undefined"  ✅
console.log(typeof user);     // "object"     ⚠️ — this is a known JS bug!
```

> `typeof null` returns `"object"` — which is incorrect and a long-standing bug in JavaScript. `null` is **not** an object; it is its own primitive type.

---

## 🟰 `null` vs `undefined` — Equality Check

```js
console.log(null == undefined);  // true  ✅ — loose equality (only checks value)
console.log(null === undefined); // false ❌ — strict equality (checks value + type)
```

---

## 📊 Quick Reference

| | `undefined` | `null` |
|---|---|---|
| **Set by** | JavaScript (automatic) | Developer (intentional) |
| **Meaning** | No value assigned yet | Explicitly empty |
| **`typeof`** | `"undefined"` | `"object"` *(JS bug)* |
| **Loose equal `==`** | `null == undefined` → `true` | `null == undefined` → `true` |
| **Strict equal `===`** | `null === undefined` → `false` | `null === undefined` → `false` |
