# 🔁 Loops in JavaScript

> Loops allow you to **repeat a line of code or an entire block** again and again — either a fixed number of times or until a condition is met.

**The Problem without loops:**

```js
console.log("Hello");
console.log("Hello");
console.log("Hello");
console.log("Hello");
console.log("Hello");
// ...repeating the same line manually is tedious and error-prone
```

> ✅ **Loops eliminate code duplication** — write the logic once, run it as many times as needed.

---

## 🧱 Line of Code vs Code Block

```js
// A single line of code
console.log("Hello");
let a = 10;

// A code block — multiple lines grouped inside { }
{
    let b = 20;
    console.log(b * 10);
}
```

---

## 📋 Types of Loops in JavaScript

| Loop | Best Used When |
|---|---|
| `for` | You know the exact number of repetitions |
| `while` | You repeat based on a condition (count unknown) |
| `do-while` | You need the block to run **at least once**, regardless of the condition |
| `forEach` | You want to iterate over each element of an array |

---

## 1️⃣ `for` Loop — Repeat N Times

> Use the `for` loop when you know exactly how many times you want to repeat.

**Syntax:**

```
for (initialization; condition; updation) { }
```

```js
for (let i = 1; i <= 10; i++) {
    console.log(i);
    console.log("Jatin");
}
```

**Breaking down each part:**

| Part | Example | Meaning |
|---|---|---|
| Initialization | `let i = 1` | Start the loop counter at 1 |
| Condition | `i <= 10` | Keep looping while `i < 10` OR `i === 10` (either is true → continue) |
| Updation | `i++` | After each iteration, increment `i` by 1 (`i = i + 1`) |

---

## 2️⃣ `while` Loop — Repeat Based on a Condition

> Use the `while` loop when you don't know in advance how many times to repeat — it keeps running as long as the condition is truthy.

```js
// ⚠️ Infinite loop — 1 is always truthy, this never stops
while (1) {
    console.log("Hello");
}

// ❌ Never executes — undefined is falsy
while (undefined) {
    console.log("Hello");
}

// ✅ Controlled loop — runs exactly 10 times
let i = 0;
while (i < 10) {
    console.log("Hello");
    i++;
}
```

---

## 3️⃣ `do-while` Loop — Always Runs At Least Once

> The `do-while` loop executes the block **first**, then checks the condition. Even if the condition is `false` from the start, the block runs **once**.

```js
do {
    console.log("Hello from do-while"); // ✅ always runs at least once
} while (undefined);                    // condition is false — loop stops after first run
```

**Key difference from `while`:**

| | `while` | `do-while` |
|---|---|---|
| Checks condition | **Before** executing | **After** executing |
| Minimum executions | 0 (may never run) | 1 (always runs once) |
