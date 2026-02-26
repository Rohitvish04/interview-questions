 
# React Interview Preparation (1–2 Years Experience)

For 1–2 years of React experience, interviewers expect solid fundamentals plus some real-world problem-solving. Here’s a focused **must-prepare** list with short model answers.

---

## Components, JSX, Props, State

### 1. What is React and what problem does it solve?
React is a JavaScript library for building user interfaces, focused on composing reusable components and efficiently updating the UI when data changes using a virtual DOM.

### 2. What is JSX? Can React work without it?
JSX is a syntax extension that lets you write HTML-like code inside JavaScript, which gets compiled to `React.createElement` calls. React can work without JSX by calling `React.createElement` directly, but JSX is more readable.

### 3. Difference between props and state?
- **Props**: Read-only data passed from parent to child, controlled by the parent.  
- **State**: Internal, mutable data managed by the component itself using hooks like `useState`.

### 4. Functional vs Class Components (and which do you use)?
Originally, class components handled state and lifecycle, but now functional components with hooks are preferred because they are simpler, less boilerplate, and better for reusing logic via custom hooks.

---

## Hooks: useState, useEffect, useMemo, useCallback, useRef

### 5. How does useState work?
`useState` returns a state value and an updater function. State updates are asynchronous and may be batched, so you should not rely on the immediate value after calling the setter.

```js
const [count, setCount] = useState(0);
setCount(prev => prev + 1);
````

### 6. Explain useEffect and its dependency array

`useEffect` runs side effects after render (e.g., data fetching, subscriptions, logging).

* No dependency array → runs after every render.
* `[]` → runs once after the first render.
* `[a, b]` → runs whenever `a` or `b` changes.

Return a function for cleanup (e.g., removing event listeners or cancelling requests).

### 7. Common useEffect pitfalls

* Missing dependencies → stale data or bugs.
* Including functions/objects created on every render → infinite loops.
* Doing heavy work directly inside `useEffect` without optimization or cancellation.

### 8. When do you use useMemo and useCallback?

* `useMemo` memoizes an expensive computation result.
* `useCallback` memoizes a function so its reference stays stable (useful when passing callbacks to memoized child components).

### 9. What is useRef and when do you use it?

`useRef` holds a mutable value that persists across renders without causing re-renders.
Used for:

* Accessing DOM elements
* Storing timers
* Tracking previous values

---

## Rendering, Virtual DOM, Keys, Data Flow

### 10. What is the virtual DOM?

The virtual DOM is a lightweight in-memory representation of the UI. When state changes, React computes the difference and applies minimal updates to the real DOM.

### 11. Why do we need keys in lists?

Keys help React identify which items changed, were added, or removed.
Use stable unique IDs. Avoid array indices if the list can reorder.

### 12. How does data flow in React?

React uses **one-way data flow**:

* Parent → Child via props
* Child → Parent via callback functions passed as props

---

## State Management, Lifting State, Context

### 13. What is “lifting state up”?

When multiple components need the same state, move it to their closest common ancestor and pass it down via props.

### 14. When would you use Context API?

Use Context for globally needed data like:

* Theme
* Authenticated user
* Language/locale

It helps avoid prop drilling.

### 15. When choose Redux or another state library?

Use a state library when:

* State is complex and global
* Many features depend on shared data
* You need middleware, time-travel debugging, or advanced async handling

For small apps, local state + Context is usually enough.

---

## Routing, Forms, and Events

### 16. What is React Router?

React Router is a library for client-side routing in SPAs.

Key concepts:

* `<Route>`
* `<Link>`
* `useNavigate`
* Nested routes
* Dynamic routes

### 17. Controlled vs Uncontrolled Components

* **Controlled**: Input value stored in React state (`onChange` updates state).
* **Uncontrolled**: Input value lives in the DOM, accessed via `ref`.

### 18. How to build a search input with debouncing?

* Store input in state
* Use `setTimeout` inside `useEffect`
* Clear timeout in cleanup

Custom `useDebounce` hook is a common pattern.

---

## Performance & Optimization

### 19. Why might a component re-render?

Re-renders happen when:

* State changes
* Props change
* Parent re-renders

To reduce unnecessary re-renders:

* Split into smaller components
* Use `React.memo`
* Use `useMemo` / `useCallback` when needed

### 20. How to render a very large list efficiently?

Use virtualization libraries like:

* `react-window`
* `react-virtualized`

Or implement:

* Pagination
* Infinite scrolling

---

## Error Handling & Project Structure

### 21. How to structure a medium React project?

Example structure:

```
src/
  features/
    auth/
    todos/
  shared/
    components/
    hooks/
  services/
  types/
```

Group by **feature/domain** instead of by file type only.

### 22. What is an error boundary?

An error boundary is a class-based component that:

* Catches JavaScript errors in its child tree
* Logs the error
* Shows a fallback UI instead of crashing the whole app

---

## JavaScript Fundamentals (Very Important)

### 23. var vs let vs const

* `var`: function-scoped, hoisted, can be redeclared
* `let`: block-scoped, can be reassigned
* `const`: block-scoped, cannot be reassigned

### 24. What is a closure?

A closure is when a function remembers variables from its outer scope even after the outer function has finished executing.

### 25. Promise vs async–await

* **Promise**: Represents a future value.
* **async/await**: Syntactic sugar over promises that makes async code look synchronous.

---

# Quick Practice Plan (1–2 Years Level)

You should be able to:

* Build a small CRUD app with routing and forms
* Use `useState`, `useEffect`, `useMemo`, `useCallback`, `useRef`, Context confidently
* Explain why something re-renders
* Debug performance issues
* Discuss real bugs you fixed and how you solved them

---

If you'd like, share a recent React project and I can convert this into personalized interview answers tailored to your experience.

```
```
