# Unhandled JSON Decoding Exception in Dart Async/Await

This repository demonstrates a common error in Dart when using async/await with network requests and JSON decoding.  The provided code fetches data from an API endpoint; however, it lacks robust error handling for potential `FormatException` exceptions thrown by `jsonDecode` if the API response is not valid JSON.

The `bug.dart` file showcases the initial code with insufficient error handling.  The solution, in `bugSolution.dart`, demonstrates improved error handling and more resilient JSON parsing.  It uses a `try-catch` block to handle the `FormatException` specifically and provides informative error messages.

## How to Reproduce

1. Clone this repository.
2. Run `bug.dart`.  If the API returns invalid JSON, the exception will not be gracefully handled.
3. Run `bugSolution.dart` to see how the improved error handling provides a better user experience and prevents unexpected app crashes.

## Key Learning Points

* Always handle potential exceptions during JSON decoding using `try-catch` blocks.
* Be specific in your exception handling; catch `FormatException` for JSON decoding errors.
* Provide informative error messages to users.
* Ensure your network requests include sufficient error handling for HTTP status codes and other potential issues.