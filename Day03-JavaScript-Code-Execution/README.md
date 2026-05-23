# ⚙️ What is an Execution Context?

> All JavaScript code is executed **inside an Execution Context**.

---

# 🌍 What is the Global Execution Context?

> The very **first** Execution Context created when a JS program runs is called the **Global Execution Context**.

---

## 🧩 Components of the Global / Function Execution Context

Every Execution Context consists of **two components:**

### 1. 🧠 Memory Component *(also called the Variable Environment)*

- Stores all **variables** and **functions** as **key-value pairs**
- Memory is allocated **before** the code starts executing

```
Key        Value
─────────────────────────────────────────────────
add     →  { entire function body }
count   →  10
```

> Both variables and functions are stored here. Functions store their **entire body** as the value.

---

### 2. ▶️ Code Component *(also called the Thread of Execution)*

- Executes the code **line by line**, in order
- Any time a **function is invoked**, a brand new **Function Execution Context** is created for it

---

## 🔧 Components of a Function Execution Context

When a function is called, its own Execution Context is created with the same two components:

### Phase 1 — Memory Allocation

All local variables are initialized with `undefined` first:

```
h1: undefined
h2: undefined
```

### Phase 2 — Code Execution

As the code runs line by line, the actual values replace `undefined`:

```
h1: 10
h2: 20
```

> ✅ Once the function finishes executing, its **Execution Context is destroyed**.

---

# 📚 Call Stack — Tracking Execution Contexts

To keep track of all Execution Contexts, JavaScript uses a **Call Stack**.

```
Call Stack — LIFO (Last In, First Out)

┌─────────────────────────────┐
│   Function Execution Context│  ← pushed when function is called
├─────────────────────────────┤
│   Global Execution Context  │  ← always at the bottom
└─────────────────────────────┘
```

> When a function is called → its context is **pushed** onto the stack.
> When it finishes → its context is **popped** off the stack.
