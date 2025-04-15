# BizzyBuddy Server

Backend server for the BizzyBuddy application, handling authentication, video calls, and audio rooms.

## Features

- User authentication (register, login)
- JWT token-based API security
- Video calling features
- Audio room functionality
- Integration with Stream Video SDK

## Prerequisites

- Node.js (v14 or higher)
- MongoDB
- Stream Video API credentials

## Environment Variables

Create a `.env` file in the server directory with the following variables:

```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/bizzybuddy
JWT_SECRET=your_jwt_secret
STREAM_API_KEY=your_stream_api_key
STREAM_API_SECRET=your_stream_api_secret
```

## Installation

1. Install dependencies:
```bash
npm install
```

2. Start MongoDB:
```bash
# Make sure MongoDB is running on your system
```

3. Start the server:
```bash
# Development mode
npm run dev

# Production mode
npm start
```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login a user
- `POST /api/auth/validate` - Validate JWT token
- `GET /api/auth/user` - Get current user data

### Audio Rooms
- `POST /api/audio-rooms` - Create a new audio room
- `GET /api/audio-rooms` - Get all audio rooms
- `POST /api/audio-rooms/:roomId/join` - Join an audio room
- `POST /api/audio-rooms/:roomId/leave` - Leave an audio room

### Video Calls
- `POST /api/calls` - Create a new call
- `GET /api/calls` - Get call history
- `POST /api/calls/:callId/join` - Join a call
- `POST /api/calls/:callId/leave` - Leave a call
- `POST /api/calls/:callId/end` - End a call

### Stream Token
- `POST /api/stream/token` - Get a fresh Stream token

## Error Handling

The server uses standard HTTP status codes:
- 200: Success
- 201: Created
- 400: Bad Request
- 401: Unauthorized
- 403: Forbidden
- 404: Not Found
- 500: Server Error

## Security

- Passwords are hashed using bcrypt
- JWT tokens expire after 24 hours
- All routes except registration and login require authentication
- CORS is enabled for the Flutter app

## Development

To run the server in development mode with auto-reload:
```bash
npm run dev
```

## Production

For production deployment:
1. Set up proper environment variables
2. Use a process manager like PM2
3. Set up proper MongoDB security
4. Use HTTPS in production 