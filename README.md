
# MongoDB Authentication and Authorization API

This project is a Node.js application that provides authentication and authorization functionalities using MongoDB. It includes user registration, login, token refresh, and role-based access control.

## Project Structure

```
.env
.gitignore
config/
    allowedOrigins.js
    corsOptions.js
    dbConnect.js
    roles_list.js
controllers/
    authController.js
    employeesController.js
    logoutController.js
    refreshTokenController.js
    registerController.js
logs/
    errLog.txt
    reqLog.txt
middleware/
    credentials.js
    errorHandler.js
    logEvents.js
    verifyJWT.js
    verifyRoles.js
model/
    Employee.js
    employees.json
    User.js
    users.json
package.json
public/
    css/
    img/
    text/
routes/
    api/
        employees.js
    auth.js
    logout.js
    refresh.js
    register.js
    root.js
server.js
views/
    404.html
    index.html
```

## Features

- User registration and login
- JWT-based authentication
- Role-based access control
- Token refresh
- Logging of requests and errors

## Installation

1. Clone the repository:
    ```sh
    git clone <repository-url>
    cd repository-name
    ```

2. Install dependencies:
    ```sh
    npm install
    ```

3. Create a `.env` file in the root directory and add the following environment variables:
    ```
    DATABASE_URI=your_mongodb_connection_string
    ACCESS_TOKEN_SECRET=your_access_token_secret
    REFRESH_TOKEN_SECRET=your_refresh_token_secret
    ```

4. Start the server:
    ```sh
    npm run dev
    ```

## API Endpoints

### Public Routes

- `POST /register` - Register a new user
- `POST /auth` - Login and get access token
- `GET /refresh` - Refresh access token
- `GET /logout` - Logout and clear refresh token

### Protected Routes

- `GET /employees` - Get all employees
- `POST /employees` - Create a new employee
- `PUT /employees` - Update an employee
- `DELETE /employees` - Delete an employee
- `GET /employees/:id` - Get an employee by ID

## Middleware

- `logger` - Logs all incoming requests
- `credentials` - Handles credentials for CORS
- `cors` - Handles Cross-Origin Resource Sharing
- `express.json` - Parses incoming JSON requests
- `cookieParser` - Parses cookies
- `verifyJWT` - Verifies JWT tokens
- `verifyRoles` - Verifies user roles
- `errorHandler` - Handles errors

## Models

- `User` - User schema with username, roles, password, and refresh tokens
- `Employee` - Employee schema with firstname and lastname

## Logging

- `logEvents` - Logs events to files
- `errLog.txt` - Error log file
- `reqLog.txt` - Request log file

## License

This project is licensed under the ISC License.

