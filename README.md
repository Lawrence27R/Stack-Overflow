<div align="center">

# 📚 Stack Overflow Clone

### A full-stack MERN clone of Stack Overflow — Ask questions, post answers, vote, and manage your developer profile

[![GitHub Repo](https://img.shields.io/badge/GitHub-Stack--Overflow-181717?style=for-the-badge&logo=github)](https://github.com/Lawrence27R/Stack-Overflow)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![Express](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)](https://expressjs.com/)

</div>

---

## 📖 About The Project

**Stack Overflow Clone** is a full-stack web application built with the **MERN stack** (MongoDB, Express.js, React, Node.js) that replicates the core features of Stack Overflow. Users can register, log in, post questions, submit answers, vote on content, explore tags, and manage their profiles — all in a clean, familiar interface.

---

## ✨ Features

### 🔐 Authentication
- User **Sign Up** and **Login** with email & password
- Password hashing with **bcryptjs**
- **JWT-based** authentication with 1-hour token expiry
- Auth middleware for protected API routes

### ❓ Questions
- Post new questions with title, body, and tags
- View all questions on the home feed
- View a single question with all its answers
- **Upvote / Downvote** questions
- Delete your own questions

### 💬 Answers
- Post answers to any question
- **Upvote / Downvote** answers
- Delete your own answers

### 🏷️ Tags
- Browse all question tags
- View questions filtered by tag

### 👤 Users & Profiles
- Browse all registered users
- View individual user profiles
- Profile page shows user's questions and activity

### 🧭 Navigation
- Persistent **Navbar** with search bar and auth state
- **Left Sidebar** for quick navigation (Home, Questions, Tags, Users)
- **Right Sidebar** with helpful info and links

---

## 🛠️ Tech Stack

### Frontend (Client)
| Technology | Purpose |
|---|---|
| **React 18** | UI Framework |
| **React Router DOM v6** | Client-side routing |
| **Redux + Redux Thunk** | Global state management |
| **Axios** | HTTP requests to backend API |
| **jwt-decode** | Decode JWT tokens on client |
| **Moment.js** | Date formatting |
| **react-copy-to-clipboard** | Copy code snippets |

### Backend (Server)
| Technology | Purpose |
|---|---|
| **Node.js** | JavaScript runtime |
| **Express.js** | Web framework / REST API |
| **MongoDB + Mongoose** | Database & ODM |
| **bcryptjs** | Password hashing |
| **jsonwebtoken (JWT)** | Authentication tokens |
| **dotenv** | Environment variable management |
| **cors** | Cross-origin resource sharing |
| **nodemon** | Development auto-restart |

---

## 📁 Project Structure

```
Stack-Overflow/
├── client/                         # React Frontend
│   ├── public/
│   └── src/
│       ├── Pages/
│       │   ├── Home/               # Home feed with all questions
│       │   ├── Auth/               # Login & Signup page
│       │   ├── AskQuestion/        # Ask a new question
│       │   ├── Questions/          # Question list & single question view
│       │   ├── Tags/               # Tags browser
│       │   ├── Users/              # All users list
│       │   └── UserProfile/        # Individual user profile
│       ├── components/
│       │   ├── Navbar/             # Top navigation bar
│       │   ├── LeftSidebar/        # Left navigation sidebar
│       │   ├── RightSidebar/       # Right info sidebar
│       │   ├── HomeMainbar/        # Main content area
│       │   ├── Avatar/             # User avatar component
│       │   └── Button/             # Reusable button component
│       ├── actions/                # Redux action creators
│       ├── api/                    # Axios API call functions
│       ├── reducers/               # Redux reducers
│       ├── assets/                 # Static images & icons
│       ├── AllRoutes.jsx           # All app routes definition
│       ├── App.js                  # Root app component
│       └── index.js                # React DOM entry point
│
├── server/                         # Node.js + Express Backend
│   ├── controllers/
│   │   ├── auth.js                 # Signup & Login logic
│   │   ├── Questions.js            # CRUD + vote for questions
│   │   ├── Answers.js              # Post & vote on answers
│   │   └── users.js                # Fetch all / single users
│   ├── models/
│   │   ├── auth.js                 # User Mongoose schema
│   │   └── Questions.js            # Question Mongoose schema
│   ├── routes/
│   │   ├── users.js                # /user routes
│   │   ├── Questions.js            # /questions routes
│   │   └── Answers.js              # /answer routes
│   ├── middleware/
│   │   └── auth.js                 # JWT auth middleware
│   ├── index.js                    # Express app entry point
│   ├── Procfile                    # Heroku deployment config
│   └── .gitignore                  # Ignores .env & node_modules
│
└── README.md
```

---

## 🔌 API Endpoints

### Auth Routes — `/user`
| Method | Endpoint | Description | Auth |
|---|---|---|---|
| POST | `/user/signup` | Register a new user | ❌ |
| POST | `/user/login` | Login and get JWT token | ❌ |
| GET | `/user/get` | Get all users | ❌ |
| PATCH | `/user/:id` | Update user profile | ✅ |

### Question Routes — `/questions`
| Method | Endpoint | Description | Auth |
|---|---|---|---|
| GET | `/questions` | Get all questions | ❌ |
| POST | `/questions/Ask` | Post a new question | ✅ |
| DELETE | `/questions/:id` | Delete a question | ✅ |
| PATCH | `/questions/:id/vote` | Upvote / Downvote | ✅ |

### Answer Routes — `/answer`
| Method | Endpoint | Description | Auth |
|---|---|---|---|
| PATCH | `/answer/:id/post` | Post an answer | ✅ |
| DELETE | `/answer/:id/delete` | Delete an answer | ✅ |
| PATCH | `/answer/:id/vote` | Upvote / Downvote | ✅ |

---

## 🚀 Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) v14+
- [MongoDB](https://www.mongodb.com/) (local or Atlas)
- npm

### 1. Clone the Repository

```bash
git clone https://github.com/Lawrence27R/Stack-Overflow.git
cd Stack-Overflow
```

### 2. Setup the Server

```bash
cd server
npm install
```

Create a `.env` file in the `server/` directory:

```env
CONNECTION_URL=your_mongodb_connection_string
JWT_SECRET=your_super_secret_jwt_key
PORT=5000
```

Start the server:

```bash
npm start
```

Server runs at: [http://localhost:5000](http://localhost:5000)

### 3. Setup the Client

```bash
cd ../client
npm install
npm start
```

Client runs at: [http://localhost:3000](http://localhost:3000)

---

## 🔐 Environment Variables

Create a `server/.env` file with the following:

```env
# MongoDB Connection String (use MongoDB Atlas for cloud)
CONNECTION_URL=mongodb+srv://<username>:<password>@cluster.mongodb.net/stackoverflow

# JWT Secret (use a long random string)
JWT_SECRET=your_random_secret_key

# Server Port (optional, defaults to 5000)
PORT=5000
```

> ⚠️ **Never commit your `.env` file.** It is already listed in `server/.gitignore`.

---

## 🌐 Pages & Routes

| Route | Page | Description |
|---|---|---|
| `/` | Home | All questions feed |
| `/Auth` | Auth | Login & Sign Up |
| `/AskQuestion` | Ask Question | Post a new question |
| `/Questions` | Questions | Browse all questions |
| `/Questions/:id` | Display Question | View question + answers |
| `/Tags` | Tags | Browse all tags |
| `/Users` | Users | All registered users |
| `/Users/:id` | User Profile | Individual user page |

---

## ☁️ Deployment

The server includes a `Procfile` for **Heroku** deployment.

```
web: node index.js
```

### Deploy Server to Heroku

```bash
# Login to Heroku
heroku login

# Create app
heroku create your-app-name

# Set environment variables
heroku config:set CONNECTION_URL=your_mongodb_atlas_uri
heroku config:set JWT_SECRET=your_jwt_secret

# Deploy
git push heroku main
```

### Deploy Client

```bash
cd client
npm run build
# Deploy the /build folder to Netlify, Vercel, or Firebase Hosting
```

---

## 🤝 Contributing

```bash
# 1. Fork the repository
# 2. Create your branch
git checkout -b feature/your-feature

# 3. Commit changes
git commit -m "Add: your feature"

# 4. Push
git push origin feature/your-feature

# 5. Open a Pull Request
```

---

## 📜 License

This project is licensed under the **ISC License**.

---
