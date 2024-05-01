# Error Handling

Proper error handling is essential to inform users of any issues that occur during API requests and to allow developers
to diagnose and address problems. This guide covers the common errors you may encounter with the UCanPay API and how to
handle them gracefully.

## HTTP Status Codes

The UCanPay API uses conventional HTTP response codes to indicate the success or failure of an API request. In general:

- `2xx` status codes indicate success.
- `4xx` status codes indicate an error resulting from the provided information (e.g., a required parameter was omitted,
  a charge failed, etc.).
- `5xx` status codes indicate an error with UCanPay's servers.

## Handling Common Errors

Here's how you can handle some of the most common error statuses:

### Bad Request (400)

This indicates that the server cannot or will not process the request due to something perceived to be a client error (
e.g., malformed request syntax).

**Example Response:**

```json
{
  "status": 400,
  "error": "Bad Request",
  "message": "The request cannot be fulfilled due to bad syntax."
}
```

**Action:** Check the JSON structure and data types of your request.

### Unauthorized (401)

Authentication has failed or has not been provided.

**Example Response:**

```json
{
  "status": 401,
  "error": "Unauthorized",
  "message": "Authentication credentials were missing or incorrect."
}
```

**Action:** Ensure your API keys are correct and have the necessary permissions.

### Forbidden (403)

The request is valid, but the server is refusing to respond to it.

**Example Response:**

```json
{
  "status": 403,
  "error": "Forbidden",
  "message": "You do not have enough privileges to execute this operation."
}
```

**Action:** Check that your API key has permissions to perform the request.

### Not Found (404)

The requested resource could not be found on the server.

**Example Response:**

```json
{
  "status": 404,
  "error": "Not Found",
  "message": "The requested resource does not exist."
}
```

**Action:** Verify the endpoint URL and the resource identifier.

### Method Not Allowed (405)

The method specified in the request is not allowed for the resource identified by the request URI.

**Example Response:**

```json
{
  "status": 405,
  "error": "Method Not Allowed",
  "message": "The request method is not supported by the resource."
}
```

**Action:** Check the HTTP method of your request (e.g., GET, POST).

### Internal Server Error (500)

A generic error message indicating an unexpected condition was encountered on the server.

**Example Response:**

```json
{
  "status": 500,
  "error": "Internal Server Error",
  "message": "An unexpected condition was encountered on the server."
}
```

**Action:** These are server-side issues. Wait and retry the request or contact UCanPay support.

## Best Practices

Adhering to the following best practices can enhance error handling and improve the stability and user experience of
your application when using the UCanPay API:

- **Log Errors:** Implement comprehensive logging for all API interactions, especially for error responses. This will
  create an audit trail that can be invaluable for troubleshooting and understanding the history of API usage.

- **User-Friendly Messages:** Translate technical error messages into clear, understandable language for end-users.
  Avoid exposing raw API errors directly to users, as these may contain sensitive information or be confusing.

- **Alerting Mechanisms:** Set up monitoring and alerting for `5xx` server errors. These types of errors are often
  indicative of issues with the API or the infrastructure it runs on and may require prompt attention.

- **Graceful Degradation:** Design your application to degrade gracefully in the event of an API failure. This may
  include providing alternate workflows, caching data, or offering informative messages to users.

- **Retry Logic:** Implement intelligent retry logic for handling transient errors. Exponential backoff strategies can
  be effective in managing retries for temporary issues.

- **Status Page:** Keep an eye on the [UCanPay Status Page](https://ucanpay.ca) for real-time information about
  the API's performance and uptime. This can help you discern whether an issue is on your end or with the API service.

- **User Feedback:** In cases where an operation fails, provide mechanisms for users to report the issue or try the
  operation again.

By following these practices, you can ensure a more robust integration with the UCanPay API and provide a better overall
experience for your users.
