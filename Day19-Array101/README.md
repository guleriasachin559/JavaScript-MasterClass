# 📦 Arrays 101

---

## ☕ What is an Array in Java?

> An array is a **data structure** that stores similar kinds of values in **consecutive memory locations**.

```java
int[] number = new int[5];                    // Size 5, zero-filled → [0, 0, 0, 0, 0]
int[] marks  = {78, 84, 91, 66, 72};          // Array literal
String[] names = new String[]{"Asha", "Ravi"};
int[][] matrix = new int[3][2];               // 2D array
```

> `a` in `int a[] = new int[3]` is a **reference variable** — it points to the array object created in **heap memory**.

---

## 5️⃣ Five Things to Remember About Java Arrays

| # | Characteristic | Detail |
|---|---|---|
| 1 | **Fixed Size** | Allocated once — cannot grow or shrink |
| 2 | **Homogeneous** | All elements must share the same declared type |
| 3 | **Heap-allocated** | The array object always lives in heap memory |
| 4 | **Default values** | `int → 0`, `boolean → false`, `Object → null` |
| 5 | **Bounds-checked** | Out-of-range index throws `ArrayIndexOutOfBoundsException` at runtime |

---

## 🌐 What is an Array in JavaScript?

> A JavaScript array is an **ordered collection of values** that can **grow, shrink, and hold any mix of types** — making it **heterogeneous** by nature.

The same array can hold a string, a number, a boolean, an object, and another array — all at once.

---

## 🛠️ 4 Ways to Create a JavaScript Array

```js
const marks = [78, 84, 91, 66, 72]; // Array literal — most common
const empty = [];                    // Empty array, grow later with push()
const demo1 = new Array(5);          // Length 5, sparse (no actual values)
const demo2 = Array.of(5);           // [5] — creates an array containing the value 5
const demo3 = Array.from("hello");   // Works on strings → ['h', 'e', 'l', 'l', 'o']
```

### Heterogeneous Array in Action

```js
const profile = ["Jatin", 32, true, { role: "SDET" }, [10, 20, 30]];

console.log(profile[0]);       // "Jatin"
console.log(profile[3].role);  // "SDET"  ← nested object access
console.log(profile[4][1]);    // 20       ← nested array access
console.log(profile.length);   // 5
```

### Adding a New Element

```js
profile.push("new");
console.log(profile.length);   // 6  ← no reallocation needed, it grows automatically
```

---

### 📝 Key Rules to Remember

1. A JavaScript array can hold **any mix of types** simultaneously.
2. **Length is automatic** — you never declare the size upfront.
3. **Indexes start at 0**, same as Java.

---

## ⚡ Key Characteristics of JavaScript Arrays

| Characteristic | Description |
|---|---|
| **Dynamic Size** | Grows with `push()`, shrinks with `pop()` — no manual reallocation |
| **Heterogeneous** | Can hold strings, numbers, booleans, objects, functions, and nested arrays together |
| **Object Under the Hood** | An array is an object with numeric keys and a `length` property (`typeof [] === "object"`) |
| **Silent on Out-of-Range** | `arr[999]` returns `undefined` instead of throwing an error |
| **Rich Method Library** | `map`, `filter`, `reduce`, `find`, `some`, `every`, `flat`, and many more |

---

## 📊 Java Array vs JavaScript Array — Side by Side

| Feature | Java | JavaScript |
|---|---|---|
| Size | Fixed at creation | Dynamic — grows and shrinks |
| Types allowed | Homogeneous (one type) | Heterogeneous (any mix) |
| Out-of-range access | Throws exception | Returns `undefined` |
| Default values | Yes (`0`, `false`, `null`) | `undefined` |
| Memory location | Heap | Heap |
