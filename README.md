# React Memory Leak: setInterval in useEffect without Cleanup

This repository demonstrates a common React bug involving memory leaks caused by the improper use of `setInterval` within the `useEffect` hook. The example showcases how failing to clean up the interval results in multiple intervals running concurrently, leading to increased memory consumption and potential performance issues.

## Bug Description

The provided code uses `setInterval` to increment a counter every second.  However, it neglects to clear the interval when the component unmounts or when the effect needs to be canceled, resulting in a memory leak.  Each time the component renders, a new interval is added without removing the previous ones.

## Solution

The solution involves using the `clearInterval` function to properly clean up the interval before the component is unmounted or when a dependency changes, ensuring that only one interval runs at a time.

## How to reproduce the bug

1. Clone the repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the counter incrementing every second.  Opening multiple tabs will demonstrate the escalating memory usage.
