# CS For Beginners

A web application designed to help beginners learn programming languages and computer science concepts. This project features user authentication, course browsing, and course request functionality, with a MongoDB backend.

---

## Features

- User registration and login (with JWT authentication)
- Browse available programming courses
- Request new courses
- Responsive UI with HTML, CSS, and JavaScript
- Email notifications (via Nodemailer)
- MongoDB database integration

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/)
- [MongoDB](https://www.mongodb.com/) (local or Atlas)
- [npm](https://www.npmjs.com/)

### Installation

1. **Clone the repository:**
    ```bash
    git clone https://github.com/Ariz253/CS-FOR-BEGINNERS.git
    cd CS-FOR-BEGINNERS
    ```
i
2. **Install dependencies:**
    ```bash
    npm install
    ```

3. **Set up environment variables:**
    - Copy `.env.example` to `.env` and fill in your credentials:
      ```
      EMAIL=your_email_here
      PASSWORD=your_email_app_password_here
      MONGODB_URI=your_mongodb_uri_here
      ```

4. **Start the server:**
    ```bash
    node serverfinal.js
    ```
    The server will run on `http://localhost:3013` by default.Feel free to change the port no if needed

---

## Database Schema

The application uses MongoDB with Mongoose. The main schema is for users:

```js
const userSchema = new mongoose.Schema({
    username: {
        type: String,
        required: true,
    },
    email: {
        type: String,
        required: true,
        unique: true,
    },
    password: {
        type: String,
        required: true,
    },
    requestedCourses: {
        type: [String],
        default: [],
    }
}, { timestamps: true });
```

- **username**: User’s display name (String, required)
- **email**: User’s email address (String, required, unique)
- **password**: Hashed password (String, required)
- **requestedCourses**: Array of course names the user has requested (Array of Strings)
- **timestamps**: Automatically adds `createdAt` and `updatedAt` fields

---

## Project Structure

```
.
├── css/                # Stylesheets
├── img/                # Images and icons
├── js/                 # JavaScript files (if any)
├── serverfinal.js      # Main backend server file
├── package.json
├── .env.example
├── .gitignore
├── README.md
└── ... (HTML files)
```

---

## Environment Variables

The following environment variables are required (see `.env.example`):

- `EMAIL`: Email address for sending notifications
- `PASSWORD`: App password for the email account
- `MONGODB_URI`: MongoDB connection string

---


## License

[ISC](LICENSE)

---

## Author
Ariz Ejaz Khan