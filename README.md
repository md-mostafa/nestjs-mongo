# NestJS-Mongo

This is a basic NestJS application demonstrating how to set up and configure a MongoDB connection using Mongoose. It includes a `Users` module showcasing CRUD operations with a clean repository pattern.

## Features
- **MongoDB Connection**: Configured with Mongoose for seamless database interactions.
- **Modular Structure**: Follows NestJS best practices with a `Users` module.
- **Repository Pattern**: Abstracts database operations for better maintainability.
- **CRUD Operations**: Create, Read, Update users with a RESTful API.

---

## Prerequisites

- Node.js (v16+ recommended)
- MongoDB (local or cloud instance)
- NestJS CLI (optional for running commands)

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/nestjs-mongo.git
   cd nestjs-mongo
   ```

2. Install dependencies:
    ```bash
    yarn install
    ```

3. Set up environment variables: Create a .env file in the root directory and add your MongoDB connection string:
    ```bash
    MONGO_URI=mongodb://localhost:27017/nestjs-mongo
    ```

4. Run the application:
    ```bash
    yarn run start:dev
    ```

---
## Project Structure
nestjs-mongo
```
nestjs-mongo
├── src
│   ├── config                 # Configuration-related module
│   │   ├── config.module.ts   # Module definition for configuration
│   │   ├── config.service.ts  # Service to access environment variables
│   │   └── config.interface.ts # Optional: Interface for strongly-typed config values
│   ├── users                  # Users module
│   │   ├── dto                # Data Transfer Objects for validation
│   │   │   ├── create-user.dto.ts
│   │   │   └── update-user.dto.ts
│   │   ├── schemas            # MongoDB schemas
│   │   │   └── user.schema.ts
│   │   ├── users.controller.ts # Controller for handling HTTP requests
│   │   ├── users.module.ts     # Module definition for users
│   │   ├── users.repository.ts # Handles database operations
│   │   ├── users.service.ts    # Business logic for users
│   ├── app.module.ts          # Root module of the application
│   ├── main.ts                # Application entry point
├── test                       # End-to-end tests
│   └── app.e2e-spec.ts        # Example E2E test for the app
├── .env                       # Environment variables (excluded from version control)
├── .env.example               # Example environment variables file for developers
├── .gitignore                 # Ignored files in Git
├── package.json               # Project dependencies and scripts
├── tsconfig.json              # TypeScript configuration
├── README.md                  # Project documentation

```

---
## Key Files

### `users.repository.ts`
Handles all database interactions, including:
- `findOne`: Fetch a single user based on a filter query.
- `find`: Fetch multiple users based on a filter query.
- `create`: Add a new user to the database.
- `findOneAndUpdate`: Update an existing user based on a filter query.

### `users.controller.ts`
Defines API endpoints and handles incoming HTTP requests. It includes:
- `GET /users`: Fetch all users.
- `GET /users/:userId`: Fetch a user by ID.
- `POST /users`: Create a new user.
- `PATCH /users/:userId`: Update a user by ID.

### `users.service.ts`
Contains business logic and serves as a bridge between the controller and the repository. It:
- Handles data transformation if needed.
- Calls the repository methods for database operations.

### `user.schema.ts`
Defines the Mongoose schema for `User` objects. It includes:
- **Fields**: `email`, `age`, etc.
- **Schema validation**: Ensures data consistency.
- **Document structure**: Maps to MongoDB collections.




