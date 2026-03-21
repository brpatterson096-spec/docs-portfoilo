# Authentication API

This document describes how users authenticate with the API.

## Base URL

https://api.example.com/v1

## Login

POST /auth/login

Authenticates a user and returns an access token.

### Request Body

| Field | Type | Required | Description |
|------|------|------|------|
| email | string | yes | User email |
| password | string | yes | User password |

### Example Request

POST /v1/auth/login

{
  "email": "user@example.com",
  "password": "securepassword"
}

### Example Response

{
  "access_token": "abc123token",
  "token_type": "Bearer"
}
## Logout

POST /auth/logout

Logs out the currently authenticated user.

### Example Request

POST /v1/auth/logout

Authorization: Bearer YOUR_ACCESS_TOKEN

### Example Response

{
  "message": "Successfully logged out"
}

### Errors

| Status | Meaning |
|------|------|
| 401 | Unauthorized |
### Errors

| Status | Meaning |
|------|------|
| 401 | Invalid credentials |
