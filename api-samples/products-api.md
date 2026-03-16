# Products API

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

GET /v1/products/100

### Example Response

{
  "id": 100,
  "name": "Wireless Mouse",
  "price": 29.99
}

### Errors

| Status | Meaning |
|------|------|
| 401 | Unauthorized |
| 404 | Product not found |
