# Login Backend

Login Backend is a Node.js application built with Express and MongoDB for managing user authentication through a RESTful API.


## Installation

To run this project locally, follow these steps:

1. **Clone the repository:**

   ```bash
   git clone https://github.com/pritamkumarbishwas/login_backend.git
   cd login_backend
   npm install
   npm run dev
   
## API Routes

Base URL: `https://login-assignment-4v4o.onrender.com/api/v1/users`

### Register a User
- **POST** `/register`
  - Registers a new user.
  - Request body should include:
    ```json
    {
        "fullName": "Your Full Name",
        "email": "your_email@example.com",
        "password": "YourPassword"
    }
    ```
  - Example:
    ```bash
    curl -X POST https://login-assignment-4v4o.onrender.com/api/v1/users/register \
      -H "Content-Type: application/json" \
      -d '{
        "fullName": "test",
        "email": "test4@gmail.com",
        "password": "test"
      }'
    ```

### Login
- **POST** `/login`
  - Logs in a user with provided credentials.
  - Request body should include:
    ```json
    {
        "email": "your_email@example.com",
        "password": "YourPassword"
    }
    ```
  - Example:
    ```bash
    curl -X POST https://login-assignment-4v4o.onrender.com/api/v1/users/login \
      -H "Content-Type: application/json" \
      -d '{
        "email": "test1@gmail.com",
        "password": "test"
      }'
    ```

### Logout (secured route)
- **POST** `/logout`
  - Logs out the currently authenticated user.
  - Requires authentication token passed as a bearer token in the Authorization header.
  - Example:
    ```bash
    curl -X POST https://login-assignment-4v4o.onrender.com/api/v1/users/logout \
      -H "Authorization: Bearer YOUR_AUTH_TOKEN"
    ```


## Environment Variables

Make sure to create a `.env` file in the root directory of your project and add the following environment variables:

- **PORT:** Port number on which the server will run.

- **MONGODB_URI:** MongoDB connection URI for your database.

- **CORS_ORIGIN:** CORS origin configuration to allow cross-origin requests.

- **ACCESS_TOKEN_SECRET:** Secret key used to sign JWT access tokens.

- **ACCESS_TOKEN_EXPIRY:** Expiry duration for access tokens.
  
- **REFRESH_TOKEN_SECRET:** Secret key used to sign JWT refresh tokens.
  
- **REFRESH_TOKEN_EXPIRY:** Expiry duration for refresh tokens.


### Instructions:

1. Create a `.env` file in the root directory of your project if it doesn't exist.
2. Copy and paste the above environment variables into the `.env` file.
3. Replace placeholder values (`username`, `password`, etc.) with your actual MongoDB credentials and desired token secrets.
4. Ensure the `.env` file is added to your `.gitignore` to keep sensitive information secure.


