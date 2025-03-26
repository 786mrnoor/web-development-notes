# Modules

**Modules** are **reusable code**  that can be **imported** and used in other parts of a program. It **hide**(encapsulation) internal implementation details

## 1. CommonJS (CJS) Modules: 
- used in Node.js environments.
- `require()` to import modules.
- ` module.exports` or `exports` to expose them. 
- It's **synchronous**, meaning modules are loaded in the order they are required

## 2. ECMAScript Modules (ESM):
- ES Module uses `import` and `export` keywords.
-  It's **asynchronous** & work in **browsers** & **Node.js**.
- Use `import()` for dynamic imports in ES Modules.
-  Use `"type": "module"` in `package.json` to enable ES Modules in Node.js.