# API Documentation

## Overview

This document describes the available API endpoints.

## Authentication

All API requests require a Bearer token in the Authorization header:

```
Authorization: Bearer <token>
```

## Endpoints

### GET /api/health

Check service health status.

**Response:**
```json
{
  "status": "healthy",
  "timestamp": "2024-01-15T10:30:00Z"
}
```

### GET /api/users

Retrieve list of users.

**Response:**
```json
{
  "users": [
    {"id": 1, "name": "Alice"},
    {"id": 2, "name": "Bob"}
  ]
}
```

### POST /api/users

Create a new user.

**Request:**
```json
{
  "name": "Charlie",
  "email": "charlie@example.com"
}
```

**Response:**
```json
{
  "id": 3,
  "name": "Charlie",
  "email": "charlie@example.com"
}
```

## Error Responses

All errors follow this format:

```json
{
  "error": "Error message",
  "code": "ERROR_CODE"
}
```
