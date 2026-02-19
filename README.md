# ahjoorxmr-backend

A NestJS backend application with comprehensive logging, error handling, and health monitoring.

## Features

- **Global Exception Handling**: Centralized error handling with detailed logging
- **Request/Response Logging**: Automatic logging of all HTTP requests
- **Response Transformation**: Consistent API response format
- **Health Checks**: Health and readiness endpoints for monitoring
- **Validation**: Request validation using class-validator
- **Winston Logging**: Structured logging with Winston
- **CORS Support**: Configurable CORS settings

## API Endpoints

### Root
- `GET /` - Returns a welcome message

### Health
- `GET /health` - Application health status
- `GET /health/ready` - Application readiness status

## Project Setup

```bash
# Install dependencies
npm install

# Copy environment file
cp .env.example .env
```

## Running the Application

```bash
# Development
npm run start:dev

# Production
npm run start:prod

# Debug mode
npm run start:debug
```

## Testing

```bash
# Unit tests
npm run test

# E2E tests
npm run test:e2e

# Test coverage
npm run test:cov
```

## Environment Variables

See `.env.example` for all available environment variables.

## Architecture

- **Common Module**: Shared utilities, filters, interceptors, and DTOs
- **Health Module**: Health check endpoints
- **Global Configuration**: Validation, logging, and error handling setup

## Response Format

All successful API responses follow this format:

```json
{
  "data": "response data",
  "statusCode": 200,
  "message": "Success",
  "timestamp": "2024-01-01T00:00:00.000Z"
}
```

Error responses follow this format:

```json
{
  "statusCode": 400,
  "error": "Bad Request",
  "message": "Validation failed",
  "timestamp": "2024-01-01T00:00:00.000Z",
  "path": "/api/endpoint"
}
```