# Airbnb Clone – Use Case Connections

This document outlines the interactions between key actors and system use cases for the backend of an Airbnb Clone application.

## Actors

- Admin: System administrator responsible for overseeing platform activity.
- Host: A registered user who can list properties for rent.
- Guest: A registered user who can book properties.
- System: The backend server, responsible for processing requests and enforcing logic.

## Use Case Mapping

| Use Case                 | Admin | Host | Guest | System | Description |
|--------------------------|:-----:|:----:|:-----:|:------:|-------------|
| Admin Login              |  Yes  |      |       |  Yes   | Admin logs in to the dashboard. System authenticates credentials and assigns privileges. |
| User Registration        |       | Yes  | Yes   |  Yes   | Host or Guest creates an account. System validates input and stores hashed credentials. |
| User Login               |       | Yes  | Yes   |  Yes   | Host or Guest logs in. System verifies credentials and generates a JWT token. |
| Create Property Listing  |       | Yes  |       |  Yes   | Host adds a new property. System saves listing with ownership metadata. |
| Book Property            |       |      | Yes   |  Yes   | Guest books a property. System checks availability, prevents conflicts, and stores booking data. |
| View Booking Detail      |  Yes  | Yes  | Yes   |  Yes   | All actors can view bookings relevant to them. System fetches data with permission filtering. |
| Make Payment             |       |      | Yes   |  Yes   | Guest makes payment. System processes through Stripe or PayPal and records transaction. |
| Submit Review            |       |      | Yes   |  Yes   | Guest submits a review after completed booking. System links review to property and booking. |

## Use Case Descriptions

### Admin Login
- Actors: Admin, System
- Flow: Admin submits credentials → System authenticates → Access granted

### User Registration
- Actors: Guest, Host, System
- Flow: User submits registration form → System validates and stores user → Token issued

### User Login
- Actors: Guest, Host, System
- Flow: User logs in → System validates password → JWT issued for session

### Create Property Listing
- Actors: Host, System
- Flow: Host creates listing → System validates input → Saves with host’s ID

### Book Property
- Actors: Guest, System
- Flow: Guest selects dates and confirms booking → System checks availability and creates booking record

### View Booking Detail
- Actors: Admin, Host, Guest, System
- Flow: User requests booking info → System authorizes and returns data

### Make Payment
- Actors: Guest, System
- Flow: Guest initiates payment → System integrates with payment gateway → Stores transaction

### Submit Review
- Actors: Guest, System
- Flow: Guest reviews completed stay → System checks booking status → Saves review linked to property

