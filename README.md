# js-essentials-for-React-js

Got it 👍
Here’s a **Markdown pamphlet** you can keep as your JavaScript “cheat sheet” for React prep.
You could save this as `javascript-for-react.md` in your notes repo.

---

# 📘 JavaScript for React – Quick Learning Pamphlet

This guide covers **all the JavaScript you must know** before learning React.

---

## 🟢 1. Variables & Scope

```js
const pi = 3.14;   // constant (cannot be reassigned)
let count = 0;     // block-scoped, can change
count = count + 1;
```

* Prefer `const` by default
* Use `let` when the value changes
* Avoid `var` (old, function-scoped)

---

## 🟢 2. Functions

### Normal vs Arrow

```js
function add(a, b) {
  return a + b;
}

const add2 = (a, b) => a + b;
```

### Default Parameters

```js
const greet = (name = "Guest") => `Hello, ${name}`;
```

---

## 🟢 3. Strings – Template Literals

Like Python f-strings:

```js
const name = "Amir";
console.log(`Hello, ${name}!`);
```

---

## 🟢 4. Objects & Arrays

### Destructuring

```js
const user = { name: "Amir", city: "Toronto" };
const { name, city } = user;
```

### Spread & Rest

```js
const nums = [1, 2, 3];
const newNums = [...nums, 4, 5];   // spread
const sum = (...args) => args.reduce((a, b) => a + b, 0);  // rest
```

---

## 🟢 5. Arrays – Useful Methods

```js
const nums = [1, 2, 3, 4];

// map → transform each item
const doubled = nums.map(n => n * 2);

// filter → keep matching items
const evens = nums.filter(n => n % 2 === 0);

// reduce → accumulate
const total = nums.reduce((acc, n) => acc + n, 0);
```

---

## 🟢 6. Control Flow

```js
if (x > 10) {
  console.log("big");
} else {
  console.log("small");
}

for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

---

## 🟢 7. Modules

Like Python imports.

```js
// math.js
export const add = (a, b) => a + b;

// app.js
import { add } from "./math.js";
console.log(add(2, 3));
```

---

## 🟢 8. Async JavaScript

### Promises

```js
fetch("https://jsonplaceholder.typicode.com/todos/1")
  .then(res => res.json())
  .then(data => console.log(data));
```

### Async/Await

```js
async function getTodo() {
  const res = await fetch("https://jsonplaceholder.typicode.com/todos/1");
  const data = await res.json();
  console.log(data);
}
getTodo();
```

---

## 🟢 9. DOM Basics

React will replace much of this, but you should know the basics.

```js
// Select an element
const btn = document.querySelector("#myBtn");

// Add event listener
btn.addEventListener("click", () => {
  alert("Button clicked!");
});
```

---

## 🟢 10. Error Handling

```js
try {
  throw new Error("Something went wrong");
} catch (err) {
  console.error(err.message);
}
```

---

# ✅ Checklist Before React

* [ ] Variables: `let`, `const`
* [ ] Functions: arrow functions, default params
* [ ] Template literals
* [ ] Objects & arrays: destructuring, spread/rest
* [ ] Array methods: `map`, `filter`, `reduce`
* [ ] Control flow (`if`, `for`, `while`)
* [ ] Modules (`import` / `export`)
* [ ] Async code: Promises, `async/await`
* [ ] DOM basics (`querySelector`, events)
* [ ] Error handling (`try/catch`)

---

📌 Master these, and you’re ready to jump into **React fundamentals (JSX, components, props, state, hooks)** without getting stuck on JavaScript syntax.

---
