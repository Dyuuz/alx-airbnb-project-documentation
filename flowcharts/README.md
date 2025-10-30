# 🧩 Flowchart – System Process

## 📁 Directory: `flowcharts/`

This directory contains the **Flowchart Diagram** for one of the core backend processes in the Airbnb Clone system.  
The selected process demonstrates how the system handles **User Registration** from input to confirmation.

---

## 🎯 Objective

The purpose of this flowchart is to visualize the **workflow** and **logic sequence** that occurs when a new user registers in the Airbnb system — including validation, database interaction, and feedback to the user.

---

## 🔄 Process Overview — User Registration

### **Workflow Steps**

1. **Start Process**
   - The flow begins when a user initiates registration.

2. **Input User Details**
   - User provides required information such as:
     - First name  
     - Last name  
     - Email  
     - Password  

3. **Validate Input**
   - The system checks for:
     - Missing fields  
     - Invalid email format  
     - Weak password  

4. **Check for Existing User**
   - The system queries the **User Data Store** to ensure the email does not already exist.

   - **If email exists:** Display an error message → **End Process.**  
   - **If email is unique:** Proceed to the next step.

5. **Encrypt Password**
   - The password is securely hashed using a cryptographic algorithm (e.g., bcrypt).

6. **Store User Record**
   - Save user details (with hashed password) into the **User Data Store**.

7. **Generate Authentication Token**
   - Create a JWT (JSON Web Token) for the new user.

8. **Send Confirmation Message**
   - Notify the user via email or in-app that their account has been successfully created.

9. **End Process**
   - The registration flow completes, and the user is redirected to the login or dashboard page.

---

## 🧠 Summary of Data Flow

- **Input:** User data (name, email, password)  
- **Process:** Validation → Uniqueness check → Encryption → Database save  
- **Output:** Confirmation response & JWT token  

---

## 🖼️ Flowchart File

You can view the flowchart representation of this process below:

