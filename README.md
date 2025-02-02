# Node.js Server Crashing After Handling Many Requests

This repository demonstrates a bug where a simple Node.js HTTP server crashes unexpectedly after handling a large number of requests. The server uses the built-in `http` module and doesn't include any error handling. The crash occurs without providing any helpful error messages in the console.

## Bug Report

A Node.js server implemented using the `http` module crashes without any error messages logged to the console after processing a significant number of requests.  The server is designed to respond with 'Hello, World!' to each request.  There are no apparent exceptions or errors caught within the application itself. This unexpected behavior can lead to service disruptions and makes debugging difficult.

## Steps to Reproduce

1. Clone this repository.
2. Run `node server.js` to start the server.
3. Use a tool like `wrk` or `ApacheBench` to send a large number of requests to the server (e.g., 10000 requests).
4. Observe the server crash without any error messages printed in the terminal.

## Solution

The solution involves proper error handling and resource management. The provided solution includes a `try...catch` block to handle potential errors and demonstrates using an event listener for error handling, logging for improved diagnostics, and preventing the server from crashing due to unhandled exceptions. This improved error handling makes the application more robust and easier to debug.