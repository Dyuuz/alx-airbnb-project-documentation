# 🏗️ Airbnb Clone Backend – Requirements Specification

**Repository:** `alx-airbnb-project-documentation`  
**File:** `requirements.md`  
**Objective:** Define the functional and technical requirements for core backend features including Authentication, Property Management, and Booking System.

---

## ⚙️ 1. User Authentication System

### **Functional Requirements**
- Users can **register**, **log in**, and **log out** securely.  
- Passwords must be **encrypted** before storage.  
- Token-based authentication (**JWT**) must be used for session management.  
- Only verified users can access restricted endpoints.  

---

### **API Endpoints**

| Method | Endpoint | Description |
|---------|-----------|-------------|
| `POST` | `/api/v1/auth/register` | Create a new user account |
| `POST` | `/api/v1/auth/login` | Authenticate user and return JWT token |
| `GET` | `/api/v1/auth/profile` | Retrieve current user profile (JWT required) |
| `POST` | `/api/v1/auth/logout` | Invalidate the user’s current session token |

---

### **Input / Output Specification**

**Input Example**
```json
{
  "first_name": "Jane",
  "last_name": "Doe",
  "email": "jane@example.com",
  "password": "SecurePass123!"
}

### **Output Example (Success)**
{
  "message": "Registration successful",
  "user_id": "uuid",
  "token": "jwt_token_here"
}

### Validation Rules

- Email must be unique and properly formatted.

- Password must be at least 8 characters and include both letters and numbers.

- Fields first_name, last_name, and email are mandatory.


## 🏠 2. Property Management System

### **Functional Requirements**
- Hosts can **add**, **update**, and **delete** property listings.  
- Each property must include **location**, **price**, **description**, and **availability**.  
- Guests can **search** and **filter** properties by key attributes.  

---

### **API Endpoints**

| Method | Endpoint | Description |
|---------|-----------|-------------|
| `POST` | `/api/v1/properties/` | Create a new property listing |
| `GET` | `/api/v1/properties/` | Retrieve list of available properties |
| `GET` | `/api/v1/properties/{id}` | Retrieve property details |
| `PUT` | `/api/v1/properties/{id}` | Update a property |
| `DELETE` | `/api/v1/properties/{id}` | Delete a property |

---

### **Input / Output Specification**

**Input Example**
```json
{
  "name": "Ocean View Apartment",
  "description": "Beautiful sea-view apartment",
  "location": "Lagos, Nigeria",
  "pricepernight": 150.00,
  "amenities": ["Wi-Fi", "Pool", "AC"]
}

### Validation Rules

- name, description, location, and pricepernight are required.

- Price must be a positive decimal number.

- Only the host who created the property can modify or delete it.


## 🗓️ 3. Booking Management System

### **Functional Requirements**
- Guests can **book properties** for available dates.  
- The system must **prevent overlapping bookings**.  
- Bookings must track **status** (pending, confirmed, canceled).  
- Hosts can **view bookings** for their properties.  

---

### **API Endpoints**

| Method | Endpoint | Description |
|---------|-----------|-------------|
| `POST` | `/api/v1/bookings/` | Create a new booking |
| `GET` | `/api/v1/bookings/` | Retrieve all bookings for the logged-in user |
| `GET` | `/api/v1/bookings/{id}` | Retrieve booking details |
| `PATCH` | `/api/v1/bookings/{id}/cancel` | Cancel a booking |

---

### **Input / Output Specification**

**Input Example**
```json
{
  "property_id": "uuid",
  "start_date": "2025-11-01",
  "end_date": "2025-11-05"
}

{
  "message": "Booking confirmed",
  "booking_id": "uuid",
  "status": "confirmed",
  "total_price": 600.00
}

### Validation Rules

- start_date and end_date must be valid and non-overlapping.

- end_date must be after start_date.

- The property must exist and be available for the selected dates.


## Additional Technical Notes

- Framework: Django + Django REST Framework

- Database: PostgreSQL (with indexing on property_id, user_id, booking_id)

- Authentication: JWT-based, with role-based access (Guest, Host, Admin)

- Logging & Monitoring: Centralized error logging using Django signals and middleware

- Security: All sensitive data encrypted at rest and in transit (HTTPS, AES, bcrypt)