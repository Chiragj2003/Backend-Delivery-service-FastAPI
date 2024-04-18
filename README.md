# Pizza Delivery API

An API for a Pizza Delivery Service built with FastAPI and integrated JWT authentication.

## Overview

This API provides endpoints for managing user authentication and placing orders for pizza delivery.

## Authentication

This API uses JWT (JSON Web Tokens) for authentication. To access protected endpoints, clients must include a JWT access token in the `Authorization` header, formatted as `Bearer <JWT>`, where `<JWT>` is the actual token.

### Security Scheme

The API uses the following security scheme:

- **Bearer Auth**: JWT-based authentication
  - Type: apiKey
  - In: header
  - Name: Authorization
  - Description: Enter: **'Bearer <JWT>'**, where JWT is the access token

## Endpoints

The following endpoints are available:

- **Authentication Routes**
  - `/auth/login`: User login to obtain JWT token.
  - `/auth/register`: User registration.
  - `/auth/me`: Get current user information.

- **Order Routes**
  - `/orders/create`: Create a new pizza order.
  - `/orders/{order_id}`: Get details of a specific order.
  - `/orders/`: Get a list of all orders.

## OpenAPI Documentation

The API documentation is generated dynamically using FastAPI's OpenAPI support. You can access the API documentation by navigating to the `/docs` endpoint when the server is running.

## Running the API

To run the API locally, follow these steps:

1. Clone the repository.
2. Install the required dependencies using `pip install -r requirements.txt`.
3. Run the FastAPI server using `uvicorn main:app --reload`.
4. Access the API documentation in your web browser at `http://localhost:8000/docs`.

## Configuration

The API configuration is loaded from a `Settings` model, which can be customized as needed. Refer to the `Settings` model for available configuration options.

## Custom OpenAPI Generation

The OpenAPI schema for this API is generated dynamically to include JWT authentication information for protected endpoints. The `custom_openapi` function in the codebase customizes the OpenAPI schema generation process to include security definitions for routes that require JWT authentication.

For more details on the custom OpenAPI generation, refer to the `custom_openapi` function in the codebase.

