# 🧰 Array Methods in JavaScript

---

## 1️⃣ `push()` — Append to the End

> Adds one or more elements to the **end** of an array. Returns the **new length** of the array.

```js
const cart = ["apple", "banana"];
const len = cart.push("cherry", "date"); // ✅ use () not []

console.log(cart); // ["apple", "banana", "cherry", "date"]
console.log(len);  // 4  ← the new length, not the array
```

> 💡 **Interview Note:** `push()` returns the **new length**, NOT the array itself — a common interview trap.

### Practice Example

```js
let names = [`Katrina`, `Alia`, `Deepika`];

console.log(names.length); // 3
console.log(names);        // ['Katrina', 'Alia', 'Deepika']
console.log(names["0"]);   // 'Katrina'
console.log(names["3"]);   // undefined ← index doesn't exist yet

// Adding with push()
let length = names.push(`Ranbir`);
console.log(names);   // ['Katrina', 'Alia', 'Deepika', 'Ranbir']
console.log(length);  // 4

// Adding directly by index
names["4"] = 'Jatin';
console.log(names); // ['Katrina', 'Alia', 'Deepika', 'Ranbir', 'Jatin']

// Skipping indices — creates a sparse array
names[7] = "Raj";
console.log(names); // ['Katrina', 'Alia', 'Deepika', 'Ranbir', 'Jatin', <2 empty>, 'Raj']

// Sparse array with an empty array
let data = [];
console.log(data.length); // 0

data[1000] = "Jatin";
console.log(data);    // [ <1000 empty items>, 'Jatin' ]
console.log(data[0]); // undefined ← empty slots return undefined
```

---

## 2️⃣ `pop()` — Remove from the End

> Removes and returns the **last** element of the array. Works as the counterpart to `push()` — together they implement a **LIFO (Last In, First Out)** stack.

```js
let names = ["Raj", "Uday", "Sourav"];

let removed = names.pop();
console.log(names);   // ["Raj", "Uday"]
console.log(removed); // "Sourav"

removed = names.pop();
console.log(names);   // ["Raj"]
console.log(removed); // "Uday"

removed = names.pop();
console.log(names);   // []
console.log(removed); // "Raj"

removed = names.pop(); // ⚠️ popping from an empty array
console.log(names);   // []
console.log(removed); // undefined
```

---

## 3️⃣ `shift()` — Remove from the Start

> Removes and returns the **first** element of the array. All remaining elements shift one position to the left.

```js
let queue = ["t1", "t2", "t3"];
const next = queue.shift();

console.log(queue); // ["t2", "t3"]
console.log(next);  // "t1"

let data = [10, 20, 30];
let firstElement = data.shift();

console.log(data);         // [20, 30]
console.log(firstElement); // 10
```

---

## 4️⃣ `unshift()` — Add to the Start

> Adds one or more elements to the **start** of the array. Returns the **new length**. Works as the counterpart to `shift()` — together they implement a **FIFO (First In, First Out)** queue.

```js
const news = ["old"];
const len = news.unshift("breaking", "latest");

console.log(news); // ["breaking", "latest", "old"]
console.log(len);  // 3

// Continuing from the shift() example above (data = [20, 30])
let newLength = data.unshift(100, 200, 300);

console.log(data);      // [100, 200, 300, 20, 30]
console.log(newLength); // 5
```

---

## 5️⃣ `includes()` — Check if a Value Exists

> Returns `true` if the value is found in the array, `false` otherwise. Uses **SameValueZero** comparison.

```js
let data = [10, 20, 30];

console.log(data.includes(20));  // true  ✅
console.log(data.includes(-11)); // false ❌
```

> 💡 **Interview Note:** Unlike `indexOf()`, `includes()` correctly treats `NaN` as equal to `NaN`.

```js
let arr = [NaN];
console.log(arr.includes(NaN));   // true  ✅ — includes handles NaN correctly
console.log(arr.indexOf(NaN));    // -1    ❌ — indexOf cannot find NaN
```

---

## 6️⃣ `indexOf()` — Find the Position of a Value

> Returns the **index** of the first occurrence of the value, or `-1` if not found.

```js
let data = [10, 20, 30, 20];

console.log(data.indexOf(20));  // 1  ← first occurrence
console.log(data.indexOf(99));  // -1 ← not found
```

---

## 📊 Quick Reference

| Method | Action | Returns |
|---|---|---|
| `push(...items)` | Add to **end** | New length |
| `pop()` | Remove from **end** | Removed element |
| `unshift(...items)` | Add to **start** | New length |
| `shift()` | Remove from **start** | Removed element |
| `includes(value)` | Check if value exists | `true` / `false` |
| `indexOf(value)` | Find position of value | Index or `-1` |
