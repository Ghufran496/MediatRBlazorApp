# MediatR Blazor Application

A demonstration project showcasing the implementation of the Mediator pattern using MediatR in a .NET solution with Blazor UI and Web API.

## Project Overview

This application demonstrates the CQRS (Command Query Responsibility Segregation) pattern implementation using MediatR in a .NET 7 solution. It consists of three main projects:

1. **BlazorUI** - A server-side Blazor application that serves as the front-end
2. **DemoApi** - A RESTful API built with ASP.NET Core
3. **demoLibrary** - A class library containing shared models, commands, queries, and handlers

## Technology Stack

- **.NET 7** - The core framework
- **Blazor Server** - For the web UI
- **ASP.NET Core Web API** - For the backend API
- **MediatR (v9.0.0)** - For implementing the mediator pattern
- **Swagger/OpenAPI** - For API documentation

## Architecture

The solution follows the CQRS pattern with MediatR:

### Core Components

- **Commands** - Represent operations that change state (e.g., `InsertPersonCommand`)
- **Queries** - Represent operations that retrieve data (e.g., `GetPersonListQuery`, `GetPersonByIdQuery`)
- **Handlers** - Process commands and queries (e.g., `InsertPersonHandler`, `GetPersonListHandler`, `GetPersonByIdHandler`)
- **Models** - Data structures shared across the application (e.g., `PersonModel`)

### Project Structure

- **demoLibrary/**
  - Commands/ - Contains command definitions
  - Queries/ - Contains query definitions
  - Handlers/ - Contains handlers for commands and queries
  - Models/ - Contains data models
  - DataAccess/ - Contains data access interfaces and implementations

- **BlazorUI/**
  - Pages/ - Blazor pages that use MediatR to communicate with the backend

- **DemoApi/**
  - Controllers/ - API controllers that use MediatR to process requests

## Key Features

- **Decoupled Architecture** - Business logic is separated from UI and API layers
- **CQRS Pattern** - Clear separation between read and write operations
- **Dependency Injection** - Proper use of DI throughout the application
- **Clean Code** - Modern C# features like records for immutable command/query objects

## Getting Started

1. Clone the repository
2. Open the solution in Visual Studio 2022 or later
3. Set the startup projects to both BlazorUI and DemoApi
4. Run the application

## API Endpoints

The API provides the following endpoints:

- `GET /api/Person` - Get all persons
- `GET /api/Person/Details/{id}` - Get a person by ID
- `POST /api/Person/Create` - Create a new person

## Implementation Details

The application demonstrates:

1. Using MediatR for in-process messaging
2. Record types for commands and queries
3. Proper separation of concerns
4. Integration between Blazor UI and API through MediatR 