# User Service PRD

## Overview

The User Service manages user accounts, authentication, and authorization for the system.

## Objectives

- Provide secure user registration and login
- Store user profile information
- Handle basic permission management

## Technical Stack

- **Backend**: Java 17, Spring Boot 3.0
- **Database**: MongoDB
- **Authentication**: JWT (JSON Web Tokens)

## Functional Requirements

### User Registration

- Accept email, password, name, and optional profile information
- Validate email format and password strength
- Hash passwords securely before storage
- Send welcome email via Notification Service

### User Authentication

- Authenticate users with email/password
- Generate JWT tokens with appropriate expiration
- Support token refresh functionality

### User Profile Management

- Allow users to view and update their profile information
- Support password reset functionality

### Basic Authorization

- Define simple role-based permissions (USER, ADMIN)
- Provide API endpoint to verify user roles and permissions

## Data Schema

```
User {
  id: ObjectId
  email: String (unique)
  passwordHash: String
  name: String
  role: String (enum: USER, ADMIN)
  createdAt: Date
  updatedAt: Date
}
```

## API Endpoints

- POST /api/users/register - Create new user
- POST /api/users/login - Authenticate user
- GET /api/users/me - Get current user profile
- PUT /api/users/me - Update user profile
- PUT /api/users/password - Change password

## Success Metrics

- User registration completion rate > 80%
- Average login time < 1 second
- Authentication service uptime > 99.5%
