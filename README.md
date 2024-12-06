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
├── src
│   ├── users
│   │   ├── dto
│   │   │   ├── create-user.dto.ts
│   │   │   ├── update-user.dto.ts
│   │   ├── schemas
│   │   │   └── user.schema.ts
│   │   ├── users.controller.ts
│   │   ├── users.module.ts
│   │   ├── users.service.ts
│   │   ├── users.repository.ts
│   ├── app.module.ts
├── .env
├── package.json
└── README.md
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




