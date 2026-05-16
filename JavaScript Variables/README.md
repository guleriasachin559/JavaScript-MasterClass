# 📦 What are Variables?

> A **variable** is a meaningful name given to a memory location.

When you have a piece of data, it gets stored somewhere in memory. Instead of referring to that raw memory address, you give it a **name** — that name is your variable.

```
Data  ──[stored in]──►  Memory  ──[named as]──►  Variable
```

**Example:**

```js
count = 10;
// 10 is the data, stored in memory, and "count" is the variable name.
```

---

## 🔑 The `var` Keyword

```js
var count = 10;
```

- In JavaScript, variables are created using the `var` keyword.
- `var` was the **only** way to declare variables from **1995 to 2015**.
- However, `var` comes with a few significant problems *(covered below)*.

---

## 🔍 How JavaScript Executes Your Code

Consider the following code:

```js
var name = "Jatin";
console.log(name);
var age = 10;
var address;
```

When this runs, the browser sends it to the **JavaScript Engine (V8)**, which creates a **Global Execution Context (GEC)** with two components:

```
Global Execution Context
┌──────────────────────────┬──────────────────────────┐
│   Memory Component       │   Code Component         │
│   (Variable Environment) │   (Thread of Execution)  │
└──────────────────────────┴──────────────────────────┘
```

This GEC is pushed onto the **Call Stack**.

### Phase 1 — Memory Allocation *(Hoisting)*

Before any code runs, JavaScript scans the **entire file** for variable and function declarations and allocates memory for them upfront — all initialized to `undefined`.

```
Memory Component:
┌───────────┬───────────┐
│   Key     │   Value   │
├───────────┼───────────┤
│  name     │ undefined │
│  age      │ undefined │
│  address  │ undefined │
└───────────┴───────────┘
```

### Phase 2 — Code Execution

JavaScript now executes the code **line by line**, replacing `undefined` with the actual values:

```
name     →  "Jatin"
age      →  10
address  →  undefined  (no value was assigned)
```

---

## 🏗️ What is Hoisting in JavaScript?

> **Hoisting** is JavaScript's behavior of moving all variable and function **declarations** to the top of their scope during Phase 1 (Memory Allocation), before any code is executed.

- Variables declared with `var` are hoisted and initialized with `undefined`
- Functions are hoisted with their **entire body**

```js
console.log(name); // undefined (not an error — it's hoisted!)
var name = "Jatin";
```

---

## ⚠️ Problems with the `var` Keyword

### 1. Allows Re-declaration

The same variable can be declared multiple times without any error — which can lead to accidental overwrites and hard-to-find bugs.

```js
var address;
var address = "Mumbai";
var address = "Delhi";  // No error — but this is problematic!
```

### 2. No Block Scope

Variables declared with `var` are **not limited to the block** `{ }` they are defined in. They "leak" out into the surrounding scope.

```js
for (var i = 0; i < array.length; i++) {
    console.log(i); // works as expected inside the loop
}

console.log(i); // ⚠️ still accessible outside the block!
```

> This is why modern JavaScript introduced `let` and `const` in **ES6 (2015)** — both of which are **block-scoped** and do **not** allow re-declaration.
