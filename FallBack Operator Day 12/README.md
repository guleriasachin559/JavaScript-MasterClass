# 🛡️ Fallback Operators in JavaScript

> Fallback operators provide a **default value** when a variable has no meaningful value. There are two main types:

| Operator | Name | Triggers fallback when value is... |
|---|---|---|
| `\|\|` | OR (Logical OR) | Any **falsy** value (`0`, `""`, `null`, `undefined`, `false`, `NaN`, etc.) |
| `??` | Nullish Coalescing | **Only** `null` or `undefined` |

```js
let username;
console.log(username); // undefined
```

---

## 1️⃣ `||` — OR Fallback *(triggers on ALL falsy values)*

> Returns the right-hand value if the left-hand side is **any falsy value**.

```js
console.log(username || "jatin"); // "jatin"  ✅ — username is undefined (falsy)
console.log(0        || "jatin"); // "jatin"  ✅ — 0 is falsy
console.log(""       || "jatin"); // "jatin"  ✅ — empty string is falsy
```

> ⚠️ This can be a problem when `0` or `""` are **valid** values — `||` would incorrectly replace them with the fallback.

---

## 2️⃣ `??` — Nullish Coalescing *(triggers ONLY on `null` or `undefined`)*

> Returns the right-hand value **only** if the left-hand side is `null` or `undefined`. All other values — including `0` and `""` — are passed through as-is.

```js
console.log(username ?? "jatin"); // "jatin"  ✅ — username is undefined
console.log(0        ?? "jatin"); // 0        ✅ — 0 is NOT null/undefined, kept as-is
console.log(""       ?? "jatin"); // ""       ✅ — empty string is NOT null/undefined, kept as-is
```

---

## 🔑 When to Use Which?

| Use `\|\|` when... | Use `??` when... |
|---|---|
| Any falsy value should trigger the fallback | Only `null` or `undefined` should trigger the fallback |
| You're certain `0` and `""` are never valid values | `0` or `""` might be **intentional valid values** |
