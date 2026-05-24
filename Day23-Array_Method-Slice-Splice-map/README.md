# 🧰 Array Methods — Part 3

---

## 1️⃣ `slice()` — Extract a Portion (Non-Mutating)

> Returns a **shallow copy** of a portion of the array from `start` to `end` (end index **not** included). Does **not** mutate the original.

```js
const a = ["a", "b", "c", "d", "e"];

console.log(a.slice(1, 4)); // ["b", "c", "d"]  ← indices 1, 2, 3 (4 excluded)
console.log(a.slice(-2));   // ["d", "e"]        ← last 2 elements
console.log(a);             // ["a","b","c","d","e"]  ✅ — original unchanged
```

### Practice Examples

```js
let names = ['Jatin', 'Anu', 'Rahul'];

let result = names.slice(0, 2);  // indices 0 and 1 only (2 is excluded)
console.log(result); // ['Jatin', 'Anu']
console.log(names);  // ['Jatin', 'Anu', 'Rahul']  ✅ — unchanged

result = names.slice(0, 4);  // end index exceeds array length — no error, no undefined
console.log(result); // ['Jatin', 'Anu', 'Rahul']

result = names.slice(-1);    // last 1 element
console.log(result); // ['Rahul']

result = names.slice(0);     // start from 0 → copies the entire array
console.log(result); // ['Jatin', 'Anu', 'Rahul']
```

> 💡 **Interview Note:** `slice()` **never mutates**. Confusing `slice()` with `splice()` is one of the most common interview mistakes — they sound similar but behave very differently.

---

## 2️⃣ `splice()` — Remove, Insert, or Replace In Place (Mutating)

> Removes, inserts, or replaces elements **in place**. Returns an array of the **removed elements**. ⚠️ Mutates the original array.

**Syntax:** `splice(startIndex, deleteCount, ...itemsToInsert)`

### Remove

```js
const arr = ["a", "b", "c", "d"];
const removed = arr.splice(1, 2); // start at index 1, remove 2 items

console.log(removed); // ["b", "c"]
console.log(arr);     // ["a", "d"]  ⚠️ — original is mutated
```

### Insert (no deletion)

```js
arr.splice(1, 0, "x", "y"); // start at index 1, delete 0, insert "x" and "y"

console.log(arr); // ["a", "x", "y", "d"]
```

### Replace

```js
arr.splice(2, 1, "Z"); // start at index 2, remove 1, insert "Z" in its place

console.log(arr); // ["a", "x", "Z", "d"]
```

---

## 3️⃣ `map()` — Transform Every Element into a New Array

> Returns a **new array** of the same length, where each element is the result of applying a callback function to the original element. Does **not** mutate the original.

### Transforming Strings

```js
let names = ['Jatin', 'Anu', 'Rahul', 'Raj'];

let result = names.map(function(value) {
    return value.toUpperCase();
});

console.log(result); // ['JATIN', 'ANU', 'RAHUL', 'RAJ']
console.log(names);  // ['Jatin', 'Anu', 'Rahul', 'Raj']  ✅ — original unchanged
```

### Transforming Numbers (Arrow Function)

```js
let numbers = [10, 30, 44, 55];
let resultNumbers = numbers.map((value) => value / 2);

console.log(resultNumbers); // [5, 15, 22, 27.5]
console.log(numbers);       // [10, 30, 44, 55]  ✅ — original unchanged
```

---

## 📊 Quick Reference

| Method | Mutates Original? | Returns |
|---|---|---|
| `slice(start, end)` | ❌ No | A new shallow-copied sub-array |
| `splice(start, deleteCount, ...items)` | ✅ Yes | Array of removed elements |
| `map(callback)` | ❌ No | A new transformed array (same length) |
