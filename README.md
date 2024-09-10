
# Top React Interview Questions

This repository provides a collection of **React Interview Questions** to help developers prepare for React.js job interviews. The questions range from basic to advanced concepts and cover various aspects of React development, including hooks, lifecycle methods, Redux, and performance optimization.

## Table of Contents

1. [JSX](#jsx)
2. [Virtual DOM](#virtual-dom)
3. [Props vs State](#props-vs-state)
4. [useState vs useEffect](#usestate-vs-useeffect)
5. [Higher-Order Components (HOC)](#higher-order-components-hoc)
6. [useCallback vs useMemo](#usecallback-vs-usememo)
7. [Redux](#redux)
8. [Redux Thunk](#redux-thunk)
9. [Class Components vs Functional Components](#class-components-vs-functional-components)
10. [Reconciliation in React](#reconciliation-in-react)
11. [Hooks in React](#hooks-in-react)
12. [useEffect vs Lifecycle Methods](#useeffect-vs-lifecycle-methods)
13. [Limitations of the Virtual DOM](#limitations-of-the-virtual-dom)
14. [useCallback and Performance](#usecallback-and-performance)
15. [useMemo vs useCallback](#usememo-vs-usecallback)
16. [Redux vs useState](#redux-vs-usestate)
17. [Side Effects in React](#side-effects-in-react)
18. [Alternatives to Redux](#alternatives-to-redux)

---

### What is JSX, and how is it different from HTML?

JSX (JavaScript XML) is a syntax extension for JavaScript used in React. It allows developers to write HTML-like code inside JavaScript and is primarily used to structure the UI in React applications. However, JSX is not valid HTML or JavaScript, so it must be transpiled into JavaScript using tools like Babel before the browser can process it.

**Key Differences**:
- **JavaScript Logic**: JSX allows embedding JavaScript expressions inside curly braces `{}`. This means you can dynamically insert values or logic directly into the markup.
- **Strict Syntax**: Unlike HTML, JSX enforces that all elements must be properly closed, including self-closing tags like `<img />` and `<br />`.
- **Attribute Naming**: In JSX, attributes like `class` and `for` are written as `className` and `htmlFor` to avoid conflicts with JavaScript keywords.

This is much more powerful than plain HTML because it allows you to combine UI with dynamic data directly.

**Why Use JSX?**  
JSX simplifies how we write UI components by allowing us to blend JavaScript and markup. This makes the code easier to read and maintain, especially when building complex, dynamic applications where UI needs to change based on data.

**Example**:
Let’s say we want to greet a user by name. With JSX, you can easily embed JavaScript logic inside the UI like this:

```jsx
const user = "Jane";
return <h1>Welcome, {user}!</h1>; // Embeds JavaScript logic into JSX
```

---

## Virtual DOM

2. **What is the Virtual DOM, and how does React use it?**

   The Virtual DOM is a lightweight, in-memory representation of the real DOM. React uses it to optimize updates by comparing changes made to the Virtual DOM and applying only those changes to the real DOM through a process called reconciliation.

   **Key Benefits:**
   - **Performance:** Updates are faster as only the changed parts of the DOM are updated.
   - **Efficiency:** Reduces unnecessary DOM manipulations, improving overall app performance.

---

## Props vs State

3. **What are props and state in React? (props vs state)**

   - **Props:** Passed from parent components to child components. They are immutable and used to pass data to components.
   - **State:** Managed within the component itself, allowing it to change over time. It is mutable and typically updated using hooks like `useState`.

   | Props                          | State                          |
   | ------------------------------ | ------------------------------ |
   | Immutable                       | Mutable                        |
   | Managed by Parent Component     | Managed by the Component        |
   | Used for Passing Data           | Used for Local Data             |
   | Triggers Re-render on Parent Update | Triggers Re-render on State Change |

---

## useState vs useEffect

4. **Explain the difference between `useState` and `useEffect` in React.**

   - **useState:** A hook that allows you to add state to a functional component. It returns an array with the current state and a function to update that state.
   - **useEffect:** A hook used for side effects like data fetching, subscriptions, or manually updating the DOM. It runs after the render and can run based on dependency changes.

   | useState                         | useEffect                       |
   | --------------------------------- | ------------------------------- |
   | Used to create state              | Used to handle side effects      |
   | Triggers a re-render on state update | Runs after every render unless controlled by a dependency array |
   | No dependencies                   | Can depend on state or props     |

---

## Higher-Order Components (HOC)

5. **What is a Higher-Order Component (HOC) in React?**

   A Higher-Order Component (HOC) is a function that takes a component as an argument and returns a new component. It is used to reuse logic across multiple components without modifying them directly.

   **Key Points:**
   - HOCs do not modify the original component; they wrap it.
   - Commonly used for concerns like authentication, analytics, or state management.

---

## useCallback vs useMemo

6. **What is the difference between `useCallback` and `useMemo`?**

   - **useCallback:** Returns a memoized function. It is used when you want to pass a stable function reference to child components to prevent unnecessary re-renders.
   - **useMemo:** Returns a memoized value. It is used to cache expensive calculations so they don’t re-run on every render.

   | useCallback                      | useMemo                         |
   | --------------------------------- | ------------------------------- |
   | Memoizes a function               | Memoizes a value                |
   | Prevents re-renders of child components | Avoids running expensive calculations |

---

## Redux

7. **What is Redux, and why is it used?**

   Redux is a state management library often used with React. It provides a centralized store to manage the entire application's state, making it easier to manage and debug state changes across large applications.

   **Key Concepts:**
   - **Store:** Holds the entire state of the application.
   - **Actions:** Plain JavaScript objects that describe changes.
   - **Reducers:** Functions that take the current state and an action, then return the new state.

---

## Redux Thunk

8. **What is Redux Thunk?**

   Redux Thunk is a middleware that allows you to write asynchronous logic in Redux. Thunk enables you to dispatch functions (thunks) that contain asynchronous code such as API calls, alongside your synchronous actions.

---

## Class Components vs Functional Components

9. **What is the difference between class components and functional components in React?**

   | Class Components                 | Functional Components           |
   | --------------------------------- | ------------------------------- |
   | Uses `this` to access state/props | Uses hooks like `useState`       |
   | Requires more boilerplate         | Simpler, less code               |
   | Lifecycle methods for side effects | Hooks like `useEffect` handle side effects |

---

## Reconciliation in React

10. **What is Reconciliation in React?**

   Reconciliation is the process React uses to determine the difference between the current and new Virtual DOM and update the real DOM accordingly. React efficiently calculates the minimal set of changes needed and applies them, rather than updating the entire DOM.

---

## Hooks in React

11. **Can you explain how hooks work in React?**

   Hooks are functions that allow you to use React’s state and lifecycle features inside functional components. Common hooks include `useState`, `useEffect`, and `useContext`.

---

## useEffect vs Lifecycle Methods

12. **Why do we need `useEffect`, and how does it differ from lifecycle methods?**

   `useEffect` in functional components can mimic several lifecycle methods like `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount` from class components. It provides a unified API to manage side effects.

---

## Limitations of the Virtual DOM

13. **What are the limitations of React’s Virtual DOM?**

   - Large trees can slow down the diffing process.
   - Complex reconciliations can overwhelm the Virtual DOM’s efficiency.
   - Additional memory usage due to maintaining an in-memory representation.

---

## useCallback and Performance

14. **How does `useCallback` help with performance in React?**

   `useCallback` memoizes a function to prevent it from being recreated on every render. This can avoid unnecessary re-renders in child components that receive the function as a prop.

---

## useMemo vs useCallback

15. **When should you use `useMemo` vs `useCallback`?**

   - Use `useMemo` to memoize values like expensive calculations.
   - Use `useCallback` to memoize functions passed as props to child components.

---

## Redux vs useState

16. **How does Redux differ from React’s built-in state management using `useState`?**

   - **Redux** is a centralized state management solution for global state.
   - **useState** manages local component-specific state.

---

## Side Effects in React

17. **What are side effects in React, and how do you handle them?**

   Side effects are actions that interact with external systems (e.g., API calls, DOM manipulation). They are managed using the `useEffect` hook.

---

## Alternatives to Redux

18. **What are the alternatives to Redux for state management in React?**

   - **Context API**: Simplifies global state management without Redux’s complexity.
   - **MobX**: A more declarative way to manage state.
   - **Recoil**: A modern state management library for fine-grained control.

