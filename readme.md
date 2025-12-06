#  User Management API (Node.js + Express)

A simple REST API built using **Node.js** and **Express.js** that performs CRUD operations on an in-memory list of users.

## 🚀 Features

* Get all users
* Get a single user by ID
* Create a new user
* Replace an existing user using PUT
* Delete a user
* Request validation middleware
* Custom logging middleware
* Global error handling

## 🛠 Tech Stack

* **Node.js**
* **Express.js**
* **JavaScript**
* **Nodemon**

## 📂 Project Setup

### 1️⃣ Clone the repository
```bash
git clone https://github.com/dharmavirkumar/NodejsPro.git
````
### 2️⃣ Install dependencies

```bash
npm install
```

### 3️⃣ Start server

```bash
npm start
```

### Server runs at:

The API runs on:

```
http://localhost:8000
```
## 🔥 API Endpoints

## ➤ Get All Users

**GET** /users

- ✔ Returns list of all users
- ✔ Returns 404 if no users exist

- Response Example:
```json
[
  {
    "id": "1",
    "firstName": "John",
    "lastName": "Doe",
    "hobbies": ["reading"]
  }
]
```

## ➤ Get User by ID

**GET** /users/:id

- ✔ Returns the user
- ✔ Returns 404 if not found

## ➤ Create User

**POST** /user

- Required Body:
```json
{
  "firstName": "John",
  "lastName": "Doe",
  "hobbies": ["reading", "gaming"]
}
```
- ✔ Auto-generates ID
- ✔ 400 if fields missing

- Response:
```json
{
  "message": "User data added successfully",
  "data": {
    "id": "timestamp",
    "firstName": "John",
    "lastName": "Doe",
    "hobbies": ["reading", "gaming"]
  }
}
```
## ➤ Update User (Full Replace)

**PUT** /user/:id

- Replaces the entire object (true PUT).

## ➤ Delete User

**DELETE** /user/:id

- ✔ Deletes user
- ✔ Returns details of deleted user

## 🧩 Middlewares Used
- ✔ Request Logger
* Logs method, URL, status code.

- ✔ Field Validator
- Ensures:
* firstName
* lastName
* hobbies

are provided for POST and PUT.

- ✔ Global Error Handler

* Captures any server error:

{
  "error": "Internal Server Error"
}

## 📌 Important Notes

* Data is stored in an in-memory array, so it resets on server restart.
* PUT replaces entire resource.
* DELETE returns deleted user.

## 🧪 Testing

You can test API using:
* Postman
* Thunder Client (VS Code)