# React setInterval Memory Leak

This repository demonstrates a common bug in React components involving the use of `setInterval` within the `useEffect` hook.  The issue stems from failing to properly clear the interval, resulting in multiple intervals running concurrently and ultimately causing a memory leak.  The solution shows how to correctly implement `setInterval` to prevent this problem.

## Bug

The `bug.js` file contains a React component that uses `setInterval` to update a counter every second.  However, it lacks a cleanup function in the `useEffect` hook, which prevents the interval from being cleared when the component unmounts or re-renders. This leads to multiple intervals running simultaneously, consuming increasing amounts of memory.

## Solution

The `bugSolution.js` file provides the corrected implementation.  A cleanup function is added to the `useEffect` hook using the `return` statement, ensuring that `clearInterval` is called when the component is unmounted or re-renders.