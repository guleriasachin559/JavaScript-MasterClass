# 📝 What is a String?

> A **String** is a series of characters — anything inside quotes is treated as a String in JavaScript.

---

## 🔤 Creating Strings — Three Ways

```js
let fname = "jatin";  // Double quotes
let x     = 'jatin';  // Single quotes  — both are identical
let y     = `jatin`;  // Backtick (Template Literal) — most flexible
```

All three are valid. The backtick (`` ` ``) form is preferred for multi-line strings and embedding variables.

---

## 🧠 How Strings are Stored in Memory

```
Stack Memory          Heap Memory
┌────────┐           ┌───────────┐
│ fname ─┼──────────►│  "jatin"  │
│ x     ─┼──────────►│  (same)   │  ← No duplicates — all variables
│ y     ─┼──────────►│  (same)   │    point to the same value
└────────┘           └───────────┘
```

> String values in heap memory are **not duplicated**. If multiple variables hold the same string, they all reference the **same value** in heap memory.

---

## 🔧 Template Literals (Backtick Strings)

Template literals support **multi-line strings** and **variable interpolation** using `${}`:

```js
let data = 10;

// Using template literal (preferred)
let message = `The value of data is ${data}`;
console.log(message); // The value of data is 10

// Using concatenation (older style)
let message2 = "The value of data is " + data;
console.log(message2); // The value of data is 10
```

---

## 🔒 Strings are Immutable

> **You cannot modify a string in place.** Any change you make creates a **brand new string** instead.

```js
let fname = "jatin";
console.log(fname[0]); // "j"

fname[0] = 'R';        // ⚠️ Attempting to modify...
console.log(fname);    // "jatin"  — unchanged! Modification is silently ignored.
```

**Compare this with an Array — which IS mutable:**

```js
let no = [10, 20, 30];
console.log(no[0]); // 10

no[0] = 33;
console.log(no);    // [33, 20, 30]  ✅ — array elements can be modified
```

---

## 🟰 Comparing Strings

Primitive strings are compared using `===`, which checks both **value and type**:

```js
let x = `jatin`;
let y = `jatin`;

console.log(x === y); // true  ✅
```

JavaScript compares the **final resolved value** — not how the string was constructed:

```js
let z = `jat` + `in`;         // concatenation happens first → "jatin"
console.log(x === z);          // true  ✅

let a = ['j','a','t','i','n'].join(""); // joined → "jatin"
console.log(x === a);          // true  ✅
```

### ⚠️ `new String()` — Object vs Primitive

```js
let b = new String("jatin"); // creates a String OBJECT (not a primitive)
let c = b.valueOf();          // extracts the primitive value from the object

console.log(typeof b); // "object"  ⚠️ — not "string"!
console.log(x === b);  // false     ⚠️ — a primitive string !== a String object
console.log(x === c);  // true      ✅ — valueOf() extracts the primitive
```

> Avoid using `new String()` — it creates a **String object**, not a primitive string, which causes unexpected `===` comparisons to fail.
