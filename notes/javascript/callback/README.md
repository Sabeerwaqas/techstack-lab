# ✅ What is a Callback Function?

A **callback function** is a function that is passed as an argument to another function, which is then called (or invoked) later after the main task completes.

> “Hey function A, here’s function B. Call B when you’re done.”

---

## 🧠 Real-World Analogy

You order a pizza and give them your number. When the pizza is ready, they call you back.  
That’s a **callback** in action!

---

## 💡 Basic Example

```javascript
function fetchUserData(callback) {
  setTimeout(() => {
    const user = { name: "Sabeer", age: 25 };
    callback(user);
  }, 1000);
}

function showUser(user) {
  console.log("User Info:", user);
}

fetchUserData(showUser);
```
🧩 Inversion of Control (Technical)
-
Inversion of Control (IoC) happens when you give control over your function to another piece of code (e.g., library, framework, API).
You don't control when, how, or even if your callback is called.

```
someLibrary.onComplete(() => {
  console.log("Callback executed!");
});
```
🧠 This can lead to:

❓ Unpredictable execution

🔁 Multiple invocations

❌ Lost callbacks (never called)

## ✅ Pros of Callbacks

| Feature            | Description                                      |
|--------------------|--------------------------------------------------|
| ✅ Simple to use    | Easy to understand and implement.                |
| ✅ Async Friendly   | Suitable for async tasks like API calls.         |
| ✅ Reusable Logic   | Functions become more flexible and dynamic.      |


## ❌ Cons of Callbacks (with Examples)

### ❌ 1. Callback Hell (Poor Readability & Nested Code)

| Problem         | Description                                                                 |
|-----------------|-----------------------------------------------------------------------------|
| Callback Hell   | When callbacks are deeply nested, your code becomes messy and hard to maintain. |


```

function loginUser(username, callback) {
  setTimeout(() => {
    callback({ id: 1, username });
  }, 500);
}

function getUserProfile(userId, callback) {
  setTimeout(() => {
    callback({ id: userId, role: "Admin" });
  }, 500);
}

function getProfileStats(profileId, callback) {
  setTimeout(() => {
    callback({ views: 1000, likes: 200 });
  }, 500);
}

// 👇 This is Callback Hell
loginUser("sabeer", (user) => {
  getUserProfile(user.id, (profile) => {
    getProfileStats(profile.id, (stats) => {
      console.log("Stats:", stats);
    });
  });
});
❌ Problem: Difficult to read, debug, or maintain.
```

❌ 2. Complex Error Handling
-
Handling errors across multiple callbacks creates repetitive code and hard-to-follow logic.

```
function readFile(filename, callback) {
  setTimeout(() => {
    if (filename !== "file.txt") {
      return callback(new Error("File not found"), null);
    }
    callback(null, "name=Sabeer");
  }, 500);
}

function parseData(data, callback) {
  setTimeout(() => {
    if (!data.includes("=")) {
      return callback(new Error("Invalid format"), null);
    }
    const parsed = Object.fromEntries([data.split("=")]);
    callback(null, parsed);
  }, 500);
}

function process(data) {
  console.log("Processed Data:", data);
}

// 👇 Error handling is repetitive at each level
readFile("file.txt", (err, data) => {
  if (err) return console.error("Read error:", err.message);

  parseData(data, (err, parsed) => {
    if (err) return console.error("Parse error:", err.message);

    process(parsed);
  });
});
❌ Problem: Hard to centralize error handling. No clean try/catch.
```

❓ Why Callbacks Are Replaced in Modern JavaScript
-
JavaScript introduced Promises and async/await to fix the limitations of callbacks.

| Feature         | Callback Hell 😵         | Promise / Async-Await 😊     |
|-----------------|---------------------------|-------------------------------|
| Readability     | 😵 Poor                    | 😌 Great                      |
| Error Handling  | 😖 Messy                   | 😎 `try...catch` support      |
| Control Flow    | 😫 Nested (Pyramid code)   | 😊 Sequential & Clean         |

## 📚 Recommended Reading

- [Asynchronous Programming](../asynchronous-programming//README.md)  
- [Promises](../promises/README.md)  
- [Async/Await](../async-await/Readme.md)
