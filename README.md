# ForgeGate Identity

> A production-ready authentication and authorization service built with ASP.NET Core, implementing modern identity management, JWT authentication, role-based access control, and secure API practices.

![.NET](https://img.shields.io/badge/.NET-9.0-purple)
![ASP.NET Core](https://img.shields.io/badge/ASP.NET%20Core-Web%20API-blue)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-16-blue)
![Docker](https://img.shields.io/badge/Docker-Ready-2496ED)
![License](https://img.shields.io/badge/License-MIT-green)

---

# Overview

ForgeGate Identity is a standalone authentication and authorization service designed for modern applications and microservice architectures.

It centralizes user authentication, authorization, token management, permissions, and security features into a dedicated service that can be integrated with multiple applications.

The project demonstrates enterprise-level identity management while following Clean Architecture and security best practices.

---

# Features

## Authentication

* User Registration
* Secure Login
* Logout
* Password Reset
* Email Verification
* Change Password

## Authorization

* Role-Based Access Control (RBAC)
* Permission-Based Authorization
* Custom Policies
* Dynamic Permissions

## Token Management

* JWT Authentication
* Refresh Tokens
* Token Revocation
* Token Rotation
* Access Token Validation

## User Management

* User Profiles
* Account Activation
* Account Lockout
* Soft Delete
* User Status

## Security

* Password Hashing
* Secure Password Policies
* Brute Force Protection
* Login Attempt Tracking
* Audit Logs

## API Security

* API Keys
* CORS Configuration
* Rate Limiting
* Request Validation

---

# Architecture

```text
                 Client Applications
                        │
                Authentication API
                        │
──────────────────────────────────────────────
          Application Layer (CQRS)
──────────────────────────────────────────────
          Domain Layer (Business Rules)
──────────────────────────────────────────────
        Infrastructure Layer
          ├── PostgreSQL
          ├── Redis
          ├── Email Provider
          └── Logging
```

---

# Technology Stack

## Backend

* ASP.NET Core
* .NET 9
* C#

## Database

* PostgreSQL
* Entity Framework Core

## Authentication

* JWT
* Refresh Tokens
* ASP.NET Identity

## Architecture

* Clean Architecture
* CQRS
* Repository Pattern
* Dependency Injection

## Infrastructure

* Redis
* Docker
* Docker Compose
* Serilog

## Documentation

* Swagger / OpenAPI

## Testing

* xUnit
* FluentAssertions
* Integration Tests

---

# Folder Structure

```text
src/

├── ForgeGate.API
├── ForgeGate.Application
├── ForgeGate.Domain
├── ForgeGate.Infrastructure

tests/

├── ForgeGate.UnitTests
├── ForgeGate.IntegrationTests

docker/

docs/
```

---

# Security Features

* JWT Authentication
* Refresh Tokens
* Role Management
* Permission Management
* Password Hashing
* Email Verification
* Password Recovery
* Account Lockout
* Security Audit Logging
* Token Revocation

---

# Authentication Flow

```text
User
 │
 │ Login
 ▼
Identity API
 │
 │ Validate Credentials
 ▼
Database
 │
 │
 ▼
Generate JWT + Refresh Token
 │
 ▼
Client Stores Tokens
 │
 ▼
Authorized Requests
```

---

# Getting Started

## Prerequisites

* .NET SDK 9
* PostgreSQL
* Docker
* Redis

---

## Clone Repository

```bash
git clone https://github.com/yourusername/forgegate-identity.git

cd forgegate-identity
```

---

## Restore Packages

```bash
dotnet restore
```

---

## Apply Migrations

```bash
dotnet ef database update
```

---

## Run with Docker

```bash
docker compose up -d
```

---

## Start Application

```bash
dotnet run --project src/ForgeGate.API
```

---

# Configuration

Example `appsettings.json`

```json
{
  "ConnectionStrings": {
    "DefaultConnection": ""
  },

  "Jwt": {
    "Issuer": "",
    "Audience": "",
    "SecretKey": "",
    "ExpirationMinutes": 60
  },

  "Redis": {
    "ConnectionString": ""
  },

  "Email": {
    "Host": "",
    "Port": 587,
    "Username": "",
    "Password": ""
  }
}
```

---

# API Endpoints

## Authentication

* POST /api/auth/register
* POST /api/auth/login
* POST /api/auth/logout
* POST /api/auth/refresh
* POST /api/auth/forgot-password
* POST /api/auth/reset-password

## Users

* GET /api/users
* GET /api/users/{id}
* PUT /api/users/{id}
* DELETE /api/users/{id}

## Roles

* GET /api/roles
* POST /api/roles
* PUT /api/roles/{id}
* DELETE /api/roles/{id}

## Permissions

* GET /api/permissions
* POST /api/permissions
* Assign permissions to roles
* Assign permissions to users

---

# CI/CD

The project supports automated deployment pipelines with:

* Build Validation
* Unit Testing
* Integration Testing
* Docker Image Build
* Security Scanning
* Automated Deployment

---

# Roadmap

## Version 1.0

* User Authentication
* JWT Support
* Refresh Tokens
* Roles
* Permissions

## Version 2.0

* OAuth2 Integration
* OpenID Connect
* Multi-Factor Authentication
* API Keys

## Version 3.0

* Single Sign-On (SSO)
* Identity Federation
* External Providers
* Device Management

---

# Future Improvements

* Google Authentication
* GitHub Authentication
* Microsoft Authentication
* Two-Factor Authentication (2FA)
* Biometric Login Support
* WebAuthn / Passkeys
* OpenTelemetry Integration
* Distributed Session Management

---

# Screenshots

Coming Soon

```text
Login

User Management

Role Management

Permission Dashboard

Audit Logs
```

---

# Contributing

Contributions are welcome.

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Submit a Pull Request

---

# License

Licensed under the MIT License.

---

# Author

**Mostafa**

Backend Developer

* ASP.NET Core
* Identity & Security
* Clean Architecture
* Distributed Systems

---

# Acknowledgements

ForgeGate Identity was created as a reference implementation of modern authentication and authorization for enterprise applications. It demonstrates scalable architecture, secure coding practices, and production-ready identity management that can serve as the authentication backbone for SaaS platforms and distributed systems.
