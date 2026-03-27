# Authentication API
## Table of Contents

- [Base URL](#base-url)
- [Login](#login)
- [Logout](#logout)
- [Register](#register)
This document describes how users authenticate with the API.

## Base URL
## Prerequisites

Before using this API, ensure you have:

- An API access token
- A tool to make HTTP requests (e.g., curl or Postman)
- Basic understanding of REST APIs
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
```http
POST /v1/auth/login

{
  "email": "user@example.com",
  "password": "securepassword"
}

### Example Response
```json
{
  "access_token": "abc123token",
  "token_type": "Bearer"
}
## Logout

POST /auth/logout

Logs out the currently authenticated user.

### Example Request
```http
POST /v1/auth/logout

Authorization: Bearer YOUR_ACCESS_TOKEN

### Example Response
```json
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
## Register

POST /auth/register

Creates a new user account.

### Request Body

| Field | Type | Required | Description |
|------|------|------|------|
| name | string | yes | User's full name |
| email | string | yes | User email |
| password | string | yes | User password |

### Example Request
```http
POST /v1/auth/register

{
  "name": "Taylor Brown",
  "email": "taylor@example.com",
  "password": "securepassword"
}

### Example Response
```json
{
  "id": 21,
  "name": "Taylor Brown",
  "email": "taylor@example.com"
}

### Errors

| Status Code | Meaning | Description |
|-------------|--------|-------------|
| 400 | Bad Request | The request was invalid or missing required fields |
| 401 | Unauthorized | Authentication credentials are missing or invalid |
| 500 | Server Error | An unexpected error occurred on the server |
