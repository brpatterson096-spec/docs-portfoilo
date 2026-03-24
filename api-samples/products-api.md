# Products API
## Table of Contents

- [Base URL](#base-url)
- [Authentication](#authentication)
- [Get Product](#get-product)
- [List Products](#list-products)
- [Create Product](#create-product)

This document describes how to retrieve product information.

## Base URL

https://api.example.com/v1

## Authentication

All requests require a bearer token.

Authorization: Bearer YOUR_ACCESS_TOKEN

## Get Product

GET /products/{id}

Returns a product by ID.

### Path Parameters

| Name | Type | Required | Description |
|-----|-----|-----|-----|
| id | integer | yes | Unique product ID |

### Example Request
```http
GET /v1/products/100

### Example Response
```json
{
  "id": 100,
  "name": "Wireless Mouse",
  "price": 29.99
}
## List Products

GET /products

Returns a list of products.

### Example Request
```http
GET /v1/products

### Example Response
```json
[
  {
    "id": 100,
    "name": "Wireless Mouse",
    "price": 29.99
  },
  {
    "id": 101,
    "name": "Mechanical Keyboard",
    "price": 89.99
  }
]

### Errors

| Status | Meaning |
|------|------|
| 401 | Unauthorized |
| 500 | Server error |
### Errors

| Status | Meaning |
|------|------|
| 401 | Unauthorized |
| 404 | Product not found |
## Create Product

POST /products

Creates a new product.

### Request Body

| Field | Type | Required | Description |
|------|------|------|------|
| name | string | yes | Product name |
| price | number | yes | Product price |

### Example Request
```http
POST /v1/products

{
  "name": "Gaming Headset",
  "price": 59.99
}

### Example Response
```json
{
  "id": 102,
  "name": "Gaming Headset",
  "price": 59.99
}

### Errors

| Status | Meaning |
|------|------|
| 400 | Invalid request |
| 401 | Unauthorized |
