# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook.  The bug arises from an incomplete dependency array, leading to an infinite re-rendering loop.  The solution shows how to correctly specify dependencies to avoid this issue.

## Bug
The `bug.js` file contains a `MyComponent` that uses `useEffect` to log the current count.  However, the dependency array `[]` is empty. This means the effect runs after every render, regardless of changes in the state.  Updating `count` leads to another render, which triggers the effect again, and the cycle continues.

## Solution
The `bugSolution.js` file demonstrates the corrected version. The `count` variable is added to the dependency array `[count]`. The effect now only runs when `count` changes.