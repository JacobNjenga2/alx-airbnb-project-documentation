# Airbnb Clone – Backend Feature Requirements

This document outlines the technical and functional requirements for the key backend features of the Airbnb Clone project.

---

## 1. 🛡️ User Authentication

### Description
Handles secure registration, login, and role-based access for guests, hosts, and admins.

### API Endpoints
- `POST /api/auth/register`  
- `POST /api/auth/login`  
- `GET /api/auth/profile`  
- `PUT /api/auth/profile`

### Input (Register)
```json
{
  "first_name": "Alice",
  "last_name": "Johnson",
  "email": "alice@example.com",
  "password": "Password123!",
  "role": "guest"
}
Output (Login)
json
Copy
{
  "token": "jwt-token",
  "user": {
    "id": "uuid",
    "email": "alice@example.com",
    "role": "guest"
  }
}
Validation Rules
Email must be unique and valid format

Password must be at least 8 characters with a number and symbol

Role must be one of: guest, host, admin

Performance
Response time < 500ms for login

Token expiration after 24h

2. 🏠 Property Management
Description
Allows hosts to create, update, delete, and view property listings.

API Endpoints
POST /api/properties

PUT /api/properties/:id

DELETE /api/properties/:id

GET /api/properties/:id

GET /api/properties

Input (Create Property)
json
Copy
{
  "title": "Ocean View Apartment",
  "description": "Cozy place with sea view.",
  "location": "Mombasa",
  "price_per_night": 80.00,
  "amenities": ["Wi-Fi", "Pool", "AC"],
  "available": true
}
Output (List Property)
json
Copy
{
  "property_id": "uuid",
  "title": "Ocean View Apartment",
  "host_id": "uuid"
}
Validation Rules
Title, description, location: required

Price must be a positive decimal

Host must be authenticated and verified

Performance
Create/edit/listings < 700ms

Paginated list: max 20 per page

3. 📆 Booking System
Description
Handles property booking by guests, prevents double booking, and allows cancellations.

API Endpoints
POST /api/bookings

GET /api/bookings/:id

DELETE /api/bookings/:id

GET /api/user/bookings

Input (Create Booking)
json
Copy
{
  "property_id": "uuid",
  "start_date": "2025-07-10",
  "end_date": "2025-07-12"
}
Output
json
Copy
{
  "booking_id": "uuid",
  "status": "confirmed",
  "total_price": 160.00
}
Validation Rules
Dates must be valid and non-overlapping

User must be authenticated

Booking must not exceed property’s availability window

Performance
Conflict check in < 300ms

Booking creation < 1s

Notes
All endpoints must return proper HTTP status codes (200, 400, 401, 404, 500)

Use pagination, filtering, and rate limiting where appropriate

Authentication via JWT

yaml
Copy

---

