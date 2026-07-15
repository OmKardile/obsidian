---

# 📘 Chapter 7 – Java Basics (10 Marks)

---
# MediConnect Backend API

  

This is the Express.js and MongoDB backend for the MediConnect application.

  

## Prerequisites

- Node.js

- MongoDB (running locally on `mongodb://127.0.0.1:27017/mediconnect`)

- Postman (for API testing)

  

## Setup Instructions

  

1. **Install Dependencies:**

   ```bash

   npm install

   ```

  

2. **Environment Configuration:**

   Create a `.env` file in the root of the backend directory with the following variables:

   ```env

   PORT=5000

   MONGODB_URI=mongodb://127.0.0.1:27017/mediconnect

   ```

  

3. **Seed Database (Optional but recommended):**

   Run the seed script to populate the database with mock doctors and a test patient.

   ```bash

   node seed.js

   ```

  

4. **Start the Server:**

   ```bash

   npm start

   ```

   *The server runs on `http://localhost:5000` by default.*

  

---

  

## API Documentation & Postman Testing Guide

  

You can use [Postman](https://www.postman.com/) to test these endpoints. Set your base URL in Postman to `http://localhost:5000/api`.

  

### 1. Auth Routes (`/auth`)

  

#### A. Login (Simulated OTP Request)

- **Endpoint:** `POST /auth/login`

- **Description:** Initiates a login via mobile number.

- **Headers:** `Content-Type: application/json`

- **Body (raw JSON):**

  ```json

  {

    "mobile": "+919876543210"

  }

  ```

- **Success Response (200 OK):**

  ```json

  {

    "message": "OTP sent successfully",

    "user": {

      "_id": "65b...",

      "fullName": "Rahul Sharma",

      "mobile": "+919876543210",

      "role": "patient",

      ...

    }

  }

  ```

*(Note down the returned `user._id` for use in subsequent requests like booking appointments).*

  

#### B. Register User

- **Endpoint:** `POST /auth/register`

- **Description:** Registers a new patient.

- **Headers:** `Content-Type: application/json`

- **Body (raw JSON):**

  ```json

  {

    "fullName": "Jane Doe",

    "mobile": "+919999988888",

    "age": 30,

    "bloodGroup": "O+",

    "gender": "Female",

    "address": "Baner, Pune"

  }

  ```

- **Success Response (201 Created):**

  ```json

  {

    "message": "User registered successfully",

    "user": { ... }

  }

  ```

  

#### C. Set PIN

- **Endpoint:** `POST /auth/set-pin`

- **Description:** Sets a fast-login 4-digit PIN for an existing user.

- **Headers:** `Content-Type: application/json`

- **Body (raw JSON):**

  ```json

  {

    "userId": "REPLACE_WITH_USER_ID",

    "pin": "1234"

  }

  ```

  

---

  

### 2. Patient Routes (`/patient`)

  

#### A. Get All Doctors

- **Endpoint:** `GET /patient/doctors`

- **Description:** Returns a list of all available doctors.

- **Success Response (200 OK):**

  ```json

  [

    {

      "_id": "65c...",

      "userId": {

        "_id": "65c...",

        "fullName": "Dr. Priya Kulkarni",

        "address": "Kondhwa, Pune"

      },

      "specialization": "Dermatologist",

      "experience": 8,

      "rating": 4.9,

      "fee": 500,

      "availableSlots": ["5:00 PM", "5:15 PM"]

    },

    ...

  ]

  ```

*(Note down a doctor's `_id` to use when testing the Book Appointment endpoint).*

  

#### B. Book an Appointment

- **Endpoint:** `POST /patient/book`

- **Description:** Books an appointment with a specific doctor.

- **Headers:** `Content-Type: application/json`

- **Body (raw JSON):**

  ```json

  {

    "patientId": "REPLACE_WITH_PATIENT_USER_ID",

    "doctorId": "REPLACE_WITH_DOCTOR_ID",

    "date": "17 Feb 2026",

    "time": "5:00 PM",

    "amountPaid": 500

  }

  ```

- **Success Response (201 Created):**

  ```json

  {

    "message": "Appointment booked successfully",

    "appointment": { ... }

  }

  ```

  

#### C. Get Patient's Appointments

- **Endpoint:** `GET /patient/appointments/:patientId`

- **Description:** Retrieves all appointments for a specific patient.

- **URL Parameter:** `patientId` (e.g., `http://localhost:5000/api/patient/appointments/65b...`)

- **Success Response (200 OK):**

  ```json

  [

    {

      "_id": "65d...",

      "patientId": "65b...",

      "doctorId": {

        "_id": "65c...",

        "userId": {

          "fullName": "Dr. Priya Kulkarni"

        }

      },

      "date": "17 Feb 2026",

      "time": "5:00 PM",

      "status": "upcoming",

      "amountPaid": 500

    }

  ]

  ```

  

---

  

### 3. Medicine Routes (`/medicine`)

  

#### A. Place an Order

- **Endpoint:** `POST /medicine/order`

- **Description:** Patient places an order for medicines.

- **Headers:** `Content-Type: application/json`

- **Body (raw JSON):**

  ```json

  {

    "patientId": "REPLACE_WITH_PATIENT_USER_ID",

    "items": [

        { "name": "Paracetamol", "quantity": 2 }

    ],

    "deliveryAddress": "Hadapsar, Pune",

    "totalAmount": 150

  }

  ```

- **Success Response (201 Created):**

  ```json

  {

    "message": "Medicine order placed successfully",

    "order": { ... }

  }

  ```

  

#### B. Get Patient's Orders

- **Endpoint:** `GET /medicine/patient/:patientId`

- **Description:** Retrieves all medicine orders for a specific patient.

- **URL Parameter:** `patientId`

  

---

  

### 4. Lab Routes (`/lab`)

  

#### A. Book a Lab Test

- **Endpoint:** `POST /lab/book`

- **Description:** Patient books a home collection or walk-in lab test.

- **Headers:** `Content-Type: application/json`

- **Body (raw JSON):**

  ```json

  {

    "patientId": "REPLACE_WITH_PATIENT_USER_ID",

    "testName": "CBC Blood Count",

    "bookingType": "home_collection",

    "date": "18 Feb 2026",

    "time": "8:00 AM",

    "amountPaid": 299

  }

  ```

- **Success Response (201 Created):**

  ```json

  {

    "message": "Lab test booked successfully",

    "labTest": { ... }

  }

  ```

  

#### B. Get Patient's Lab Tests

- **Endpoint:** `GET /lab/patient/:patientId`

- **Description:** Retrieves all lab tests for a specific patient.

- **URL Parameter:** `patientId`

  

---

  

### 5. Ambulance Routes (`/ambulance`)

  

#### A. Request an Ambulance

- **Endpoint:** `POST /ambulance/request`

- **Description:** Patient requests an ambulance (govt, private, icu).

- **Headers:** `Content-Type: application/json`

- **Body (raw JSON):**

  ```json

  {

    "patientId": "REPLACE_WITH_PATIENT_USER_ID",

    "ambulanceType": "private",

    "pickupLocation": "Hadapsar, Pune",

    "dropLocation": "Ruby Hall Clinic",

    "estimatedFare": 600

  }

  ```

- **Success Response (201 Created):**

  ```json

  {

    "message": "Ambulance requested successfully",

    "booking": { ... }

  }

  ```

  

#### B. Get Patient's Ambulance Requests

- **Endpoint:** `GET /ambulance/patient/:patientId`

- **Description:** Retrieves all ambulance bookings for a specific patient.

- **URL Parameter:** `patientId`

  

---

  

## Postman Testing Workflow Example

To fully test the happy path in Postman:

1. Run `GET http://localhost:5000/api/patient/doctors` to view available doctors. Copy the `_id` of one doctor.

2. Run `POST http://localhost:5000/api/auth/login` using `{"mobile": "+919876543210"}`. Copy the `user._id` returned.

3. Run `POST http://localhost:5000/api/patient/book` using the patient ID and doctor ID.

4. Run `POST http://localhost:5000/api/medicine/order` using the patient ID to buy medicines.

5. Run `POST http://localhost:5000/api/lab/book` using the patient ID to book a lab test.

6. Run `POST http://localhost:5000/api/ambulance/request` using the patient ID in case of emergency.