# Airbnb Clone Project- Full Scale Back End Implementation

## Overview of the Project
The Airbnb Clone Project is a full-stack web application designed to replicate Airbnb's core functionalities, such as property listings, bookings, and user management. It aims to provide a scalable and secure platform using modern web technologies.

## Project Goals
- Implement secure user registration and authentication.
- Enable property listing creation and management.
- Develop a booking system for property reservations.
- Integrate payment processing for transactions.
- Allow users to leave reviews and ratings.
- Optimize data storage and retrieval.

## Technology Stack
- Django
- PostgreSQL
- GraphQL
- Celery
- Redis
- Docker

## Technology Stack Overview

-**Django** This is a Python web framework for building RESTful APIs to handle user and property data.
-**PostgreSQL**: A relational database for storing user, property, and booking information.
- **GraphQL**: A query language for flexible data retrieval from the backend.
- **Celery**: Handles asynchronous tasks like sending notifications.
- **Redis**: Provides caching to improve performance.
- **Docker**: Ensures consistent development and deployment environments.

## Overview of the Database Design 
- **Users**: Fields: user_id, first_name, last_name, email, password, phone number, age. 
            Relationships: A User can be a property owner or a booker. User can own multiple Properties or/and make multiple Bookings.
- **Properties**: Fields: property_id, property_title, description, price, owner_id. 
            Relationships: One or Multiple Properties may belong to one owner. A user by booking owns a property by virtue of rent , and only owns one property. 
- **Bookings**: 
            Fields: booking_id, user_id, property_id, check_in, check_out.
            Relationships: A booking belongs to the user who has booked, by virtue of rent. One user can make multiple bookings.
- **Reviews**: 
            Fields: review_id, user_id, property_id, property_rating, comment/s. 
            Relationships: A user by virtue of booking is the only one allowed to leave a review. 
            They leave a review after completing a stay. One user leaves one review per property. 
- **Payments**: 
            Fields: payment_id, booking_id, amount, status. 
            Relationships: A user can pay upfront. Only one user by virtue of booking can make a payment. 
            A user/booker can make multiple payments. 

## Team Roles
- **Backend Developer**: Handles server-side coding, API creation, and database connections for the app’s core features.
- **Database Administrator**: Sets up and tunes the PostgreSQL database to store and retrieve data efficiently.
- **DevOps Engineer**: Uses Docker to manage app containers and sets up automated deployment processes.
- **Security Specialist**: Adds security layers to APIs, like user verification and data protection.
- **Project Manager**: Keeps the team on track, assigns tasks, and ensures deadlines are met.

## Feature Breakdown
- **User Management**: Lets users sign up, log in, and edit their profiles securely.
- **Property Management**: Owners list and manage properties; bookers browse and pick rentals.
- **Booking System**: Users book properties for specific dates, with checks for availability.
- **Payment Processing**: Handles secure payments for bookings, keeping transactions safe.
- **Reviews and Ratings**: Bookers leave ratings and comments after stays to build trust.

## API Security
- **Authentication**: Uses tokens (JWT) to check user identity before granting API access.
- **Authorization**: Limits what users can do based on their role, like owner or booker.
- **Rate Limiting**: Caps API calls to stop overloads and keep the system running.
- **Encryption**: Secures data with HTTPS and encrypts sensitive info like passwords.

Security matters to keep user info safe, protect payments, and ensure the app stays reliable.

## CI/CD Pipeline
CI/CD automates testing and deploying code to make development smoother. **GitHub Actions** runs tests and pushes updates, while **Docker** keeps environments the same across dev and production. This cuts errors and speeds up releases.