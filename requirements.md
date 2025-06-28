# Technical and Functional requirements for features

## Technical Requirements
1. **Database Management**
    Use a relational database such as PostgreSQL or MySQL.
    Required tables:
    `Users` (guests and hosts)
    `Properties`
    `Bookings`
    `Reviews`
    `Payments`
2. **API Development**
    Use RESTful APIs to expose backend functionalities to the frontend.
    Include proper HTTP methods and status codes for:
    `GET` (retrieve data)
    `POST` (create data)
    `PUT`/`PATCH` (update data)
    `DELETE` (remove data)
    Use GraphQL for complex data fetching scenarios (optional but recommended).
3. **Authentication and Authorization**
    Use JWT for secure user sessions.
    Implement role-based access control (RBAC) to differentiate permissions between:
    `Guests`
    `Hosts`
    `Admins`

## Core Functionalities
The backend for the Airbnb Clone must enable key features that align with the functionalities of a rental marketplace.

1. **User Management**
- User `Registration`:
    Allow users to sign up as `guests` or `hosts`.
    Use secure authentication methods like `JWT` (JSON Web Tokens).
- User `Login` and `Authentication`:
    Implement login via email and password.
    Include OAuth options (e.g., Google, Facebook).
- `Profile Management`:
    Enable users to update their profiles, including profile photos, contact info, and preferences.
2. **Property Listings Management**
- 'Add' Listings:
    Hosts can create property listings by providing details such as title, description, location, price, amenities, and availability.
- `Edit`/`Delete` Listings:
    Hosts can update or remove their property listings.
3. **Search and Filtering**
- Implement `search` functionality to allow users to find properties by:
    * Location
    * Price range
    * Number of guests
    * Amenities (e.g., Wi-Fi, pool, pet-friendly)
    * Include pagination for large datasets.
4. **Booking Management**
- `Booking` Creation:
    Guests can book a property for specified dates.
    Prevent double bookings using date validation.
- Booking `Cancellation`:
    Allow guests or hosts to cancel bookings based on the cancellation policy.
Booking `Status`:
    Track booking statuses such as pending, confirmed, canceled, or completed.
5. **Payment Integration**
- Implement secure payment gateways (e.g., Stripe, PayPal) to handle:
- Upfront payments by guests.
- Automatic payouts to hosts after a booking is completed.
- Include support for multiple currencies.
