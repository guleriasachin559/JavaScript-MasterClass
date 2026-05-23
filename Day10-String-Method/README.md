# 🔧 String Methods in JavaScript

> Primitive string values in JavaScript are stored in **Heap Memory** and can be created using single quotes `' '`, double quotes `" "`, or backticks `` ` ` ``.

```js
let fname    = `jatin`;
let x        = `jatin`;
let emailId  = `sachinguleria556@gmail.com`;
```

---

## 📏 `.length` — Get the Length of a String

> `.length` is a **property**, not a method — it returns the total number of characters in the string.

```js
console.log(emailId.length); // 26
```

---

## 🔠 `.toUpperCase()` — Convert to Uppercase

> Creates and returns a **new string** in all uppercase. The original string is not modified.

```js
let data = emailId.toUpperCase();
console.log(data); // SACHINGULERIA556@GMAIL.COM
```

---

## 🔡 `.toLowerCase()` — Convert to Lowercase

> Creates and returns a **new string** in all lowercase.

```js
let lowerCaseData = emailId.toLowerCase();
console.log(lowerCaseData); // sachinguleria556@gmail.com
```

---

## ✂️ `.trim()` — Remove Leading & Trailing Whitespace

> Removes all **leading** (start) and **trailing** (end) white spaces from a string.

```js
let x       = `       HELLO      `;
let trimmed = x.trim();
console.log(trimmed); // "HELLO"
```

---

## 🔍 `.includes()` — Check if a Substring Exists

> Returns `true` if the given substring is found inside the string, otherwise `false`.

```js
console.log(emailId.includes('@')); // true  ✅
```

---

## 📍 `.indexOf()` — Find the Position of a Character

> Returns the **index** (position) of the first occurrence of the given character or substring. Returns `-1` if not found.

```js
console.log(emailId.indexOf('g')); // 6
```

---

## 🚀 `.startsWith()` — Check the Beginning of a String

> Returns `true` if the string **starts with** the given substring.

```js
console.log(emailId.startsWith('sachin')); // true  ✅
```

---

## 🏁 `.endsWith()` — Check the End of a String

> Returns `true` if the string **ends with** the given substring.

```js
console.log(emailId.endsWith('gmail.com')); // true  ✅
```

---

## ✂️ `.slice()` vs `.substring()` — Extract a Portion of a String

Both methods extract a part of a string using a **start** and **end** index (end index is **not** included).

```js
let username  = emailId.slice(0, 5);      // characters at index 0 → 4
let user_name = emailId.substring(0, 5);  // characters at index 0 → 4

console.log(username);  // sachin... (first 5 characters)
console.log(user_name); // sachin... (same result)
```

| Method | Supports Negative Index? |
|---|---|
| `.slice()` | ✅ Yes — counts from the end of the string |
| `.substring()` | ❌ No — negative values are treated as `0` |

---

## 🔄 `.replace()` & `.replaceAll()` — Replace Occurrences

### `.replace()` — Replaces the **first** occurrence only

```js
let newResult = emailId.replace('sachin', 'Raj');
console.log(newResult); // rajguleria556@gmail.com
```

### `.replaceAll()` — Replaces **all** occurrences

```js
let allReplaced = emailId.replaceAll('5', '9');
console.log(allReplaced); // sachinguleria996@gmail.com
```
