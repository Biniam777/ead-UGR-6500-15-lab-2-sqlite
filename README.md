# PizzaStore API

A Minimal API implementation using ASP.NET Core, Entity Framework Core, and SQLite. This project demonstrates how to build a simple REST API for managing a pizza store, persisting data to a local SQLite database.

## Features

- **Minimal API**: Lightweight and fast API architecture using ASP.NET Core.
- **Entity Framework Core**: ORM for data access.
- **SQLite**: Lightweight, file-based relational database.
- **Swagger/OpenAPI**: Interactive API documentation.
- **CRUD Operations**: Create, Read, Update, and Delete operations for Pizza entities.

## Prerequisites

- [.NET 8.0 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)

## Getting Started

1. **Clone the repository** (if you haven't already):
   ```bash
   git clone <repository-url>
   cd ead-UGR-6500-15-lab-2-sqlite
   ```

2. **Navigate to the project directory**:
   ```bash
   cd PizzaStore
   ```

3. **Restore dependencies**:
   ```bash
   dotnet restore
   ```

4. **Run the application**:
   ```bash
   dotnet run
   ```

5. **Access the API**:
   - The application is configured to run on `http://localhost:5000`.
   - **Swagger UI**: Open your browser and navigate to [http://localhost:5000/swagger](http://localhost:5000/swagger) to explore and test the API endpoints interactively.

## API Endpoints

| Method | Endpoint | Description | Request Body (JSON) |
|--------|----------|-------------|---------------------|
| `GET` | `/` | Health check / Hello World | N/A |
| `GET` | `/pizzas` | Retrieve all pizzas | N/A |
| `GET` | `/pizza/{id}` | Retrieve a specific pizza by ID | N/A |
| `POST` | `/pizza` | Create a new pizza | `{"name": "string", "description": "string"}` |
| `PUT` | `/pizza/{id}` | Update an existing pizza | `{"name": "string", "description": "string"}` |
| `DELETE` | `/pizza/{id}` | Delete a pizza | N/A |

## Database

The project uses **SQLite** as the database provider.

- The database file `Pizzas.db` is located in the `PizzaStore` directory.
- Entity Framework Core migrations are used to manage the database schema.

### Managing Migrations

If you modify the `Pizza` model, you can update the database schema using the following commands:

1. **Create a new migration**:
   ```bash
   dotnet ef migrations add <MigrationName>
   ```

2. **Apply migrations to the database**:
   ```bash
   dotnet ef database update
   ```

## Project Structure

- `Program.cs`: Contains the application entry point, service configuration, and API route definitions.
- `Pizza.cs`: Defines the `Pizza` data model.
- `PizzaDb`: The `DbContext` class for Entity Framework Core.
- `Properties/launchSettings.json`: Configuration for launching the application (ports, environment variables).
