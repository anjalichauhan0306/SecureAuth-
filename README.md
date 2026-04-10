## 🔐 Secure Authentication System

This project implements a robust and secure authentication system using modern best practices to ensure user data protection and controlled access.

### 🚀 Features

- **JWT-based Authentication**
  - Secure token-based login system
  - Stateless authentication for scalability

- **Role-Based Authorization**
  - Supports multiple user roles (Admin, Educator, Student)
  - Access control based on user roles

- **Password Security**
  - Passwords are hashed using bcrypt before storing in database
  - Prevents plain-text password storage

- **Protected Routes**
  - Backend routes are secured using middleware
  - Only authenticated users can access protected APIs

- **Token Verification Middleware**
  - Validates JWT on every request
  - Prevents unauthorized access

- **Session Handling**
  - Tokens stored securely on client-side
  - Auto logout on token expiry

---

### ⚙️ Tech Stack Used

- Node.js
- Express.js
- MongoDB
- JWT (jsonwebtoken)
- bcrypt.js

---

### 🔄 Authentication Flow

1. User registers with email & password
2. Password is hashed using bcrypt
3. User logs in → JWT token is generated
4. Token is sent to client
5. Client sends token in headers for protected routes
6. Middleware verifies token and grants access

---

### 🔒 Security Best Practices Implemented

- Password hashing using bcrypt
- JWT expiration handling
- Role-based access control (RBAC)
- Protected API routes using middleware
- Environment variables for sensitive data

---

### 📌 Example Protected Route

```js
router.get("/dashboard", verifyToken, (req, res) => {
  res.json({ message: "Authorized access" });
});