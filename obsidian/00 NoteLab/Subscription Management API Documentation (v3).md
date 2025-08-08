API for managing subscriptions, plans, and payments in a Django REST Framework implementation, transitioning from Laravel (v2) to Python Django (v3).

## Base URL

`/api/v3/`

## Authentication

JWT-based authentication required for all endpoints.

## Endpoints

### 1. List Subscriptions

- **GET** `/subscriptions/`
- **Description**: Retrieve a list of all subscriptions for the authenticated user.
- **Query Parameters**:
    - `status` (optional): Filter by status (`active`, `inactive`).
    - `plan_id` (optional): Filter by subscription plan ID.
- **Response**:
    
    ```json
    [
      {
        "id": 1,
        "user_id": 1,
        "subscription_plan_id": 1,
        "plan_amount": 29.99,
        "plan_frequency": "month",
        "starts_at": "2025-04-01T00:00:00Z",
        "ends_at": "2025-05-01T00:00:00Z",
        "trial_ends_at": null,
        "status": "active"
      }
    ]
    ```
    
- **Status Codes**:
    - 200: Success
    - 401: Unauthorized

### 2. Create Subscription

- **POST** `/subscriptions/`
- **Description**: Create a new subscription for the authenticated user.
- **Request Body**:
    
    ```json
    {
      "subscription_plan_id": 1,
      "plan_amount": 29.99,
      "plan_frequency": "month",
      "payment_gateway": "stripe",
      "transaction_id": "txn_123"
    }
    ```
    
- **Response**:
    
    ```json
    {
      "id": 1,
      "user_id": 1,
      "subscription_plan_id": 1,
      "plan_amount": 29.99,
      "plan_frequency": "month",
      "starts_at": "2025-04-01T00:00:00Z",
      "ends_at": "2025-05-01T00:00:00Z",
      "status": "active"
    }
    ```
    
- **Status Codes**:
    - 201: Created
    - 400: Bad Request
    - 401: Unauthorized

### 3. Retrieve Subscription

- **GET** `/subscriptions/{id}/`
- **Description**: Retrieve details of a specific subscription.
- **Response**:
    
    ```json
    {
      "id": 1,
      "user_id": 1,
      "subscription_plan_id": 1,
      "plan_amount": 29.99,
      "plan_frequency": "month",
      "starts_at": "2025-04-01T00:00:00Z",
      "ends_at": "2025-05-01T00:00:00Z",
      "status": "active"
    }
    ```
    
- **Status Codes**:
    - 200: Success
    - 401: Unauthorized
    - 404: Not Found

### 4. Update Subscription

- **PATCH** `/subscriptions/{id}/`
- **Description**: Update an existing subscription (e.g., change plan or status).
- **Request Body**:
    
    ```json
    {
      "plan_frequency": "year",
      "status": "active"
    }
    ```
    
- **Response**:
    
    ```json
    {
      "id": 1,
      "user_id": 1,
      "subscription_plan_id": 1,
      "plan_amount": 299.99,
      "plan_frequency": "year",
      "starts_at": "2025-04-01T00:00:00Z",
      "ends_at": "2026-04-01T00:00:00Z",
      "status": "active"
    }
    ```
    
- **Status Codes**:
    - 200: Success
    - 400: Bad Request
    - 401: Unauthorized
    - 404: Not Found

### 5. Delete Subscription

- **DELETE** `/subscriptions/{id}/`
- **Description**: Cancel a subscription.
- **Response**: Empty response.
- **Status Codes**:
    - 204: No Content
    - 401: Unauthorized
    - 404: Not Found

### 6. List Subscription Plans

- **GET** `/subscription-plans/`
- **Description**: Retrieve all available subscription plans.
- **Response**:
    
    ```json
    [
      {
        "id": 1,
        "name": "Premium Monthly",
        "price": 29.99,
        "currency": "USD",
        "frequency": "month",
        "tier": "premium"
      }
    ]
    ```
    
- **Status Codes**:
    - 200: Success
    - 401: Unauthorized

### 7. Process Payment

- **POST** `/payments/`
- **Description**: Process a payment for a subscription.
- **Request Body**:
    
    ```json
    {
      "subscription_id": 1,
      "amount": 29.99,
      "payment_gateway": "stripe",
      "transaction_id": "txn_123"
    }
    ```
    
- **Response**:
    
    ```json
    {
      "id": 1,
      "subscription_id": 1,
      "amount": 29.99,
      "payment_gateway": "stripe",
      "transaction_date": "2025-04-01T00:00:00Z"
    }
    ```
    
- **Status Codes**:
    - 201: Created
    - 400: Bad Request
    - 401: Unauthorized

## Class Diagram
![[class 2.png]]


## Activity Diagram

![[activity-diagram.png]]

## Notes

- The v3 API improves on v2 by adding support for multiple payment gateways (Stripe, PayPal) and flexible plan frequencies (month, year, quarter, biannual, pay-as-you-go).
- All datetime fields use ISO 8601 format.
- Error responses follow standard JSON API format.