# Node.js Basics

**Node.js** is a **runtime environment** that lets run **JavaScript outside the browser**. It uses the **V8 engine**. It is non-blocking, fast, and ideal for I/O-heavy apps.

---

## Non-Blocking
- When NodeJS encounters a non-blocking operation, It doesn't wait for its completion.
- Instead, it registers a callback function (or uses `promises` or `async/await`) to be executed when the operation is done.
- Meanwhile, Node.js continues to execute other parts of the program.
- This allows Node.js to handle multiple operations concurrently, improving efficiency.


## NPM (Node Package Manager)

**npm** stands for **Node Package Manager**. It is:

* The **default package manager** for **Node.js**
* Also a huge **online registry** of open-source JavaScript packages

### Useful npm Commands

| Command               | Description                      |
| --------------------- | -------------------------------- |
| `npm init -y`         | Create default `package.json`    |
| `npm install`         | Install all dependencies listed  |
| `npm uninstall <pkg>` | Remove a package                 |
| `npm update`          | Update outdated packages         |
| `npm run <script>`    | Run a script from `package.json` |

---

### What is the npm Registry?

The **npm registry** is an **online database** of packages at [https://www.npmjs.com](https://www.npmjs.com).
You can:

* Search for packages
* Read docs
* Check download stats and versions

---

## NPX (Node Package Execute)

It comes bundled with **npm (v5.2.0+)** and allows you to **run Node.js packages directly from the command line** — **without installing them globally**.

Packages run with `npx` are stored in a temporary cache. They don’t clutter your global setup.

---

## Common Built-in Modules

| Module   | Purpose                   |
| -------- | ------------------------- |
| `path`   | Handle file paths         |
| `fs`     | File system operations    |
| `os`     | System info (CPU, memory) |
| `http`   | Create web server         |
| `events` | Event emitter pattern     |
| `crypto` | Hashing, encryption       |

---