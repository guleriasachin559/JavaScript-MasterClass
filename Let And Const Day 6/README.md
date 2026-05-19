# 🔐 `let` and `const` Keywords

---

## 🔵 The `let` Keyword

```js
let z = 10;
```

| # | Behavior |
|---|---|
| 1 | ❌ **Cannot be re-declared** in the same scope |
| 2 | 🧱 **Block-scoped** — only accessible within the block it was defined in |
| 3 | ⏳ **Hoisting is allowed, but early access is not** *(Temporal Dead Zone applies)* |
| 4 | ✅ **Value can be modified** (reassignment is allowed) |

**Example — Re-declaration not allowed:**

```js
let z = 10;
let z = 20; // ❌ SyntaxError: Identifier 'z' has already been declared
```

---

## 🔴 The `const` Keyword

| # | Behavior |
|---|---|
| 1 | 📖 **Read-only** — value cannot be changed after assignment |
| 2 | ❌ **Cannot be re-declared** |
| 3 | ❌ **Cannot be reassigned** |
| 4 | 🧱 **Block-scoped** — same as `let` |
| 5 | ⏳ **Hoisting is allowed, but early access is not** *(Temporal Dead Zone applies)* |

**Convention:** `const` variables are typically written in `UPPER_SNAKE_CASE`:

```js
const RATE_OF_INT = 8.5;
```

---

## ⏳ Temporal Dead Zone (TDZ)

When JavaScript runs your code, variables declared with `let` and `const` are **hoisted** just like `var` — but with a key difference.

### How it works:

```
Phase 1 — Memory Allocation (Hoisting)
┌──────────────────────────────────────────────────────────────┐
│  var  variables  →  stored in Global Memory  →  undefined    │
│  let/const vars  →  stored in Temporal Dead Zone (TDZ)       │
└──────────────────────────────────────────────────────────────┘

Phase 2 — Code Execution
┌──────────────────────────────────────────────────────────────┐
│  Once the line of initialization is reached,                 │
│  the variable moves OUT of the TDZ and becomes accessible.   │
└──────────────────────────────────────────────────────────────┘
```

> **Temporal Dead Zone** = the period between when a `let`/`const` variable is hoisted and when it is actually initialized. Accessing it during this window throws a `ReferenceError`.

---

## 💻 Examples

### `var` — hoisted with `undefined` (no TDZ)

```js
console.log(name); // undefined  ✅ (no error)
var name;
```

### `let` — hoisted but in TDZ (early access throws error)

```js
console.log(age); // ❌ ReferenceError: Cannot access 'age' before initialization
let age;

age = 20;
console.log(age); // 20  ✅
```

### `let` declared before use — works perfectly

```js
let name = "Jatin";
console.log(name); // "Jatin"  ✅
```
