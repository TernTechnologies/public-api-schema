# Candidate API Documentation

## Introduction

This API documentation provides details about the endpoints and data structures for creating a new candidate with the associated information.

### Base URL

The base URL for accessing the production API is `https://push.tern-group.com`
The base URL for accessing the development API is `https://push.dev.tern-group.com`

The API is accessible over HTTPS.
The default resource path for the API is `/crm-events/v1`.

### JSON Schema

The API expects and returns data in JSON format. Below is the JSON schema representing the candidate data structure.

[Candidate JSON Schema](candidate-schema.json)
[Example Candidate JSON](../../example/candidate/example-candidate.json)

## Endpoints

1. **Create a New Candidate**

    `POST /candidates`

    - Create a new candidate record.

    **Request Body:**

    JSON object representing the candidate details following the JSON schema.

    **Response:**

    - `201 Created`: Returns the created candidate information in the JSON format as per the schema.
    - `400 Bad Request`: If the request body is invalid or missing required fields.

    **Example:**

    ```http
    POST /candidates
    Content-Type: application/json

    {
        "name": "John Doe",
        "email": "",
        "phone": "1234567890",
        "resume": "https://example.com/resume.pdf"
        // add other fields as required
    }
    ```

2. **Update Candidate Details**

    `PUT /candidates`

    - Update the details of an existing candidate.

    **Request Body:**

    Full JSON object as required representing the candidate details following the JSON schema.

    **Response:**

    - `200 OK`: Returns the updated candidate information in the JSON format as per the schema.
    - `400 Bad Request`: If the request body is invalid or missing required fields.
    - `404 Not Found`: If the candidate with the specified ID is not found.

    **Example:**

    ```http
    PUT /candidates/123
    Content-Type: application/json

    {
        "name": "John Doe",
        "email": "
        // add other fields as required
    }
    ```

## Error Responses

The API may return the following error responses:

-   `400 Bad Request`: If the request is invalid or missing required parameters.
-   `401 Unauthorized`: If authentication credentials are missing or invalid.
-   `404 Not Found`: If the requested resource is not found.
-   `500 Internal Server Error`: If there is a server-side error.
-   `503 Service Unavailable`: If the server is temporarily unable to handle the request.

## Rate Limiting

To ensure fair usage of the API, rate limiting is enforced. Exceeding the rate limit will result in a `429 Too Many Requests` response.
