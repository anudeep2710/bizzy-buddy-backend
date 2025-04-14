# BizzyBuddy API Backend

Backend API server for the BizzyBuddy Flutter application. This backend provides authentication, user management, and video call functionality.

## Features

- User authentication (register, login)
- JWT token-based authorization
- Video call integration with Stream SDK
- Call history tracking

## Deployment

This repository is configured for deployment on Render.com.

### Environment Variables

- `PORT` - Port to run the server on (defaults to 5000)
- `JWT_SECRET` - Secret key for JWT token generation (set this in production)

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login a user
- `POST /api/auth/validate` - Validate JWT token
- `GET /api/auth/user` - Get current user details

### Video Calls
- `POST /api/calls` - Create a new video call
- `POST /api/calls/:callId/join` - Join an existing call
- `POST /api/calls/:callId/leave` - Leave a call
- `POST /api/calls/:callId/end` - End a call (only creator or admin)
- `GET /api/calls` - Get call history for user

## Local Development

1. Clone the repository
```
git clone https://github.com/anudeep2710/bizzybuddy-backend.git
cd bizzybuddy-backend
```

2. Install dependencies
```
npm install
```

3. Run the development server
```
npm run dev
```

4. The server will be available at http://localhost:5000

## Connect with Flutter App

Update the `baseUrl` in your Flutter app's `ApiService` to point to your deployed API:

```dart
// For production
const deployedUrl = 'https://your-render-url.onrender.com/api';

// For local testing
// Android: 'http://10.0.2.2:5000/api'
// iOS: 'http://localhost:5000/api'
```

## License

MIT 