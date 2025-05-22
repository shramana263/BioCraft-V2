# API Documentation - BioCraft

## Overview
This document provides detailed information about the BioCraft API endpoints and their usage.

## Base URL
```
Production: https://your-production-api.com/api
Development: http://localhost:8000/api
```

## Authentication
All authenticated endpoints require a Bearer token in the Authorization header:
```
Authorization: Bearer {your-jwt-token}
```

## Authentication Endpoints

### POST /login
Login user and get authentication token.

**Request Body:**
```json
{
    "email": "user@example.com",
    "password": "password123"
}
```

**Response:**
```json
{
    "success": true,
    "user": {
        "id": 1,
        "name": "John Doe",
        "email": "user@example.com"
    },
    "token": "jwt-token-here"
}
```

### POST /registration
Register a new user account.

**Request Body:**
```json
{
    "name": "John Doe",
    "email": "user@example.com",
    "password": "password123",
    "password_confirmation": "password123"
}
```

### POST /logout
Logout current user (requires authentication).

**Response:**
```json
{
    "success": true,
    "message": "Successfully logged out"
}
```

## User Endpoints

### GET /user
Get current authenticated user information.

**Response:**
```json
{
    "id": 1,
    "name": "John Doe",
    "email": "user@example.com",
    "created_at": "2024-01-01T00:00:00.000000Z"
}
```

### GET /users
Get list of all users (admin only).

**Response:**
```json
{
    "data": [
        {
            "id": 1,
            "name": "John Doe",
            "email": "user@example.com"
        }
    ]
}
```

## Biodata Endpoints

### POST /biodata
Create new biodata entry.

**Request Body:**
```json
{
    "personal_details": {
        "name": "John Doe",
        "phone": "+1234567890",
        "address": "123 Main St"
    },
    "education": [
        {
            "degree": "Bachelor's",
            "institution": "University Name",
            "year": "2020"
        }
    ],
    "experience": [
        {
            "position": "Software Developer",
            "company": "Company Name",
            "duration": "2020-2023"
        }
    ],
    "skills": ["JavaScript", "React", "Node.js"]
}
```

### GET /biodata
Get user's biodata.

### PUT /biodata/{id}
Update existing biodata.

### DELETE /biodata/{id}
Delete biodata entry.

## File Upload Endpoints

### POST /upload/profile-image
Upload profile image.

**Request:**
- Content-Type: multipart/form-data
- Field: image (file)

**Response:**
```json
{
    "success": true,
    "image_url": "uploads/profile/image.jpg"
}
```

## Error Responses

### Validation Error (422)
```json
{
    "success": false,
    "message": "Validation failed",
    "errors": {
        "email": ["The email field is required."]
    }
}
```

### Unauthorized (401)
```json
{
    "success": false,
    "message": "Unauthorized"
}
```

### Not Found (404)
```json
{
    "success": false,
    "message": "Resource not found"
}
```

## Rate Limiting
- 60 requests per minute per IP address
- 1000 requests per hour for authenticated users

## Pagination
List endpoints support pagination:
```
GET /users?page=1&per_page=15
```

**Response:**
```json
{
    "data": [],
    "current_page": 1,
    "total": 100,
    "per_page": 15,
    "last_page": 7
}
```
