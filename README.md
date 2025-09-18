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


Perfect 👍 let’s expand your toolkit with a **Bonus JavaScript pamphlet**.
This isn’t mandatory before React, but it makes you a **stronger React developer** because you’ll understand *why* things behave a certain way.

---

# 📘 JavaScript for React – Bonus Concepts

These are **extra JS skills** that will help you when React code gets more advanced.

---

## 🟣 1. ES6 Classes

React used to rely on **class components** (now mostly replaced by functional components + hooks). Still good to know.

```js
class Person {
  constructor(name) {
    this.name = name;
  }

  greet() {
    return `Hello, my name is ${this.name}`;
  }
}

const amir = new Person("Amir");
console.log(amir.greet()); // "Hello, my name is Amir"
```

React example (old style):

```js
class Welcome extends React.Component {
  render() {
    return <h1>Hello {this.props.name}</h1>;
  }
}
```

---

## 🟣 2. JavaScript Event Loop

This explains **why async code works the way it does**.

* **Call Stack** → runs synchronous code first.
* **Task Queue / Callback Queue** → holds async callbacks.
* **Event Loop** → pushes async tasks into the stack when it’s free.

```js
console.log("Start");

setTimeout(() => {
  console.log("Timeout");
}, 0);

console.log("End");

// Output: Start → End → Timeout
```

Even with `0ms`, async tasks wait until the stack is clear.

---

## 🟣 3. `this` Keyword

`this` can confuse beginners. Arrow functions help because they **don’t change `this`**.

```js
const obj = {
  name: "Amir",
  normal: function () {
    console.log(this.name);
  },
  arrow: () => {
    console.log(this.name); // undefined, takes from outer scope
  }
};

obj.normal(); // Amir
obj.arrow();  // undefined
```

In React:

* Class methods often need `.bind(this)`
* Functional components (with hooks) avoid this problem

---

## 🟣 4. Closures

A closure = function that remembers its scope even when called later.
React uses closures in hooks (`useState`, `useEffect`).

```js
function counter() {
  let count = 0;
  return function () {
    count++;
    return count;
  };
}

const myCounter = counter();
console.log(myCounter()); // 1
console.log(myCounter()); // 2
```

---

## 🟣 5. Optional Chaining & Nullish Coalescing

Safe way to access nested data.

```js
const user = { profile: { city: "Toronto" } };

console.log(user?.profile?.city); // Toronto
console.log(user?.account?.email); // undefined

const email = user?.account?.email ?? "not provided";
console.log(email); // "not provided"
```

---

## 🟣 6. TypeScript Basics (Optional, but highly recommended for React jobs)

TypeScript = JavaScript with **types**.
It prevents silly bugs and makes React code easier to maintain.

```ts
function add(a: number, b: number): number {
  return a + b;
}

let username: string = "Amir";
```

In React:

```tsx
type Props = { name: string };

const Welcome: React.FC<Props> = ({ name }) => <h1>Hello {name}</h1>;
```

---

# ✅ Bonus Checklist

* [ ] ES6 Classes
* [ ] Event Loop & Async Behavior
* [ ] `this` keyword & arrow functions
* [ ] Closures (functions with memory)
* [ ] Optional chaining (`?.`) & nullish coalescing (`??`)
* [ ] TypeScript basics (if aiming for jobs/projects using it)

---

📌 These aren’t required to *start* React, but knowing them will make you feel **much less lost** when advanced React tutorials, job interviews, or older codebases come up.

---
