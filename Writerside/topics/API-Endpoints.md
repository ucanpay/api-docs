# API Endpoints

This section of the documentation provides detailed information about each endpoint available in the API. For each endpoint, you will find the necessary details to make requests, understand the responses, and handle potential errors effectively.

## Overview

Endpoints are the touchpoints through which your application interacts with our API. They define the specific operations that can be performed—from retrieving data to executing actions.

## Endpoint Structure

Each endpoint in our API is associated with a specific URL pattern and supports one or more HTTP methods (GET, POST, PUT, DELETE, etc.). The base URL for all API endpoints is:

```api.ucanpay.ca```

### Example Endpoint: Retrieve User Data

**Endpoint:** `/users/{id}`

**Method:** GET

**Description:**
Retrieve the details of a user specified by the user ID.

**Parameters:**
- `id` (path) - The ID of the user to retrieve.

**Response:**
```json
{
  "id": "123",
  "name": "Jane Doe",
  "email": "jane.doe@example.com"
}
```

**Error Responses:**

- **404 Not Found** if the user ID does not exist.
- **500 Internal Server Error** for server errors.


### Example Endpoint: Update User Data

**Endpoint:** `/users/{id}`

**Method:** PUT

**Description:**
Update the details of a user specified by the user ID.

**Request Body:**
```json
{
  "name": "Jane Doe Updated",
  "email": "updated.jane.doe@example.com"
}

```

**Response:**
```json
{
  "id": "123",
  "name": "Jane Doe",
  "email": "jane.doe@example.com"
}
```

**Error Responses:**

- **400 Bad Request** if the request data is invalid.
- **404 Not Found** if the user ID does not exist.
- **500 Internal Server Error** for server errors.
