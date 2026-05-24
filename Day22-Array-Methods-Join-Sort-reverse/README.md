# 🧰 Array Methods — Part 2

---

## 1️⃣ `join()` — Combine All Elements into a String

> Joins all elements of an array into a **single string**, separated by the given separator.

```js
const path = ["home", "jatin", "sdet"];

console.log(path.join("/"));  // 'home/jatin/sdet'
console.log(path.join(">"));  // 'home>jatin>sdet'

let data = [10, 20, 30];
let result = data.join('%');
console.log(result); // '10%20%30'
```

---

## 2️⃣ `reverse()` — Reverse the Array In Place

> Reverses the array **in place** (mutates the original) and returns a reference to the same array.

```js
let data = [10, 20, 30];
let data2 = data.reverse();

console.log(data2); // [30, 20, 10]
console.log(data);  // [30, 20, 10]  ⚠️ — the ORIGINAL array is also reversed!
```

> ⚠️ **Mutation warning:** `data` and `data2` point to the **same array** in memory. Reversing one reverses both.

---

## 3️⃣ Reversing Without Mutating — The Spread Operator `...`

> To reverse a copy of the array while keeping the original intact, use the **spread operator** (`...`) to create a **shallow copy** first.

```js
let names = ["Raj", "Uday", "Deepak"];

let x = [...names].reverse(); // spread creates a new array, then reverse that copy
console.log(x);     // ["Deepak", "Uday", "Raj"]
console.log(names); // ["Raj", "Uday", "Deepak"]  ✅ — original is untouched
```

### Creating a Manual Copy (without spread)

```js
let names = ['Uday', 'Deepak', 'Jatin'];
let backup = [];

for (let index = 0; index < names.length; index++) {
    backup[index] = names[index];
}

console.log(backup); // ['Uday', 'Deepak', 'Jatin']
console.log(names);  // ['Uday', 'Deepak', 'Jatin']  ✅ — original unchanged
```

> The spread operator `[...arr]` achieves the same result in a single line — always prefer it over a manual copy loop.

---

## 4️⃣ `sort()` — Sort the Array In Place

> Sorts the array **in place** (mutates the original). The **default sort order is lexicographic (dictionary order)** — not numeric.

### ⚠️ Default Sort — Lexicographic (Strings)

```js
const nums = [10, 1, 21, 2, 100];
nums.sort();
console.log(nums); // [1, 10, 100, 2, 21]  ⚠️ — sorted as strings, not numbers!
```

> JavaScript converts each element to a string and compares character by character — so `"100"` comes before `"2"` because `"1" < "2"`.

### Sorting a Copy (without mutating the original)

```js
let numberData = [1, 2, 10, 21, 100];
let numberDataCopy = [...numberData].sort();

console.log(numberDataCopy); // [1, 10, 100, 2, 21]  ← lexicographic
console.log(numberData);     // [1, 2, 10, 21, 100]  ✅ — original unchanged
```

### ✅ Numeric Sort — Ascending Order

> Pass a **comparator function** `(a, b) => a - b` to sort numerically:
> - Negative result → `a` comes first (order is correct, no swap)
> - Positive result → `b` comes first (positions are swapped)

```js
let numberData = [1, 2, 10, 21, 100];
numberData.sort((a, b) => a - b);
console.log(numberData); // [1, 2, 10, 21, 100]  ✅ — ascending numeric order
```

### ✅ Numeric Sort — Descending Order

```js
numberData.sort((a, b) => b - a);
console.log(numberData); // [100, 21, 10, 2, 1]  ✅ — descending numeric order
```

---

## 📊 Quick Reference

| Method | Mutates Original? | Returns |
|---|---|---|
| `join(separator)` | ❌ No | A single joined string |
| `reverse()` | ✅ Yes | The reversed array (same reference) |
| `[...arr].reverse()` | ❌ No | A new reversed array |
| `sort()` | ✅ Yes | The sorted array (lexicographic by default) |
| `sort((a,b) => a-b)` | ✅ Yes | The sorted array (ascending numeric) |
| `sort((a,b) => b-a)` | ✅ Yes | The sorted array (descending numeric) |
