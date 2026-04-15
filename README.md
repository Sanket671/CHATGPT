# Advanced ChatGPT (RAG System with Real-Time Memory)

## Overview

A full-stack ChatGPT-like application built with React frontend and Node.js backend, featuring real-time messaging, user authentication, and AI-powered responses using Google's Gemini API.

## Features

- 🔐 User Authentication (Register/Login)
- 💬 Real-time chat using Socket.io
- 🧠 AI-powered responses with Google Gemini API
- 📝 Short-term memory (chat history)
- 🗄️ Long-term memory with Pinecone vector database
- 💾 Data persistence with MongoDB
- 🎨 Responsive React frontend

## Tech Stack

### Backend
- Node.js & Express.js
- MongoDB with Mongoose
- Socket.io for real-time communication
- JWT for authentication
- Google Gemini API for AI responses
- Pinecone for vector storage

### Frontend
- React.js with Hooks
- React Router for navigation
- Axios for API calls
- Socket.io-client for real-time features
- Tailwind CSS for styling

## Project Structure

```
chatgpt-project/
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   │   ├── auth.controller.js
│   │   │   └── chat.controller.js
│   │   ├── db/
│   │   │   └── db.js
│   │   ├── middlewares/
│   │   │   └── auth.middleware.js
│   │   ├── models/
│   │   │   ├── chat.model.js
│   │   │   ├── message.model.js
│   │   │   └── user.model.js
│   │   ├── routes/
│   │   │   ├── auth.routes.js
│   │   │   └── chat.routes.js
│   │   ├── services/
│   │   │   ├── ai.service.js
│   │   │   └── vector.service.js
│   │   ├── sockets/
│   │   │   └── socket.server.js
│   │   └── app.js
│   ├── server.js
│   ├── package.json
│   └── .env
├── frontend/
│   ├── public/
│   │   └── index.html
│   ├── src/
│   │   ├── components/
│   │   │   ├── Auth/
│   │   │   │   ├── Login.js
│   │   │   │   └── Register.js
│   │   │   ├── Chat/
│   │   │   │   ├── ChatList.js
│   │   │   │   ├── ChatWindow.js
│   │   │   │   └── Message.js
│   │   │   └── Layout/
│   │   │       └── Navbar.js
│   │   ├── context/
│   │   │   ├── AuthContext.js
│   │   │   └── SocketContext.js
│   │   ├── services/
│   │   │   ├── api.js
│   │   │   └── socket.js
│   │   ├── App.js
│   │   ├── App.css
│   │   └── index.js
│   ├── package.json
│   └── package-lock.json
└── README.md
```

## Installation & Setup

### Prerequisites
- Node.js (v14 or higher)
- MongoDB
- Google Gemini API key
- Pinecone account and API key

### Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the backend directory with the following variables:
   ```
   PORT=3000
   MONGODB_URI=mongodb://localhost:27017/chatgpt
   JWT_SECRET=your_jwt_secret_here
   GEMINI_API_KEY=your_gemini_api_key_here
   PINECONE_API_KEY=your_pinecone_api_key_here
   PINECONE_INDEX_NAME=chatgpt-embeddings
   ```

4. Start the backend server:
   ```bash
   npm run dev
   ```

### Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the frontend development server:
   ```bash
   npm start
   ```

4. The application will open in your browser at `http://localhost:5000`

## API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `GET /api/auth/check` - Check authentication status

### Chats
- `POST /api/chat` - Create a new chat
- `GET /api/chat` - Get all chats for a user
- `GET /api/chat/:chatId/messages` - Get messages for a specific chat

### Socket Events
- `ai-message` - Send a message to the AI
- `ai-response` - Receive response from the AI
- `error` - Error handling

## Environment Variables

### Backend (.env)
- `PORT` - Backend server port (default: 3000)
- `MONGODB_URI` - MongoDB connection string
- `JWT_SECRET` - Secret for JWT token generation
- `GEMINI_API_KEY` - Google Gemini API key
- `PINECONE_API_KEY` - Pinecone API key
- `PINECONE_INDEX_NAME` - Pinecone index name

## Key Features Implementation

### Authentication
- JWT-based authentication with HTTP-only cookies
- Protected routes using authentication middleware
- Password hashing with bcryptjs

### Real-time Communication
- Socket.io for bidirectional communication
- Authentication middleware for socket connections
- Real-time message delivery

### AI Integration
- Google Gemini 2.0 Flash for AI responses
- Text embeddings for semantic search
- Vector storage with Pinecone for long-term memory

### Memory Management
- Short-term memory: Last 20 messages in MongoDB
- Long-term memory: Vector embeddings in Pinecone
- Semantic search for relevant context retrieval

## Usage

1. Register a new account or login with existing credentials
2. Create a new chat or select an existing one
3. Start sending messages to interact with the AI
4. The AI will respond with relevant information based on the conversation history

## Troubleshooting

### Common Issues

1. **Connection refused errors**: Ensure backend is running on port 3000
2. **CORS issues**: Verify CORS configuration in backend/app.js
3. **Authentication errors**: Check JWT secret and token handling
4. **Socket connection failures**: Verify Socket.io configuration

### Debugging Tips

1. Check browser console for error messages
2. Verify backend server is running and accessible
3. Confirm environment variables are properly set
4. Check MongoDB connection status

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is licensed under the MIT License.

## Acknowledgments

- Google Gemini API for AI capabilities
- Pinecone for vector database services
- MongoDB for data persistence
- React and Node.js communities for excellent tools and libraries