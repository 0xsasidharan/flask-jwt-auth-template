

# 🛡️ Flask JWT Auth API Template

A beginner-friendly Flask API boilerplate for user registration, login, JWT authentication, logout with token blacklisting, and user management.

---

## 🚧 Project Progress Checklist

| No | Feature / Task                             | Status    |
| -- | ------------------------------------------ | --------- |
| 1  | Set up Flask-JWT-Extended in app config    | ✅ Done    |
| 2  | Create `UserModel` and `UserSchema`        | ✅ Done    |
| 3  | Build `/register` route with password hash | ✅ Done    |
| 4  | Create `/login` route with token return    | ✅ Done    |
| 5  | Protect routes with `@jwt_required()`      | ✅ Done    |
| 6  | Add custom claims / user identity logic    | ⬜ Pending |
| 7  | Implement logout and token blacklist       | ✅ Done    |
| 8  | Add refresh token support                  | ⬜ Pending |
| 9  | Test full auth flow in Postman/Insomnia    | ⬜ Pending |

---

## 🔑 Endpoints

| Method | Endpoint          | Description             | Auth Required |
| ------ | ----------------- | ----------------------- | ------------- |
| POST   | `/register`       | Register a new user     | ❌ No          |
| POST   | `/login`          | Login and get JWT token | ❌ No          |
| POST   | `/logout`         | Logout user (blacklist) | ✅ Yes         |
| GET    | `/user/<user_id>` | Get user by ID          | ❌ No          |
| DELETE | `/user/<user_id>` | Delete user by ID       | ❌ No          |
| GET    | `/test`           | Test protected route    | ✅ Yes         |

---


## ✅ Example Usage

### 📝 Register a New User

**POST /register**

```json
{
  "username": "arun",
  "password": "securepassword"
}
```

**Response**

```json
{
  "message": "User has been created successfully"
}
```

---

### 🔐 Login

**POST /login**

```json
{
  "username": "arun",
  "password": "securepassword"
}
```

**Response**

```json
{
  "access_token": "<JWT_TOKEN_HERE>"
}
```

---

### 🚪 Logout

**POST /logout**

> Requires Authorization header: `Bearer <JWT_TOKEN>`

**Response**

```json
{
  "message": "User Logged out successfully"
}
```

---



### 🧪 Test Auth-Protected Route

**GET /test** 


#### ✅ Example Response

```json
{
  "message": "Auth Checked"
}
```

---

### 🔐 Example Usage with JWT Token

#### 🧰 Using `curl`:

```bash
curl -X GET http://localhost:5000/test \
  -H "Authorization: Bearer YOUR_JWT_TOKEN_HERE"
```

#### 🧪 Using Postman:

1. Set method: `GET`
2. URL: `http://localhost:5000/test`
3. Go to **Headers** tab:

   * Key: `Authorization`
   * Value: `Bearer YOUR_JWT_TOKEN_HERE`

> Replace `YOUR_JWT_TOKEN_HERE` with your actual token.
