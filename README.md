# User Management REST API

A robust RESTful API for user management built with Node.js, Express, and MongoDB. This API provides secure user authentication, CRUD operations, and follows best practices for security and performance.

## Features

- 🔐 JWT-based Authentication
- 👥 User Management (CRUD operations)
- 🔒 Password Hashing with bcrypt
- 🛡️ Security Middleware (Helmet, CORS, Rate Limiting)
- 📝 API Documentation with Swagger
- 🎯 Error Handling
- 📊 MongoDB Integration
- 🚀 Performance Optimizations

## Prerequisites

- Node.js (v14 or higher)
- MongoDB
- npm or yarn

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd api-project
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file in the root directory with the following variables:
```env
PORT=3000
MONGODB_URI=mongodb://localhost:27017/user-management
JWT_SECRET=your_jwt_secret_key
JWT_EXPIRES_IN=24h
```

4. Start the server:
```bash
npm start
```

For development with auto-reload:
```bash
npm run dev
```

## API Documentation

### Authentication

#### Login
```http
POST /api/auth/login
Content-Type: application/json

{
    "email": "user@example.com",
    "password": "password123"
}
```

Response:
```json
{
    "status": "success",
    "data": {
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
        "user": {
            "id": "user_id",
            "name": "User Name",
            "email": "user@example.com"
        }
    }
}
```

### User Management

#### Create User
```http
POST /api/users
Content-Type: application/json

{
    "name": "John Doe",
    "email": "john@example.com",
    "phone": "1234567890",
    "password": "password123"
}
```

#### Get All Users
```http
GET /api/users
Authorization: Bearer <token>
```

#### Get User by ID
```http
GET /api/users/:id
Authorization: Bearer <token>
```

#### Update User
```http
PUT /api/users/:id
Authorization: Bearer <token>
Content-Type: application/json

{
    "name": "Updated Name",
    "phone": "9876543210"
}
```

#### Delete User
```http
DELETE /api/users/:id
Authorization: Bearer <token>
```

## Error Handling

The API uses standard HTTP status codes and returns errors in the following format:

```json
{
    "status": "error",
    "message": "Error description"
}
```

Common status codes:
- 200: Success
- 201: Created
- 400: Bad Request
- 401: Unauthorized
- 404: Not Found
- 500: Internal Server Error

## Security Features

- Password hashing using bcrypt
- JWT-based authentication
- Rate limiting to prevent abuse
- CORS enabled
- Helmet for security headers
- Input validation
- Error handling middleware

## Development

### Project Structure
```
api-project/
├── src/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   ├── docs/
│   └── app.js
├── .env
├── package.json
└── README.md
```

### Available Scripts

- `npm start`: Start the server
- `npm run dev`: Start the server with nodemon for development
- `npm test`: Run tests
- `npm run lint`: Run ESLint

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support, email support@example.com or create an issue in the repository. 