# Users API

This document describes how to retrieve user information from the Users API.

## Base URL

https://api.example.com/v1

## Authentication

All requests require a bearer token.

Example header:

Authorization: Bearer YOUR_API_TOKEN

## Get User

GET /users/{id}

Returns a user by ID.

### Path Parameters

| Name | Type | Required | Description |
|-----|-----|-----|-----|
| id | integer | yes | Unique user ID |

### Example Request

GET /v1/users/10

### Example Response

{
  "id": 10,
  "name": "Jane Smith",
  "email": "jane@example.com"
}

### Errors

| Status | Meaning |
|------|------|
| 401 | Unauthorized |
| 404 | User not found |
## List Users

GET /users

Returns a list of users.

### Example Request

GET /v1/users

### Example Response

[
  {
    "id": 10,
    "name": "Jane Smith",
    "email": "jane@example.com"
  },
  {
    "id": 11,
    "name": "Alex Johnson",
    "email": "alex@example.com"
  }
]

### Errors

| Status | Meaning |
|------|------|
| 401 | Unauthorized |
| 500 | Server error |
## Create User

POST /users

Creates a new user.

### Request Body

| Field | Type | Required | Description |
|------|------|------|------|
| name | string | yes | User's full name |
| email | string | yes | User's email address |

### Example Request

POST /v1/users

{
  "name": "Chris Miller",
  "email": "chris@example.com"
}

### Example Response

{
  "id": 12,
  "name": "Chris Miller",
  "email": "chris@example.com"
}
## Delete User

DELETE /users/{id}

Deletes a user by ID.

### Path Parameters

| Name | Type | Required | Description |
|-----|-----|-----|-----|
| id | integer | yes | The ID of the user to delete |

### Example Request

DELETE /v1/users/12

### Example Response

{
  "message": "User deleted successfully"
}

### Errors

| Status | Meaning |
|------|------|
| 401 | Unauthorized |
| 404 | User not found |
### Errors

| Status | Meaning |
|------|------|
| 400 | Invalid request |
| 401 | Unauthorized |
## Update User

PUT /users/{id}

Updates an existing user.

### Path Parameters

| Name | Type | Required | Description |
|-----|-----|-----|-----|
| id | integer | yes | The ID of the user to update |

### Request Body

| Field | Type | Required | Description |
|------|------|------|------|
| name | string | no | Updated user name |
| email | string | no | Updated email address |

### Example Request

PUT /v1/users/12

{
  "name": "Chris Miller",
  "email": "chris.miller@example.com"
}

### Example Response

{
  "id": 12,
  "name": "Chris Miller",
  "email": "chris.miller@example.com"
}

### Errors

| Status | Meaning |
|------|------|
| 400 | Invalid request |
| 401 | Unauthorized |
| 404 | User not found |
