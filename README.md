# Node.js Server Hangs or Experiences Unexpected Delays

This repository demonstrates a common issue in Node.js servers where unexpected delays or hangs can occur due to unhandled exceptions or blocking operations within request handlers.

## Problem
The provided `server.js` demonstrates a scenario where a 5-second delay is introduced in the request handler.  In real-world applications, this could be caused by:

* **Long-running operations:** Database queries, file I/O, external API calls.
* **Unhandled exceptions:** Errors that are not caught and handled properly.
* **Blocking operations:** Operations that prevent the event loop from processing other events.

This can lead to poor performance and unresponsive servers. The solution demonstrates how to avoid such issues.

## Solution
The solution is found in `serverSolution.js`.  Key improvements include:

* **Asynchronous operations:** Using asynchronous methods to handle long-running operations.
* **Error handling:** Implementing robust error handling to prevent unhandled exceptions.
* **Avoiding blocking operations:** Using appropriate techniques to avoid blocking the event loop.

## How to reproduce
1. Clone this repository.
2. Run `node server.js`
3. Make a request to `http://localhost:3000`. Observe the 5-second delay. This shows how a simple delay can cause a hang for longer requests.
4. Run `node serverSolution.js`
5. Make a request to `http://localhost:3000`.  This demonstrates that the improvements prevent hanging for longer requests.