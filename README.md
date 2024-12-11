# Infinite useEffect Loop in React

This repository demonstrates a common React bug: an infinite loop caused by an incorrectly implemented `useEffect` hook. The component updates its state within the `useEffect` causing a continuous re-render and leading to performance issues or crashes.

## Bug Description

The `MyComponent` uses `useEffect` to log the count.  However,  calling `setCount` inside the `useEffect` creates an infinite loop, as the state change triggers the `useEffect` again, and so on. 

## Solution

The solution uses functional updates in the `setCount` call.  This ensures that the state update is based on the previous state, breaking the infinite loop.