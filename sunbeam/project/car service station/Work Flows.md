	# Online Car Service Station – Functional Flows

## 🧑‍💻 Client Flow
1. **Authentication**
   - Register / Login
   - Manage Profile (edit, logout)
2. **Select Service Station**
   - Choose from list/filter of service stations (admins)
   - Services + pricing update per station
3. **Browse Services**
   - View service list and details
   - Check rates for chosen station
4. **Booking**
   - Select service
   - Pick date & time
   - Confirm booking
   - System generates **Quotation/Receipt** with final pricing
   - Quotation sent to client before car drop-off
5. **Booking Tracking**
   - View "My Bookings"
   - Track status (Pending → In Progress → Completed)
6. **Service History**
   - Past services with details
   - Download receipts/quotations (optional)
7. **Chat**
   - Real-time chat with selected Admin (station manager)

---

## 🛠️ Admin Flow (Service Station Manager)
1. **Authentication**
   - Login
   - Manage Profile
2. **Service Management**
   - Add / Edit / Remove services
   - Set service-specific pricing for own station
3. **Staff Management**
   - View staff list
   - Add staff members
   - Edit roles (mechanic, helper, receptionist, etc.)
4. **Booking Management**
   - View bookings for their station
   - Update booking status
   - Confirm or adjust quotation if needed
5. **Service History**
   - View completed services under own station
6. **Chat**
   - Chat with clients of their station

---

## 👑 Super Admin Flow (Owner)
1. **Authentication**
   - Login as Super Admin
2. **Admin Management**
   - Add Admins (service station managers)
   - Remove Admins
   - View all registered service stations
3. **Global Oversight**
   - View all bookings across all stations
   - Access overall service history
   - Analytics dashboard (optional: revenue, bookings, station performance)
4. **(Optional) Communication**
   - Global announcements/notifications
   - Chat access if required (but normally only Admin ↔ Client)
