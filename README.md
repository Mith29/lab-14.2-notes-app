# Notes App

A secure backend service built with Node.js, Express, and MongoDB that supports:

- Local Authentication (Email & Password)
- GitHub OAuth Authentication
- Private Notes CRUD API
- JWT Authentication & Authorization

---

## Project Structure


project-root/
│
├── config/
│ ├── connection.js
│ └── passport.js
│
├── models/
│ ├── User.js
│ └── Notes.js
│
├── routes/
│ ├── userRoutes.js
│ └── noteRoutes.js
│
├── utils/
│ └── auth.js
│
├── .env
├── .gitignore
├── package.json
└── server.js


---

## Installation & Setup

### 1. Clone the repository

git clone <https://github.com/Mith29/lab-14.2-notes-app>
cd project-folder


### 2. Install dependencies

npm install


### 3. Create `.env` file

PORT=3000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key

GITHUB_CLIENT_ID=your_github_client_id
GITHUB_CLIENT_SECRET=your_github_client_secret
GITHUB_CALLBACK_URL=http://localhost:3000/api/users/auth/github/callback


---

## Run the Server


npm run dev


Server runs at:

http://localhost:3000


---

## Authentication

### Register
POST /api/users/register


{
"username": "bob",
"email": "bob@example.com
",
"password": "pass1234"
}


---

### Login
POST /api/users/login

Response:

{
"token": "...",
"user": {...}
}


---

## GitHub OAuth

Start login:

GET /api/users/auth/github


Callback:

GET /api/users/auth/github/callback


Redirect result:

http://localhost:3000/success?token=YOUR_TOKEN


---

## Notes API (Protected)

All routes require:

Authorization: Bearer <token>


### Create Note

POST /api/notes


### Get All Notes

GET /api/notes


### Get Single Note

GET /api/notes/:id


### Update Note

PUT /api/notes/:id


### Delete Note

DELETE /api/notes/:id


---

## Security Features

- Password hashing using bcrypt  
- JWT-based authentication  
- Protected routes with middleware  
- Authorization (users access only their own notes)  
- Environment variables for sensitive data  
- `.gitignore` for security  

---

## Testing Tools

- Postman  
- Thunder Client  