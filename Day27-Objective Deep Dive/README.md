# 🔬 Object Deep Dive — 4 Ways to Create Objects

---

## 1️⃣ Object Literal *(Most Common)*

```js
let userData = {
    username: 'Jatin'
};
console.log(userData); // { username: 'Jatin' }
```

---

## 2️⃣ `new Object()` Constructor *(Rarely Used)*

> Functionally identical to an object literal `{}`. Almost no one uses this in practice.

```js
// Create an empty object
let data = new Object();
console.log(data); // {}

// Add properties dynamically after creation
data.name = 'Raj';
console.log(data); // { name: 'Raj' }
```

---

## 3️⃣ `Object.create()` — Create with a Prototype

> Creates a new object and sets its **prototype** to the object passed in. If `null` is passed, the new object has **no prototype** at all.

### With `null` prototype

```js
let student = Object.create(null); // no prototype chain
student.name = 'Ritu';
console.log(student); // [Object: null prototype] { name: 'Ritu' }
```

### With an existing object as prototype

```js
let student = Object.create(userData); // userData becomes the prototype
student.name = 'Ritu';

console.log(student);                       // { name: 'Ritu' }  ← own properties only
console.log(Object.getPrototypeOf(student)); // { username: 'Jatin' }  ← prototype (userData)
console.log(student.username);              // 'Jatin'  ← inherited from prototype
```

> `student.username` returns `'Jatin'` because JavaScript looks up the **prototype chain** when a property is not found directly on the object.

### Modifying and Deleting Properties

```js
student.name = 'Raj';
console.log(student.name); // 'Raj'  ← own property updated

delete student.name;
console.log(student); // {}  ← own property removed; prototype is untouched

console.log(student.hasOwnProperty('name'));  // false  ← deleted
console.log(student.hasOwnProperty('marks')); // false  ← never existed
```

> `hasOwnProperty()` checks if a property belongs directly to the object — it does **not** look up the prototype chain.

> 💡 **Note:** Reserved keywords (like `class`, `for`, `if`) are allowed as object keys in JavaScript.

---

## 4️⃣ `class` Constructor *(ES6 — Object-Oriented Style)*

> A `class` in JavaScript is a blueprint for creating objects. The `constructor` method runs automatically when a new instance is created with `new`.

```js
class User {
    constructor(name, age, contactNumber) {
        this.name          = name;          // 'this' refers to the new instance
        this.age           = age;
        this.contactNumber = contactNumber;
    }
}
```

### All arguments provided

```js
let studentRef = new User("Jatin", 35, "8527252412");
console.log(studentRef);
// User { name: 'Jatin', age: 35, contactNumber: '8527252412' }
```

### Missing arguments default to `undefined`

```js
let studentRef2 = new User("Jatin");
console.log(studentRef2);
// User { name: 'Jatin', age: undefined, contactNumber: undefined }
```

---

## 📊 4 Ways to Create Objects — Quick Reference

| Method | Syntax | When to Use |
|---|---|---|
| Object Literal | `let obj = { key: value }` | Default choice — simple and readable |
| `new Object()` | `let obj = new Object()` | Rarely used — equivalent to literal |
| `Object.create()` | `Object.create(proto)` | When you need explicit prototype control |
| `class` Constructor | `new ClassName(args)` | Object-oriented design with multiple instances |
