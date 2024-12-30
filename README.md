# React useEffect Infinite Loop Bug
This repository demonstrates a common error in React's `useEffect` hook: an infinite loop caused by omitting a state variable from the dependency array.

## Bug Description
The `MyComponent` component uses `useState` to track a count.  The `useEffect` hook logs the current count to the console. However, the `count` variable is missing from the dependency array of the `useEffect` hook. This leads to an infinite render loop because the effect runs after every render, regardless of changes in `count`, causing the component to re-render repeatedly and triggering the effect again.

## Solution
Adding `count` to the dependency array fixes the issue. The effect now only runs when `count` changes.