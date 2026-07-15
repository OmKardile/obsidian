# Online Car Service Station – Functional Module Breakdown
## (With Super Admin, Admin-Specific Pricing, Client-Selected Service Station, and Booking Quotation)

## 1. Authentication Module
- **User Registration & Login** (Clients)
- **Admin Login** (Service Station Managers)
- **Super Admin Login** (Owner)
- **Password Reset / Recovery** (optional)

## 2. Super Admin Module (Owner)
- **Manage Admins**
  - Add Admins
  - Remove Admins
- **View All Admins & Their Service Stations**
- **View All Bookings Across All Admins**
- **Analytics Dashboard** (optional)

## 3. Admin Module (Service Station Manager)
- **Manage Services**
  - Add / Edit / Remove Services
  - Set Service-Specific Pricing (per admin)
- **Manage Bookings**
  - Update Booking Status (Pending → In Progress → Completed)
- **Manage Staff**
  - View Staff List
  - Add / Edit Staff Roles
- **Chat with Clients**
- **View Service History of Own Station**

## 4. Service Browsing Module (Client)
- **Home Page**
  - Filter / Select Service Station (Admin) by name
  - Display services and rates based on selected admin
- **Service List Page**
- **Service Details Page**

## 5. Booking Module (Client)
- **Select Service**
- **Select Service Station (via filter)**
- **Pick Date & Time**
- **Confirm Booking**
- **Generate Quotation / Receipt**
  - Sent to client with final pricing
  - Client can approve before bringing car in

## 6. Booking Tracking Module (Client)
- **My Bookings Page**
- **Booking Status View**
- **Notifications** (optional)

## 7. Service History Module (Client)
- **Past Services List**
- **Service Details** (completed jobs)

## 8. User Profile Module (Client)
- **View Profile**
- **Edit Profile**
- **Logout**

## 9. Chat Module
- **Client ↔ Admin** Chat (real-time)
- **Admin ↔ Client** Chat
- **Attachment Support** (optional: images of car issues)
- **Notifications for New Messages**
