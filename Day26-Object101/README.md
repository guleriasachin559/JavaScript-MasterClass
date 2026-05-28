# 📦 Objects 101

---

## 🤔 Why Does `typeof` Array Return `"object"`?

```js
let names = ['Jatin', 'Raj', 'Rahul'];

console.log(names);         // ['Jatin', 'Raj', 'Rahul']
console.log(typeof names);  // "object"
console.log(names[0]);      // 'Jatin'
console.log(names['0']);    // 'Jatin'  ← string key also works
```

**Why?** Because in JavaScript, arrays are internally stored in heap memory as objects with string keys:

```
Heap Memory:
{
    "0"    : "Jatin",
    "1"    : "Raj",
    "2"    : "Rahul",
    length : 3
}
```

> Since JavaScript arrays have **no fixed size**, they are implemented as objects with numeric string keys — which is why `typeof []` returns `"object"`.

---

## ❓ What is an Object?

> A JavaScript object is similar to a **HashMap / Map in Java** — it stores data as **key-value pairs**.
> The key is always a **string** (or Symbol). The value can be anything: a primitive, array, function, or another object.

---

## 🛠️ Creating an Object — Object Literal (Most Common)

### Standard Key Names

```js
let user = {
    firstName : "Jatin",          // String
    age       : 35,               // Number
    isActive  : true,             // Boolean
    marks     : [75, 85, 90],     // Array
    greet: function(username) {   // Function (method)
        console.log(`Hello ${username}`);
    },
    address: {                    // Nested Object
        line1         : 'C-304',
        apartmentName : 'Jupiter',
        city          : 'Mumbai',
        pincode       : '400104',
    }
};
```

### Keys with Spaces — Use String Keys

> If a key contains a **space**, wrap it in quotes. Access it using **bracket notation** only.

```js
let user = {
    'first name': "Jatin",  // ← must use bracket notation to access
    age: 35,
};
```

### Keys with Underscores — Use Directly

```js
let user = {
    first_name: "Jatin",  // ← underscores are valid, use dot notation normally
    age: 35,
};
```

---

## 🔍 Accessing Object Properties

```js
// Entire object
console.log(user); // { firstName: 'Jatin', age: 35, ... }

// Dot notation (standard)
console.log(user.firstName); // 'Jatin'
console.log(user.age);       // 35
console.log(user.isActive);  // true

// Bracket notation (required for keys with spaces)
console.log(user['first name']); // 'Jatin'

// Accessing an array property
console.log(user.marks);      // [75, 85, 90]
console.log(user.marks[0]);   // 75
console.log(user.marks['0']); // 75  ← string index also works
// console.log(user.marks.0); // ❌ SyntaxError — cannot use dot notation for numeric index

// Calling a method
user.greet('Uday');            // Hello Uday
console.log(user.greet('Uday')); // Hello Uday → undefined  ⚠️ (the function logs but returns nothing)

// Accessing a nested object
console.log(user.address.line1); // 'C-304'

console.log(typeof user); // "object"
```

---

## 🔁 Traversing an Object

### `for...in` — Iterates Over Keys ✅

```js
for (let key in user) {
    console.log(key, ':', user[key]); // prints every key-value pair
}
```

### `for...of` — Does NOT Work on Plain Objects ❌

```js
for (let key of user) {
    console.log(key); // ❌ TypeError: user is not iterable
}
```

> `for...of` works on **iterables** (arrays, strings, Maps, Sets). Plain objects are **not iterable** — use `for...in` instead.

---

## 📊 Key vs Value Access — Quick Reference

| What you want | Syntax | Example |
|---|---|---|
| All keys | `for...in` | `for (let key in user)` |
| Value by key (dot) | `obj.key` | `user.firstName` |
| Value by key (bracket) | `obj['key']` | `user['first name']` |
| Nested object value | `obj.key.subKey` | `user.address.city` |
| Array inside object | `obj.key[index]` | `user.marks[0]` |
| Call a method | `obj.method()` | `user.greet('Uday')` |
