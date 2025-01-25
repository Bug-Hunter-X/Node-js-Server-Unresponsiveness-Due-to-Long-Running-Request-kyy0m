# Node.js Server Unresponsiveness

This repository demonstrates a common Node.js issue where a server becomes unresponsive due to a long-running request blocking the event loop. The example uses a simple Express.js server with a route that simulates a 5-second delay.  During this delay, the server is unable to accept new requests.

## Bug

The `server.js` file contains the buggy code.  The server hangs for 5 seconds before responding to requests. This makes the server unresponsive to other requests during that period. This happens because Node.js is single-threaded.

## Solution

The `serverSolution.js` file provides a solution by using asynchronous operations.  This allows other requests to be processed concurrently, preventing the server from hanging.