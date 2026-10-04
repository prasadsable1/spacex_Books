# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some Oxlint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Oxc](https://oxc.rs)
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/)

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the Oxlint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and Oxlint's TypeScript related rules in your project.




























<!-- 
## LocalStorage in JavaScript / React

`localStorage` lets you **save data in the browser** so it remains available even after refreshing or closing the browser.

It stores data as **strings**, so objects/arrays usually need `JSON.stringify()` and `JSON.parse()`.

---

### 1. Save simple value

```js
localStorage.setItem("name", "Prasad");
```

### 2. Get value

```js
const name = localStorage.getItem("name");

console.log(name);
```

Output:

```text
Prasad
```

### 3. Remove one item

```js
localStorage.removeItem("name");
```

### 4. Remove everything

```js
localStorage.clear();
```

---

# ⭐ Save Object

You **cannot directly** store an object properly.

❌ Don't do:

```js
localStorage.setItem("user", user);
```

Use:

```js
localStorage.setItem(
  "user",
  JSON.stringify(user)
);
```

Example:

```js
const user = {
  name: "Prasad",
  email: "prasad@gmail.com",
  age: 20
};

localStorage.setItem(
  "user",
  JSON.stringify(user)
);
```

---

# ⭐ Get Object

```js
const savedUser =
  JSON.parse(localStorage.getItem("user"));

console.log(savedUser.name);
console.log(savedUser.email);
```

---

# ⭐ Save Array

```js
const users = [
  {
    id: 1,
    name: "Amit"
  },
  {
    id: 2,
    name: "Rahul"
  }
];

localStorage.setItem(
  "users",
  JSON.stringify(users)
);
```

Get it:

```js
const users =
  JSON.parse(localStorage.getItem("users")) || [];

console.log(users);
```

The `|| []` is useful because `getItem()` returns `null` if the key doesn't exist.

---

# 🚀 React Example — Save Form Data

```jsx
import { useState } from "react";

function App() {

  const [name, setName] = useState("");

  function saveUser() {

    const user = {
      name: name
    };

    localStorage.setItem(
      "user",
      JSON.stringify(user)
    );

    alert("Saved!");
  }

  return (
    <div>

      <input
        value={name}
        onChange={(e) =>
          setName(e.target.value)
        }
        placeholder="Enter name"
      />

      <button onClick={saveUser}>
        Save
      </button>

    </div>
  );
}

export default App;
```

---

# ⭐ Load saved data when React starts

This is extremely useful.

```jsx
import { useState, useEffect } from "react";

function App() {

  const [name, setName] = useState("");

  useEffect(() => {

    const savedUser =
      JSON.parse(
        localStorage.getItem("user")
      );

    if (savedUser) {
      setName(savedUser.name);
    }

  }, []);

  return (
    <h1>
      Hello {name}
    </h1>
  );
}

export default App;
```

Flow:

```text
Browser
   ↓
localStorage
   ↓
getItem()
   ↓
JSON.parse()
   ↓
React state
   ↓
UI
```

---

# 🔥 Very useful: Login state

For a frontend-only competition project, you might need to remember whether a user is logged in.

### Login

```js
const user = {
  id: 1,
  name: "Prasad",
  role: "admin"
};

localStorage.setItem(
  "loggedInUser",
  JSON.stringify(user)
);
```

### Check login

```js
const user =
  JSON.parse(
    localStorage.getItem("loggedInUser")
  );

if (user) {
  console.log("Logged in");
} else {
  console.log("Not logged in");
}
```

### Logout

```js
localStorage.removeItem("loggedInUser");
```

---

# 🔥 LocalStorage + React state

A common pattern:

```jsx
const [items, setItems] = useState(() => {

  const saved =
    localStorage.getItem("items");

  return saved
    ? JSON.parse(saved)
    : [];

});
```

Then whenever items change:

```jsx
useEffect(() => {

  localStorage.setItem(
    "items",
    JSON.stringify(items)
  );

}, [items]);
```

This gives you:

```text
User action
     ↓
setItems()
     ↓
React state changes
     ↓
useEffect()
     ↓
localStorage updated
     ↓
Refresh page
     ↓
Data still exists
```

---

## ⚠️ Remember these 6 lines

```js
// Save
localStorage.setItem("key", "value");

// Get
localStorage.getItem("key");

// Remove
localStorage.removeItem("key");

// Clear
localStorage.clear();

// Object → string
JSON.stringify(object);

// String → object
JSON.parse(string);
```

**Most important exam/competition point:** `localStorage` stores **strings**, not JavaScript objects/arrays directly. -->
