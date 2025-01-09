# React setInterval Memory Leak in useEffect

This repository demonstrates a common error in React: using `setInterval` within the `useEffect` hook without proper cleanup.  This leads to memory leaks as the interval continues to run even after the component unmounts.

## Bug

The `bug.js` file shows a `MyComponent` that increments a counter every second using `setInterval`. However, it lacks the necessary cleanup function in the `useEffect` hook's return statement to stop the interval when the component is unmounted.

## Solution

The `bugSolution.js` file corrects this by adding `clearInterval(intervalId)` to the `useEffect` hook's return function. This ensures that the interval is properly stopped when the component unmounts, preventing memory leaks.

## How to reproduce the bug:

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe that the counter keeps increasing even if you navigate away from the page (in a browser), indicating a memory leak. The solution addresses this issue by properly clearing the interval.
