## What is `useEffect` hook?

- The `useEffect` Hook allows us to perform side effects in our components like:
  - fetching the data
  - updating the DOM directly
  - setting the timers.
- Runs after render.

### The useEffect Hook accepts two arguments:

- **A callback function:** This function contains the logic for the side effect.
- **An optional dependency array:** This array controls when the effect re-runs.
  - If the array is omitted, the effect runs after every render.
  - If an empty array [] is provided, the effect runs only once after the initial mount.
  - If an array with dependencies (e.g., `[prop1, state2]`) is provided, the effect re-runs only when any of those dependencies change between renders.

### Cleanup Function:

The cleanup function is crucial for preventing memory leaks and managing resources, such as removing event listeners or clearing timers.

The `useEffect` callback can optionally return a cleanup function. This function is executed:

- Before the effect runs again (if dependencies change).
- When the component unmounts from the DOM.

```jsx
useEffect(() => {
  console.log("Mounted");
  return () => console.log("Cleanup");
}, []);
```

## What is `useRef` hook?

- The `useRef` Hook allows us to persist values between renders.
- It can be used to store a mutable value that does not cause a re-render when updated.
- It can be used to access a DOM element directly.

```jsx
function FocusInput() {
  const inputRef = useRef(null);

  const focusInput = () => {
    if (inputRef.current) {
      inputRef.current.focus(); // Access the DOM element and call focus()
    }
  };
  return <input type="text" ref={inputRef} />;
}
```

## What is `useContext` hook?

- React Context is a way to manage state globally.
- The `useContext` hook is designed to simplify state management and avoid "prop drilling" in applications.

### How `useContext` works:

- **Create Context:** We first create a context object using `React.createContext()`. This object can optionally define a default value.
- **Provide Context:** A Provider component associated with the created context is used to wrap a part of the component tree. This Provider accepts a value prop, which is the data we want to make available to its descendants.
- **Consume Context:** In any functional component nested within the Provider, we can use the `useContext` hook to access the provided value. `useContext` takes the context object as its argument and returns the current context value from the nearest Provider above it in the component tree.
