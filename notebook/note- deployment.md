# Deployment Notes (Railway DB + Render)

## Mistakes Made

|Problem|Symptom|Root Cause|Fix|
|---|---|---|---|
|Wrong API URL|404 on login|Frontend calling `/auth/login`|Use `/api/auth/login`|
|Missing `/api`|Backend routes not found|Express mounted under `/api/*`|Update frontend base URL|
|Generic catch block|Only "Server Error" shown|Error hidden|`catch(err)` + `console.error(err)`|
|Using `err` inside `catch {}`|Backend crash|`err` undefined|Use `catch(err)`|
|Not checking Network tab|Guessing issue|Wrong debugging flow|Check Request URL first|
|Not checking Response tab|Couldn't see real error|Response body ignored|Open Response tab|
|Missing DB_PORT|DB timeout|Railway doesn't use 3306|Add `port: process.env.DB_PORT`|
|Not testing DB separately|Login looked broken|DB was broken|`SELECT 1` on startup|
|Not redeploying after env change|Same issue persists|Vite embeds env at build time|Redeploy frontend|
|React Router on Render|`/login` 404 on refresh|No rewrite rule|`_redirects` file|

---

# Railway + Render Deployment Checklist

## 1. Railway Database

Create MySQL service.

Get:

```env
MYSQLHOST
MYSQLPORT
MYSQLUSER
MYSQLPASSWORD
MYSQLDATABASE
```

Example:

```env
DB_HOST=zephyr.proxy.rlwy.net
DB_PORT=40583
DB_USER=root
DB_PASSWORD=*****
DB_NAME=railway
```

---

## 2. Import Database

Local:

```bash
mysqldump -u USER -p DBNAME > dump.sql
```

Import to Railway:

```bash
mysql -h HOST -P PORT -u USER -p DATABASE < dump.sql
```

PowerShell:

```powershell
Get-Content dump.sql | mysql -h HOST -P PORT -u USER -p DATABASE
```

---

## 3. Backend (Render Web Service)

### Root Directory

```text
backend
```

### Build Command

```bash
npm install
```

### Start Command

```bash
npm start
```

### Environment Variables

```env
DB_HOST=zephyr.proxy.rlwy.net
DB_PORT=40583
DB_USER=root
DB_PASSWORD=*****
DB_NAME=railway
JWT_SECRET=*****
```

---

## 4. Backend DB Config

```js
const mysql = require("mysql2");

const pool = mysql.createPool({
  host: process.env.DB_HOST,
  port: process.env.DB_PORT,
  user: process.env.DB_USER,
  password: process.env.DB_PASSWORD,
  database: process.env.DB_NAME,

  ssl: {
    rejectUnauthorized: false
  }
});

module.exports = pool.promise();
```

---

## 5. Test DB on Startup

Temporarily:

```js
db.query("SELECT 1")
  .then(() => console.log("DB CONNECTED"))
  .catch(err => console.error("DB ERROR:", err));
```

---

## 6. Frontend (Render Static Site)

### Root Directory

```text
frontend
```

### Build Command

```bash
npm install && npm run build
```

### Publish Directory

```text
dist
```

### Environment Variable

```env
VITE_API_URL=https://your-backend.onrender.com/api
```

---

## 7. Axios Setup

```js
import axios from "axios";

export default axios.create({
  baseURL: import.meta.env.VITE_API_URL
});
```

Usage:

```js
api.post("/auth/login", data);
```

Result:

```text
https://your-backend.onrender.com/api/auth/login
```

---

## 8. React Router Fix

Create:

```text
frontend/public/_redirects
```

Content:

```text
/ /index.html 200
/* /index.html 200
```

Without this:

```text
/login
/admin
/user
```

will 404 after refresh.

---

# Debugging Flow

Always follow:

```text
1. Browser Console
2. Network Tab
3. Request URL
4. Response Status
5. Response Body
6. Backend Logs
7. Database Logs
8. Code
```

---

# Common Status Meanings

|Status|Meaning|
|---|---|
|404|Wrong URL / Route|
|401|Auth issue|
|403|Permission issue|
|400|Validation issue|
|500|Backend crashed|
|ETIMEDOUT|DB connection problem|
|ECONNREFUSED|Host/Port wrong|
|ER_ACCESS_DENIED|Credentials wrong|
|Unknown database|DB_NAME wrong|

---

# Final Pre-Submission Checklist

```text
☐ Frontend deployed
☐ Backend deployed
☐ Railway DB connected
☐ DB_PORT configured
☐ SSL configured if required
☐ Login works
☐ Admin dashboard works
☐ User dashboard works
☐ Store Owner dashboard works
☐ Rating submission works
☐ Build passes
☐ README updated
☐ Demo URL tested in incognito
```

This checklist alone will prevent most deployment issues on React + Express + MySQL assignments.