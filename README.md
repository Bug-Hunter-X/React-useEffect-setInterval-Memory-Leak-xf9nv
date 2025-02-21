# React useEffect setInterval Memory Leak

This repository demonstrates a common mistake when using `setInterval` within a React `useEffect` hook: forgetting to return a cleanup function.  This can lead to memory leaks, as the interval continues to run even after the component unmounts.

## Bug

The `bug.js` file contains the problematic code. The `setInterval` function is used to update a counter every second. However, no cleanup function is returned to stop the interval when the component unmounts.

## Solution

The `bugSolution.js` file shows the corrected code.  The `setInterval` is now correctly managed by returning a cleanup function that uses `clearInterval` to stop the interval before the component unmounts.