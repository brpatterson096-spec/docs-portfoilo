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
