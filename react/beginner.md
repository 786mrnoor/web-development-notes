## What is React?

- A JavaScript library for building user interfaces, based on components. Uses a **virtual DOM** for efficient rendering.

## What are components?

- Components are **reusable** piece of code that allow developers to break down complex UIs into **smaller**, **manageable**, and **independent units**.
- Components are simple JavaScript functions that accept **props** as an argument, can use react **hooks** and return **JSX**.

```jsx
function Greeting({ name }) {
  return <h1>Hello, {name}</h1>;
}
```

## What is JSX

- JSX stands for JavaScript XML.
- It is a syntax extension for JavaScript.
- It allows developers to write HTML-like code directly within their JavaScript files.
- It describe the structure and appearance of UI components.

## What are props?

- Props are arguments passed into React components.
- Props are **immutable**.

## What are hooks?

- Hooks allow components to have access to React features like state, context, refs, and lifecycle.
- **Hook Rules**
  There are 3 rules for hooks:

1. Hooks can only be called inside React function components.
1. Hooks can only be called at the top level of a component.
1. Hooks cannot be conditional.

## What is state?

- State generally refers to application data or properties that need to be tracked.
- It represents the **internal**, **mutable** data of a component.
- State is managed with `useState` Hook.
- This hook returns an array containing two elements:
  1.  The current state value.
  1.  A function to update that state which triggers re-rendering.

## Event handling

- Event handling in React refers to the process of capturing and responding to user interactions within React components.
- React events are written in camelCase syntax.
- React event handlers are written inside curly braces:
- React uses a **synthetic event system** that wraps native browser events.

## Conditional rendering

- Conditional rendering refers to the practice of dynamically displaying different content or components based on specific conditions.

## Why keys in lists?

- "lists" refer to the rendering of multiple components or elements based on a collection of data, typically an array.
- Each element in a list must have a unique `key` prop.
- Keys help React identify which items changed, added, or removed. Improves reconciliation.
- When list items are reordered or filtered, keys help React maintain the correct state of individual components by associating them with their unique identifiers.
