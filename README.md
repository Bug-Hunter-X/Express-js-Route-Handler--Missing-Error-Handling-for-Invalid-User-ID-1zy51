# Express.js Route Handler: Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling when dealing with user input.  Specifically, the example code attempts to parse a user ID as an integer without checking for non-numeric input, which can cause the application to crash or behave unexpectedly.

## Bug Description

The provided code fetches user data based on an ID from the request parameters. However, it doesn't handle the scenario where the `userId` is not a valid integer.  Attempting to parse a non-numeric string as an integer will result in `NaN`, leading to the `find` method failing to locate the user, and potentially throwing an error depending on how the error is handled (or not handled).

## Solution

The solution involves adding input validation to ensure that the `userId` is a valid integer before attempting to use it.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies (if any).
3. Run the application (e.g., `node bug.js`).
4. Send a request to `/users/<invalid_id>` (e.g., `/users/abc`). Observe the error (or lack of graceful error handling).

## License

[MIT](https://opensource.org/licenses/MIT)