# 🧪 Array Practice

> A JavaScript array is an **object** — and objects are always stored in **Heap Memory**.
> The variable holding the array is a **reference variable** that points to the array in the heap.

---

## 🔤 Working with a String Array

```js
let names = [`Jatin`, `Raj`, `Ritu`];

console.log(names);    // ['Jatin', 'Raj', 'Ritu']
console.log(names[0]); // 'Jatin'
console.log(names[1]); // 'Raj'
```

### Iterating with a `for` loop

```js
for (let index = 0; index < names.length; index++) {
    console.log(names[index]);
}
```

### Iterating with `for...of` — gives **values**

```js
console.log("-".repeat(20));

for (let x of names) {   // equivalent to Java's  for (String name : names)
    console.log(x);       // Jatin, Raj, Ritu
}
```

### Iterating with `for...in` — gives **keys (indices)**

```js
console.log("-".repeat(30));

for (let z in names) {    // always gives the key!
    console.log(z);        // 0, 1, 2  ← these are the index keys
}
```

### Accessing by String Key

```js
console.log("-".repeat(30));
console.log(names["0"]); // 'Jatin' ← arrays are objects, so string keys work too
```

---

## 🛠️ Variations in Creating Arrays

### `Array.of()` — Create an Array from Specific Values

```js
let marks = Array.of(3, 5, 10); // stores these exact values → [3, 5, 10]

console.log(marks.length); // 3
console.log(marks);        // [3, 5, 10]
```

### `new Array(n)` — Create a Sparse Array of a Given Size

```js
console.log("-".repeat(30));

let data = new Array(5);       // creates 5 empty slots — no actual values

console.log(data);             // [ <5 empty items> ]
console.log(data[0]);          // undefined
console.log(data[1]);          // undefined
console.log(data[2]);          // undefined
console.log(data[3]);          // undefined
console.log(data[4]);          // undefined
console.log(data.length);      // 5
console.log(data[104]);        // undefined ← out-of-range also returns undefined, no error
```

### `Array.from()` — Create an Array from an Iterable

> `Array.from()` works on **strings** (and other iterables). It does **not** work on plain numbers.
> This is similar to Java's `String.toCharArray()`.

```js
let demo1 = Array.from(`Jatin`);
console.log(demo1); // ['J', 'a', 't', 'i', 'n']  ✅

let demo2 = Array.from(10);
console.log(demo2); // []  ← 10 is not iterable, so an empty array is returned
```

---

## 📊 Loop Comparison on Arrays

| Loop | What It Gives | Example Output on `['Jatin', 'Raj', 'Ritu']` |
|---|---|---|
| `for` | Values via index | `'Jatin'`, `'Raj'`, `'Ritu'` |
| `for...of` | Values directly | `'Jatin'`, `'Raj'`, `'Ritu'` |
| `for...in` | Keys (indices) | `0`, `1`, `2` |
