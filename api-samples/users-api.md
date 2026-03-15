# Users API
## Table of Contents

- [Base URL](#base-url)
- [Authentication](#authentication)
- [Get User](#get-user)
- [List Users](#list-users)
- [Create User](#create-user)
- [Update User](#update-user)
- [Delete User](#delete-user)

This document describes how to retrieve user information from the Users API.

## Base URL

https://api.example.com/v1

## Authentication

## Table of Contents

- [Base URL](#base-url)
- [Login](#login)
- [Logout](#logout)
- [Register](#register)

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

POST /v1/auth/register

{
  "name": "Taylor Brown",
  "email": "taylor@example.com",
  "password": "securepassword"
}

### Example Response

{
  "id": 21,
  "name": "Taylor Brown",
  "email": "taylor@example.com"
}

### Errors

| Status | Meaning |
|------|------|
| 400 | Invalid request |
| 409 | Email already exists |
