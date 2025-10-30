# 🏡 ALX Airbnb Project Documentation

## 📊 Directory: `data-flow-diagram/`

This directory contains the **Data Flow Diagram (DFD)** for the Airbnb Clone backend system.  
The diagram represents how data moves between different entities, processes, and data stores within the application.

---

## 🎯 Objective

The goal of this DFD is to visualize how **users**, **properties**, **bookings**, and **payments** interact across the system.  
It highlights key inputs, processes, and outputs to ensure a clear understanding of data management and system communication.

---

## 🧩 Diagram Description

The Data Flow Diagram (Level 1) includes the following **core entities** and **data processes**:

### **External Entities**
- 👤 **User (Guest/Host)** — initiates actions such as registration, property listing, and booking.
- 🛠️ **Admin** — oversees all transactions and manages system data.
- 💳 **Payment Gateway** — processes guest payments and sends payment confirmations.

---

### **Processes**
1. **User Registration & Authentication**
   - Users submit personal details → System validates and stores them in the **User Data Store**.
   - Authenticated users gain access tokens for future actions.

2. **Property Management**
   - Hosts add/edit property details → System saves them to the **Property Data Store**.
   - Data such as price, location, and amenities are stored and updated dynamically.

3. **Search & Booking**
   - Guests send search queries → System retrieves matching listings.
   - When a booking is made, data flows between **User**, **Booking Process**, and **Property Data Store**.
   - Booking confirmation is stored and linked to user and property records.

4. **Payment Processing**
   - Booking details are sent to the **Payment Gateway**.
   - Payment confirmation or failure messages flow back to update the **Payment Data Store** and notify the user.

5. **Review & Rating**
   - After completed stays, users can submit feedback.
   - Reviews are stored and linked to both **User** and **Property** entities.

---

### **Data Stores**
- 🗃️ **User Data Store** — stores user profiles, authentication tokens, and roles.  
- 🗃️ **Property Data Store** — stores all property details and availability status.  
- 🗃️ **Booking Data Store** — stores booking records and their current status.  
- 🗃️ **Payment Data Store** — stores transaction data and verification logs.  
- 🗃️ **Review Data Store** — keeps guest ratings and comments.

---

## 📎 Diagram File

The visual representation of this data flow can be found below:

![alt text](data_flow.png)