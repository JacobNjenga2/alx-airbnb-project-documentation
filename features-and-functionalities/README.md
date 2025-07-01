# Airbnb Clone Backend – Features and Functionalities

This document outlines the essential backend features required to power the Airbnb Clone.

## Core Functionalities

### 1. User Management
- Guest/Host registration
- Login via email/password
- OAuth login (Google/Facebook)
- JWT authentication
- Role-based access control
- Profile update and photo upload

### 2. Property Listings
- Add/edit/delete property
- Include title, description, location, price, amenities, availability
- Upload property images

### 3. Search & Filtering
- Search by location
- Filter by price, guests, amenities
- Paginate large result sets

### 4. Booking System
- Book property with date validation
- Prevent double bookings
- Cancel bookings
- Track booking status (pending, confirmed, etc.)

### 5. Payments
- Stripe/PayPal integration
- Host payouts
- Multi-currency support

### 6. Reviews & Ratings
- Guest reviews and ratings
- Host responses
- Reviews linked to bookings

### 7. Notifications
- Email and in-app alerts:
  - Booking confirmations
  - Cancellations
  - Payment updates

### 8. Admin Dashboard
- Monitor and manage:
  - Users
  - Properties
  - Bookings
  - Payments

See `airbnb_features.png` for the visual feature breakdown.
