# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid input. Specifically, this example shows a route that fetches a user by ID, but fails to handle the case where the ID is not a valid number.

## Bug

The `bug.js` file contains the buggy code.  The route handler attempts to parse the user ID as an integer using `parseInt()`, but doesn't handle the case where `req.params.id` is not a parsable integer. This leads to unexpected behavior or crashes.

## Solution

The `bugSolution.js` file shows the corrected code.  The solution adds error handling to check if `parseInt(userId)` returns `NaN`. If so, it gracefully handles the error by returning a 400 Bad Request status code.