# Common Errors

Encountering errors is a natural part of working with APIs. This guide details some of the most common errors you may encounter when using the UCanPay API, along with explanations and tips for resolving them. Each error includes a description, common causes, and suggested actions to remedy the issue.

## HTTP Status Codes Overview

The UCanPay API returns standard HTTP status codes to signal the success or failure of an API request. Here’s a brief recap:

- `2xx` status codes denote successful operations.
- `4xx` status codes indicate errors caused by the information provided by the client.
- `5xx` status codes indicate errors on the UCanPay server side.

## Specific Common Errors

### Error 400: Bad Request

Occurs when the server cannot process the request due to a client error, such as incorrect syntax or a missing parameter.

**Resolution:**
- Verify the JSON structure of your request.
- Ensure all required fields are included and correctly formatted.

### Error 401: Unauthorized

This error signifies that authentication has failed, often due to incorrect or missing credentials.

**Resolution:**
- Confirm that your API keys are entered correctly.
- Check that your credentials have the necessary permissions for the requested operation.

### Error 403: Forbidden

Indicates that the server understands the request but refuses to authorize it. This can occur if your API key lacks the permissions to perform the request.

**Resolution:**
- Check the permissions associated with your API key.
- Ensure your account has sufficient privileges for the requested action.

### Error 404: Not Found

The requested resource could not be found but may be available again in the future.

**Resolution:**
- Double-check the endpoint URL.
- Verify the identifiers used in the request path.

### Error 405: Method Not Allowed

The HTTP method used in the request is not supported by the resource.

**Resolution:**
- Ensure that the HTTP method (GET, POST, PUT, DELETE) matches what the API endpoint expects.

### Error 500: Internal Server Error

A generic error message indicating an unexpected condition encountered by the server.

**Resolution:**
- Wait a few moments and retry the request.
- If the issue persists, contact UCanPay support.

## Best Practices for Handling Errors

Adopting a proactive approach to error handling can enhance the robustness of your application:

- **Implement Error Logging:** Maintain logs of all interactions, especially errors. This helps in diagnosing issues and understanding the usage patterns of your application.
- **User Communication:** Translate error messages into user-friendly language. Avoid exposing raw API errors directly to the user.
- **Alerting Mechanisms:** Use monitoring tools to alert you to critical errors, especially those with `5xx` status.
- **Graceful Degradation:** Design your application to continue operating in a limited mode if certain functionalities are unavailable due to API errors.
- **Retry Logic:** Employ retry mechanisms for transient errors, ideally with exponential backoff.
- **Feedback Loops:** Provide users with options to report issues or attempt the operation again.

For real-time API status updates, visit the [UCanPay Status Page](https://status.ucanpay.ca).

Following these guidelines will help ensure that your integration with the UCanPay API is as seamless and reliable as possible.
