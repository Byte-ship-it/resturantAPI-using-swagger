# Restaurant API

This is a Restaurant API built using Node.js and TypeScript. The API provides endpoints for managing restaurant operations such as menus, orders, waiters, and billing. It utilizes Swagger for API documentation.

## Features

- **User Authentication**: Authentication middleware to protect routes.
- **CRUD Operations**: Create, Read, Update, and Delete operations for menus, orders, waiters, and bills.
- **MongoDB Integration**: Uses MongoDB for data storage.
- **Swagger Documentation**: Interactive API documentation.

## Getting Started

### Prerequisites

- Node.js (>=14.x)
- npm (>=6.x)
- MongoDB

### Installation

1. Clone the repository:
    ```sh
    git clone <repository-url>
    cd ResturantAPI_Using-Swagger-main
    ```

2. Install the dependencies:
    ```sh
    npm install
    ```

3. Set up the environment variables:
    Create a `.env` file in the root directory and add the following variables:
    ```env
    MONGO_URI=<Your MongoDB URI>
    JWT_SECRET=<Your JWT Secret>
    ```

### Running the Application

To start the application, run:
```sh
npm start
```

The API will be available at `http://localhost:3000`.

### API Documentation

The API documentation is available at `http://localhost:3000/api-docs`. It is generated using Swagger.

## Project Structure

- **src/config**: Configuration files.
- **src/controllers**: API controllers for handling requests.
- **src/middleware**: Middleware for request processing.
- **src/models**: Mongoose models for MongoDB.
- **src/repositories**: Data access logic.
- **src/routes**: Route definitions.
- **src/types**: TypeScript type definitions.
- **src/utills**: Utility functions.

## API Documentation

### Authentication

| Method | Endpoint | Description | Request Body | Responses |
|--------|----------|-------------|--------------|-----------|
| POST | /login | Authenticate a user and generate a JWT token | `{ "username": "string", "password": "string" }` | `200 OK`: Returns JWT token <br> `401 Unauthorized`: Invalid credentials |

### Menu

| Method | Endpoint | Description | Request Body | Responses |
|--------|----------|-------------|--------------|-----------|
| GET | /menu | Get the list of all menu items | N/A | `200 OK`: Returns a list of menu items |
| POST | /menu | Create a new menu item | `{ "name": "string", "price": "number", "category": "string" }` | `201 Created`: Menu item created successfully <br> `400 Bad Request`: Invalid request data |
| PUT | /menu/{id} | Update an existing menu item | `{ "name": "string", "price": "number", "category": "string" }` | `200 OK`: Menu item updated successfully <br> `404 Not Found`: Menu item not found |
| DELETE | /menu/{id} | Delete a menu item | N/A | `200 OK`: Menu item deleted successfully <br> `404 Not Found`: Menu item not found |

### Orders

| Method | Endpoint | Description | Request Body | Responses |
|--------|----------|-------------|--------------|-----------|
| GET | /orders | Get the list of all orders | N/A | `200 OK`: Returns a list of orders |
| POST | /orders | Create a new order | `{ "tableNumber": "number", "items": [ { "menuItemId": "string", "quantity": "number" } ] }` | `201 Created`: Order created successfully <br> `400 Bad Request`: Invalid request data |
| PUT | /orders/{id} | Update an existing order | `{ "tableNumber": "number", "items": [ { "menuItemId": "string", "quantity": "number" } ] }` | `200 OK`: Order updated successfully <br> `404 Not Found`: Order not found |
| DELETE | /orders/{id} | Delete an order | N/A | `200 OK`: Order deleted successfully <br> `404 Not Found`: Order not found |

### Waiters

| Method | Endpoint | Description | Request Body | Responses |
|--------|----------|-------------|--------------|-----------|
| GET | /waiters | Get the list of all waiters | N/A | `200 OK`: Returns a list of waiters |
| POST | /waiters | Create a new waiter | `{ "name": "string", "age": "number" }` | `201 Created`: Waiter created successfully <br> `400 Bad Request`: Invalid request data |
| PUT | /waiters/{id} | Update an existing waiter | `{ "name": "string", "age": "number" }` | `200 OK`: Waiter updated successfully <br> `404 Not Found`: Waiter not found |
| DELETE | /waiters/{id} | Delete a waiter | N/A | `200 OK`: Waiter deleted successfully <br> `404 Not Found`: Waiter not found |

### Bills

| Method | Endpoint | Description | Request Body | Responses |
|--------|----------|-------------|--------------|-----------|
| GET | /bills | Get the list of all bills | N/A | `200 OK`: Returns a list of bills |
| POST | /bills | Create a new bill | `{ "orderId": "string", "amount": "number" }` | `201 Created`: Bill created successfully <br> `400 Bad Request`: Invalid request data |
| PUT | /bills/{id} | Update an existing bill | `{ "orderId": "string", "amount": "number" }` | `200 OK`: Bill updated successfully <br> `404 Not Found`: Bill not found |
| DELETE | /bills/{id} | Delete a bill | N/A | `200 OK`: Bill deleted successfully <br> `404 Not Found`: Bill not found |

## Available Scripts

- `npm start`: Start the application.
- `npm run dev`: Start the application in development mode with hot-reloading.
- `npm run build`: Compile the TypeScript code.
- `npm test`: Run tests.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

