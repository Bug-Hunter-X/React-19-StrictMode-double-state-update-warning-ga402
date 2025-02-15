# React 19 StrictMode Double State Update Warning

This repository demonstrates a common error encountered when upgrading to React 19 due to changes in StrictMode.  The bug involves calling `setCount` twice in quick succession, triggering a warning in StrictMode.  The solution shows how to refactor the code to prevent the warning.

## Bug

The `bug.js` file contains code that updates the state multiple times within a single event handler. React 19 StrictMode detects this and issues a warning because it can lead to unexpected behavior.  The warning itself doesn't immediately cause a crash, but it indicates a potential performance issue or logic error.

## Solution

The `bugSolution.js` file demonstrates how to fix the issue.  The key is to ensure state updates are performed sequentially and not in parallel within the same event. One common pattern is to use `setTimeout` with a `0` delay to ensure the updates happen after the current render has completed.