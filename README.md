# Express.js Route Handler Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers: the lack of error handling for invalid input.  Specifically, the example shows a route that retrieves a user by ID.  If the ID is not a valid number, the code crashes without providing a graceful error message to the user.

## Bug
The `bug.js` file contains the problematic code. The route handler attempts to parse the `userId` from the request parameters as an integer using `parseInt()`, but it doesn't check if the result is a valid number. If `req.params.id` is not a valid integer (e.g., a string or a non-numeric value), `parseInt()` will return `NaN`, and the subsequent `.find()` operation may cause an error or return unexpected results.

## Solution
The `bugSolution.js` file provides a corrected version.  It includes checks to ensure that `userId` is a valid number before proceeding. This prevents potential errors and ensures the application handles invalid input gracefully.

## How to run the code:
1. Clone this repository.
2. Navigate to the project directory.
3. Install dependencies using `npm install express`.
4. Run the buggy code with `node bug.js` and the fixed code with `node bugSolution.js`.  Test with both valid and invalid user IDs.