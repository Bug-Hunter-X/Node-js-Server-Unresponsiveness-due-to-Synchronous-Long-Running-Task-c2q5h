# Node.js Server Unresponsiveness Bug

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in the request handler blocks the event loop, causing the server to hang or become unresponsive.  The `server.js` file contains the buggy code, while `serverSolution.js` provides a solution using asynchronous operations.

## Bug Description

The server uses a `while` loop to simulate a long-running task.  This blocks the event loop, preventing other requests from being processed until the loop completes.  This leads to unresponsiveness and poor performance.

## Solution

The solution involves refactoring the code to use asynchronous operations, such as `setTimeout` or promises, to prevent blocking the event loop.  This allows the server to handle multiple requests concurrently.

## How to Reproduce

1. Clone this repository.
2. Navigate to the directory.
3. Run `node server.js`.
4. Try to make multiple requests to the server (e.g., using `curl`).  You will observe that the server becomes unresponsive.
5. Run `node serverSolution.js` to see the corrected version.  This version will handle multiple requests without hanging.