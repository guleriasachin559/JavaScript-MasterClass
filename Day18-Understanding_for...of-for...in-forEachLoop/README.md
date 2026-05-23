# 🔁 Advanced Loops in JavaScript

---

## 1️⃣ `for...of` Loop — Iterate over Values

> `for...of` directly gives you the **value** of each element — no index needed. It works with **arrays** and **strings**.

### Iterating an Array

```js
const data = ['Jatin', 'Uday', 'Alia', 'Deepika', 'Raj'];

// Using a traditional for loop (verbose)
for (let index = 0; index < data.length; index++) {
    console.log(data[index]);
}

// Using for...of (cleaner — preferred for arrays)
for (let username of data) {
    console.log(username);
}
```

### Iterating a String

```js
let user = 'Jatin';

// Using for...of — each character one by one
for (let character of user) {
    console.log(character); // J, a, t, i, n
}

// Equivalent with a traditional for loop
for (let index = 0; index < user.length; index++) {
    console.log(user[index]);
}
```

---

## 2️⃣ `for...in` Loop — Iterate over Keys / Indices

> `for...in` gives you the **index** (for arrays) or **key** (for objects). It is primarily used for iterating over **objects**.

### On an Array — gives indices

```js
const data = ['Jatin', 'Uday', 'Alia', 'Deepika', 'Raj'];

for (let x in data) {
    console.log(x); // 0, 1, 2, 3, 4  ← index values, not the items
}
```

### On an Object — gives keys *(primary use case)*

```js
let response = { username: 'Jatin', age: 35, city: 'Mumbai' };

for (let key in response) {
    console.log(key);                        // username, age, city
    console.log(key + " → " + response[key]); // username → Jatin, age → 35, city → Mumbai
}
```

---

## 3️⃣ `forEach` Loop — Array Method with a Callback

> `forEach` is an **array method** that runs a callback function once for each element. It provides both the **value** and the **index**.

### Basic usage — value only

```js
data.forEach(function(user) {
    console.log(user);
});
```

### With value and index

```js
data.forEach(function(user, index) {
    console.log(user + " " + index);
});
```

### With template literals *(cleaner)*

```js
data.forEach(function(user, index) {
    console.log(`${index}: ${user}`);
});
```

### Arrow function shorthand *(most concise)*

```js
// Value only
data.forEach(user => console.log(user));

// Value and index
data.forEach((user, index) => {
    console.log(user);
    console.log(index);
});
```

---

## 📊 Quick Comparison — Which Loop to Use?

| Loop | Works On | Gives You | Best Used For |
|---|---|---|---|
| `for...of` | Arrays, Strings | **Values** | Cleanly iterating array/string elements |
| `for...in` | Objects, Arrays | **Keys / Indices** | Iterating object properties |
| `forEach` | Arrays only | **Value + Index** | Array iteration with a callback function |
