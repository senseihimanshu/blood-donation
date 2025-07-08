<<<<<<< HEAD
# 🩸 BloodConnect - Blood Donation Platform

A comprehensive blood donation platform connecting hospitals with donors through real-time matching and emergency notifications.

## Features

### For Donors
- **Profile Management**: Blood type, location, availability status
- **Emergency Toggle**: Get priority notifications for critical requests
- **Distance Control**: Set maximum distance for donation requests (1-50 km)
- **Real-time Notifications**: Instant alerts for matching blood requests
- **Donation History**: Track donation count and last donation date

### For Hospitals
- **Blood Request Management**: Create and manage blood requests
- **Patient Information**: Store patient details and criticality levels
- **Donor Matching**: Automatic matching based on blood compatibility and distance
- **Emergency Requests**: Priority system for critical cases
- **Real-time Updates**: Live donor responses and status updates

### Technical Features
- **Geospatial Matching**: MongoDB geospatial queries for distance-based matching
- **Blood Compatibility**: Automatic matching based on blood type compatibility
- **Real-time Communication**: Socket.io for instant notifications
- **Secure Authentication**: JWT-based authentication for users and hospitals
- **Mobile Responsive**: Works seamlessly on all devices

## Tech Stack

### Backend
- **Node.js** with Express.js
- **MongoDB** with Mongoose (geospatial indexing)
- **Socket.io** for real-time communication
- **JWT** for authentication
- **bcryptjs** for password hashing

### Frontend
- **React** with TypeScript
- **React Router** for navigation
- **React Hook Form** for form management
- **Socket.io-client** for real-time updates
- **React Toastify** for notifications

## Installation & Setup

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or Atlas)
- npm or yarn

### Backend Setup

1. **Navigate to backend directory**:
   ```bash
   cd backend
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Configure environment variables**:
   ```bash
   # Copy .env file and update with your settings
   PORT=5000
   MONGODB_URI=mongodb://localhost:27017/blood_donation
   JWT_SECRET=your_jwt_secret_key_here
   ```

4. **Seed the database with mock data**:
   ```bash
   npm run seed
   ```

5. **Start the backend server**:
   ```bash
   npm run dev
   ```

### Frontend Setup

1. **Navigate to frontend directory**:
   ```bash
   cd frontend
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Start the React development server**:
   ```bash
   npm start
   ```

## Demo Credentials

### Hospital Login
- **Email**: `allindiainstituteofmedicalsciences@hospital.com`
- **Password**: `hospital123`

### Donor Login
- **Email**: `aarav.sharma0@gmail.com`
- **Password**: `user123`

*Note: All user emails follow the pattern `firstname.lastname[number]@gmail.com`*

## Database Design

### User Schema
```javascript
{
  name, email, password, phone, bloodType,
  location: { type: 'Point', coordinates: [lng, lat] },
  address, maxDistance, isAvailable, emergencyContact,
  lastDonation, donationCount, isVerified
}
```

### Hospital Schema
```javascript
{
  name, email, password, phone, registrationNumber,
  location: { type: 'Point', coordinates: [lng, lat] },
  address, city, state, pincode, contactPerson,
  services, isVerified
}
```

### BloodRequest Schema
```javascript
{
  hospital, patientName, patientAge, patientGender,
  bloodType, unitsNeeded, urgency, neededBy,
  description, status, matchedDonors, isEmergency,
  contactInfo
}
```

## Blood Compatibility Matrix

| Recipient | Compatible Donors |
|-----------|------------------|
| A+ | A+, A-, O+, O- |
| A- | A-, O- |
| B+ | B+, B-, O+, O- |
| B- | B-, O- |
| AB+ | A+, A-, B+, B-, AB+, AB-, O+, O- (Universal Recipient) |
| AB- | A-, B-, AB-, O- |
| O+ | O+, O- |
| O- | O- (Universal Donor) |

## API Endpoints

### Authentication
- `POST /api/auth/register/user` - User registration
- `POST /api/auth/register/hospital` - Hospital registration
- `POST /api/auth/login/user` - User login
- `POST /api/auth/login/hospital` - Hospital login
- `GET /api/auth/me` - Get current user

### Users
- `GET /api/users/profile` - Get user profile
- `PUT /api/users/profile` - Update user profile
- `PATCH /api/users/emergency-toggle` - Toggle emergency contact
- `PATCH /api/users/availability-toggle` - Toggle availability
- `PATCH /api/users/max-distance` - Update max distance

### Blood Requests
- `POST /api/blood-requests` - Create blood request
- `GET /api/blood-requests/hospital` - Get hospital's requests
- `GET /api/blood-requests/donor` - Get donor's matched requests
- `GET /api/blood-requests/emergency` - Get emergency requests
- `PATCH /api/blood-requests/:id/respond` - Respond to request
- `PATCH /api/blood-requests/:id/donated/:donorId` - Mark as donated

## Real-time Events

### Socket.io Events
- `newBloodRequest` - New matching blood request for donor
- `donorResponse` - Donor response notification for hospital
- `emergencyAlert` - Critical emergency notifications

## Data Scalability

**Current Scale**: 500 users + 50 hospitals (No sharding needed)

**Future Scaling Options**:
- **Horizontal Sharding**: By geographic regions
- **Vertical Partitioning**: Separate read/write operations
- **Caching**: Redis for frequently accessed data
- **CDN**: For static assets and images

## Security Features

- Password hashing with bcryptjs
- JWT token-based authentication
- Rate limiting for API endpoints
- Input validation and sanitization
- CORS configuration
- Helmet.js for security headers

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License.

## Support

For support, email support@bloodconnect.com or create an issue in the repository.

---

**Save Lives. Donate Blood. 🩸**
=======
# blood-donation
>>>>>>> e4ef6e90f7dcf1240054f2f71c4a41150cff2c19
