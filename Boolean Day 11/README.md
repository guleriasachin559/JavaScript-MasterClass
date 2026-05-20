# ✅ Boolean in JavaScript

```js
let isActive  = true;
let isPresent = false;

console.log(isActive);         // true
console.log(typeof isActive);  // "boolean"
```

---

## 🔄 Booleans & Type Coercion

Booleans are most commonly used in `if` conditions and loops. However, JavaScript goes a step further — it can **forcefully convert any value into a boolean** through a process called **Type Coercion**.

```js
if ("Jatin") {            // String → boolean (non-empty string = true)
    console.log("Hello"); // "Hello" ✅ — this block executes
}
```

> Whenever a non-boolean value appears in a condition, JavaScript automatically coerces it into `true` or `false`.

---

## ❌ Falsy Values — 8 Total

The following values are the **only falsy values** in JavaScript — everything else is truthy:

| Value | Description |
|---|---|
| `false` | The boolean false |
| `0` | Zero |
| `-0` | Negative zero |
| `0n` | BigInt zero |
| `""` | Empty string *(no characters at all)* |
| `null` | Intentional absence of value |
| `undefined` | Variable declared but not assigned |
| `NaN` | Not a Number |

> ⚠️ **Important distinction:**
> - `''` → **empty string** — **falsy** ❌
> - `' '` → **a string with a space** — **truthy** ✅ (it is not empty)

---

## ✅ Truthy Values

> Everything that is **not** in the falsy list above is **truthy** — including some that may surprise you:

| Value | Truthy? |
|---|---|
| `[]` — Empty array | ✅ Yes |
| `{}` — Empty object | ✅ Yes |
| `[1, 2, 3]` — Non-empty array | ✅ Yes |
| `{ name: "Jatin" }` — Non-empty object | ✅ Yes |

```js
if ({}) {
    console.log("Hello"); // ✅ executes — empty object is truthy!
}
```

---

## 🔧 `Boolean()` Method

> Use `Boolean()` to explicitly convert any value to its boolean equivalent.

```js
console.log(Boolean(1));    // true  ✅
console.log(Boolean(0));    // false ❌
```

---

## ⚡ Double NOT `!!` — Quick Boolean Conversion

> The `!!` (double negation) operator is a shorthand way to convert any value to its boolean equivalent.

**How it works:**
- `!value` → negates the value (converts to boolean, then flips it)
- `!!value` → negates twice → gives you back the **true boolean representation**

```js
console.log(!!"jatin"); // true  ✅ (non-empty string is truthy)
console.log(!!0);       // false ❌ (0 is falsy)

console.log(`*`.repeat(30)); // ****************************** (utility example)
```
