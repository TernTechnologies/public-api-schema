# Candidate API Documentation

## Introduction

This API documentation provides details about the endpoints and data structures for creating a new candidate with the associated information.

### Base URL
The base URL for accessing the API is `https://push.tern-group.com`

### JSON Schema
The API expects and returns data in JSON format. Below is the JSON schema representing the candidate data structure.

[Candidate JSON Schema](candidate.schema.json)

## Endpoints

1. **Create a New Candidate**

   `POST /candidates`
   - Create a new candidate record.

   **Request Body:**
   
   JSON object representing the candidate details following the JSON schema.

   **Response:**
   
   - `201 Created`: Returns the created candidate information in the JSON format as per the schema.
   - `400 Bad Request`: If the request body is invalid or missing required fields.

## Error Responses

The API may return the following error responses:

- `400 Bad Request`: If the request is invalid or missing required parameters.
- `401 Unauthorized`: If authentication credentials are missing or invalid.
- `404 Not Found`: If the requested resource is not found.
- `500 Internal Server Error`: If there is a server-side error.
- `503 Service Unavailable`: If the server is temporarily unable to handle the request.

## Rate Limiting

To ensure fair usage of the API, rate limiting is enforced. Exceeding the rate limit will result in a `429 Too Many Requests` response.
