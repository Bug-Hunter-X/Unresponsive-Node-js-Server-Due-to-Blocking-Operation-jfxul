# Unresponsive Node.js Server

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in the request handler blocks the event loop, making the server unresponsive.  The solution showcases the use of asynchronous operations to prevent this problem.

## Bug

The `server.js` file contains a Node.js HTTP server with a request handler that performs a synchronous operation (a `while` loop) that keeps the CPU busy for 5 seconds. During this time, the server is unable to process any other requests, leading to unresponsiveness.

## Solution

The `serverSolution.js` file demonstrates how to resolve this by using asynchronous operations.  Instead of blocking the event loop, the solution uses `setTimeout` to schedule the response after a 5-second delay.  This allows the event loop to continue processing other requests while the delay is running.