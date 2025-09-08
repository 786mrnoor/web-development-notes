## How to optimize React performance?

- Use `React.memo`, `useMemo`, `useCallback` to avoid unnecessary re-renders.
- Code splitting with `React.lazy`.

### `React.memo`

`React.memo` wraps a functional component and memoizes (caches) its rendered output. It prevents unnecessary re-renders of a component when its props have not changed.

### `useMemo`

`useMemo` is used to memoize the result of an expensive computation or value. It prevents the re-execution of a function that calculates a value unless its dependencies change.

### `useCallback`

`useCallback` is used to memoize a function definition itself. It prevents the re-creation of a function on every render, which can be beneficial when passing functions as props to child components, especially those wrapped with React.memo.

## What are error boundaries?

- Components that catch errors in children during rendering.
- Implemented using `componentDidCatch` in class components.

## What is React reconciliation?

- The process React uses to compare virtual DOM with the real DOM, and only update changed nodes (diffing algorithm).

## What is SSR (Server Side Rendering)?

- Rendering React pages on the server before sending to client → improves SEO and performance.
- Done using frameworks like **Next.js**.
