# 🔴 Deep Dive into the `const` Keyword

---

## 📌 A Note on ES / ECMAScript

> **ES** stands for **ECMAScript** — the standard that defines the syntax and features of JavaScript. JavaScript follows the ECMAScript specification for its rules and behavior.

---

## 🔑 The Golden Rule of `const`

```
const does NOT lock the value — it locks the LINK (reference).
```

| Scenario | Allowed? |
|---|---|
| Re-assigning a primitive (`const x = 5; x = 10`) | ❌ Not allowed |
| Re-assigning an object/array to a new one | ❌ Not allowed |
| Modifying a property inside a `const` object | ✅ Allowed |
| Modifying an element inside a `const` array | ✅ Allowed |

---

## 💻 Example 1 — Re-assigning a Primitive Value

```js
const PI = 3.14;
PI = 2; // ❌ TypeError: Assignment to constant variable.

console.log(PI);
```

> Since `PI` holds a **primitive value**, re-assigning it directly changes the link — which `const` does not allow.

---

## 💻 Example 2 — Modifying a Property Inside a `const` Object

```js
const data = { name: "Jatin" };
data.name = "Katrina"; // ✅ Allowed — modifying the value inside the object

console.log(data);       // { name: 'Katrina' }
console.log(data.name);  // Katrina
```

**Why does this work?**

```
Stack Memory                  Heap Memory
┌───────────┐                ┌──────────────────────┐
│  data ────┼───────────────►│  { name: "Katrina" } │
└───────────┘                └──────────────────────┘
     ↑
  (link is locked by const — but the content inside heap can change)
```

> `const` locks the **link** between `data` and the object in heap memory. Since we are only changing the **value inside** the object (not the link itself), this is perfectly valid.

---

## 💻 Example 3 — Modifying Elements Inside a `const` Array

```js
const array = [10, 20, 30];
console.log(array); // [10, 20, 30]

array[0] = 20;      // ✅ Allowed — modifying an element inside the array
console.log(array); // [20, 20, 30]

array = [20, 20, 20]; // ❌ TypeError: Assignment to constant variable.
                       // Re-assigning changes the link — not allowed!
```

**Why is `array[0] = 20` allowed but `array = [...]` not?**

```
✅ array[0] = 20        → modifies the content inside heap  → link unchanged → OK
❌ array = [20, 20, 20] → points to a brand new array       → link changed   → NOT OK
```

---

## 📝 Key Takeaway

> You **can** modify the contents of a `const` object or array.
> You **cannot** re-link a `const` variable to point to a completely new value or reference.
