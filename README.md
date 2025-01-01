# Unhandled Request in Express.js Route Handler

This repository demonstrates a common error in Express.js applications where a route handler doesn't explicitly send a response, leading to hanging requests.  The `bug.js` file showcases the problematic code, while `bugSolution.js` provides the corrected version.

## Problem

The server starts successfully, but requests to the root path '/' hang indefinitely. This happens because the route handler logs a message but doesn't use `res.send()`, `res.json()`, or any other method to send a response back to the client.  Without this, the connection remains open, resulting in a timeout.

## Solution

The solution involves adding a response-sending mechanism.  This can be a simple text response, JSON data, or any other relevant content depending on the application's needs.  `bugSolution.js` illustrates how to fix the issue by adding `res.send('Hello from Express!')`. This sends a simple text response to the client, closing the connection and completing the request.
