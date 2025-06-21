## 🛡️ Flask JWT Auth Template

A simple Flask API boilerplate for user registration, login (JWT), and user management.

---
## 🚧 Project Progress Checklist


| No | Feature / Task                             | Status    |
| --- | ------------------------------------------ | --------- |
| 1  | Set up Flask-JWT-Extended in app config    | ✅ Done    |
| 2  | Create `UserModel` and `UserSchema`        | ✅ Done    |
| 3  | Build `/register` route with password hash | ✅ Done    |
| 4  | Create `/login` route with token return    | ⬜ Pending |
| 5  | Protect routes with `@jwt_required()`      | ⬜ Pending |
| 6  | Add custom claims / user identity logic    | ⬜ Pending |
| 7  | Implement logout and token blacklist       | ⬜ Pending |
| 8  | Add refresh token support                  | ⬜ Pending |
| 9  | Test full auth flow in Postman/Insomnia    | ⬜ Pending |

---
### 🔑 Endpoints

| Method | Endpoint          | Description         |
| ------ | ----------------- | ------------------- |
| POST   | `/register`       | Register a new user |
| GET    | `/user/<user_id>` | Get user by ID      |
| DELETE | `/user/<user_id>` | Delete user by ID   |

---

### ✅ Example Request: Register

**POST /register**

```json
{
  "username": "sasi",
  "password": "securepassword"
}
```

**Response**

```json
{
  "message": "User has been created successfully"
}
```


