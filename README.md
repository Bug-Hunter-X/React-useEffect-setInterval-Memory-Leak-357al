# React useEffect setInterval Memory Leak

This repository demonstrates a common mistake when using the `setInterval` function within a React `useEffect` hook: forgetting to return a cleanup function. This can lead to memory leaks, as the interval continues to run even after the component unmounts.

## Bug

The `bug.js` file contains the erroneous code. The `setInterval` function is called, but no cleanup function is returned to stop the interval when the component is unmounted.  This results in the `setInterval` continuing indefinitely, consuming resources even after the component is no longer needed. 

## Solution

The `bugSolution.js` file provides the corrected code. It includes a cleanup function that uses `clearInterval` to stop the interval when the component unmounts, preventing memory leaks.