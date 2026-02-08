# Cognivo-AI

A modern, AI-powered virtual assistant web application with voice recognition and speech synthesis capabilities. Built with React and Node.js, this application allows users to interact with a personalized virtual assistant through voice commands.

## Features

- 🎤 **Voice Recognition**: Real-time speech-to-text using Web Speech API
- 🔊 **Speech Synthesis**: Text-to-speech responses in Hindi
- 🤖 **AI-Powered**: Integrated with Google Gemini AI for intelligent responses
- 👤 **User Authentication**: Secure signup/signin with JWT tokens
- 🎨 **Customizable Assistant**: Personalize your assistant's name and image
- 📱 **Responsive Design**: Modern UI built with Tailwind CSS
- 📜 **Conversation History**: Track your interaction history
- 🔍 **Smart Actions**: 
  - Google search
  - YouTube search and play
  - Calculator
  - Social media (Instagram, Facebook)
  - Weather information
  - Time, date, day, and month queries

## Tech Stack

### Frontend
- **React 19** - UI library
- **Vite** - Build tool and dev server
- **Tailwind CSS** - Styling
- **React Router DOM** - Routing
- **Axios** - HTTP client
- **Web Speech API** - Voice recognition and synthesis

### Backend
- **Node.js** - Runtime environment
- **Express 5** - Web framework
- **MongoDB** - Database (via Mongoose)
- **JWT** - Authentication
- **Cloudinary** - Image storage
- **Google Gemini API** - AI integration
- **Multer** - File upload handling
- **Bcrypt** - Password hashing

## Project Structure

```
4.virtualAssistant/
├── backend/
│   ├── config/
│   │   ├── cloudinary.js      # Cloudinary configuration
│   │   ├── db.js              # MongoDB connection
│   │   └── token.js           # JWT token utilities
│   ├── controllers/
│   │   ├── auth.controllers.js    # Authentication logic
│   │   └── user.controllers.js    # User operations
│   ├── middlewares/
│   │   ├── isAuth.js          # Authentication middleware
│   │   └── multer.js          # File upload middleware
│   ├── models/
│   │   └── user.model.js      # User schema
│   ├── routes/
│   │   ├── auth.routes.js     # Authentication routes
│   │   └── user.routes.js     # User routes
│   ├── gemini.js              # Gemini AI integration
│   └── index.js               # Server entry point
└── frontend/
    ├── src/
    │   ├── components/        # Reusable components
    │   ├── context/           # React context (UserContext)
    │   ├── pages/             # Page components
    │   │   ├── Home.jsx       # Main assistant interface
    │   │   ├── SignIn.jsx     # Sign in page
    │   │   ├── SignUp.jsx     # Sign up page
    │   │   ├── Customize.jsx  # Assistant customization
    │   │   └── Customize2.jsx # Additional customization
    │   └── assets/            # Images and static files
    └── package.json
```

## Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v14 or higher)
- **npm** or **yarn**
- **MongoDB** (local or cloud instance like MongoDB Atlas)
- **Google Gemini API Key**
- **Cloudinary Account** (for image storage)

## Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd 4.virtualAssistant/4.virtualAssistant
   ```

2. **Install backend dependencies**
   ```bash
   cd backend
   npm install
   ```

3. **Install frontend dependencies**
   ```bash
   cd ../frontend
   npm install
   ```

## Configuration

### Backend Environment Variables

Create a `.env` file in the `backend` directory with the following variables:

```env
PORT=5000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
GEMINI_API_URL=your_gemini_api_endpoint
```

### Frontend Configuration

Update the `serverUrl` in `frontend/src/context/UserContext.jsx` to match your backend URL (default: `http://localhost:5000`).

## Running the Application

### Development Mode

1. **Start the backend server**
   ```bash
   cd backend
   npm run dev
   ```
   The server will run on `http://localhost:5000`

2. **Start the frontend development server**
   ```bash
   cd frontend
   npm run dev
   ```
   The frontend will run on `http://localhost:5173`

### Production Build

1. **Build the frontend**
   ```bash
   cd frontend
   npm run build
   ```

2. **The built files will be in `frontend/dist`**

## Usage

1. **Sign Up**: Create a new account with your name, email, and password
2. **Sign In**: Log in with your credentials
3. **Customize Assistant**: Set your assistant's name and upload an image
4. **Interact**: Use voice commands by saying your assistant's name followed by your request
   - Example: "Hey [Assistant Name], what's the weather today?"
   - Example: "Hey [Assistant Name], search for React tutorials on YouTube"

## API Endpoints

### Authentication
- `POST /api/auth/signup` - Register a new user
- `POST /api/auth/signin` - Login user
- `GET /api/auth/logout` - Logout user

### User
- `GET /api/user/current` - Get current user data
- `POST /api/user/update` - Update assistant name and image
- `POST /api/user/asktoassistant` - Send query to assistant

## Voice Commands Supported

The assistant can handle various types of commands:

- **General Questions**: Factual or informational queries
- **Google Search**: "Search for [query] on Google"
- **YouTube**: "Search for [query] on YouTube" or "Play [song/video]"
- **Calculator**: "Open calculator"
- **Social Media**: "Open Instagram" or "Open Facebook"
- **Weather**: "What's the weather today?"
- **Time/Date**: "What time is it?", "What's the date?", "What day is it?", "What month is it?"

## Browser Compatibility

- **Chrome/Edge**: Full support for Web Speech API
- **Safari**: Limited support
- **Firefox**: Limited support

**Note**: Voice recognition works best in Chrome/Edge browsers.

## Security Features

- Password hashing with bcrypt
- JWT-based authentication
- Secure cookie handling
- CORS configuration
- Protected routes with authentication middleware
