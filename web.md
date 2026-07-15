Below are **concise interview-ready answers** for all major questions from the previous list. Use them for **rapid revision before interview**.

---

# 1. React Fundamentals – Answers

### What is React?

```text
React is a JavaScript library for building user interfaces using reusable components and virtual DOM for efficient rendering.
```

### What are components?

```text
Components are reusable building blocks of a React application that return UI elements.
```

### Functional vs Class components

```text
Functional: JavaScript functions using hooks
Class: ES6 classes using lifecycle methods
```

### JSX

```text
JSX is a syntax extension that allows writing HTML-like code inside JavaScript.
```

### Virtual DOM

```text
Virtual DOM is a lightweight copy of the real DOM used by React to detect changes and update only necessary elements.
```

### Props vs State

```text
Props: read-only data passed from parent
State: internal mutable data inside component
```

### One-way data binding

```text
Data flows from parent → child components.
```

### Hooks

```text
Hooks allow functional components to use state and lifecycle features.
```

### useState

```javascript
const [count, setCount] = useState(0)
```

Used to manage component state.

### useEffect

```javascript
useEffect(()=>{
  fetchData()
},[])
```

Runs side effects like API calls.

### useRef

```text
Stores mutable values without re-rendering.
```

### useContext

```text
Access global data without prop drilling.
```

### Prop drilling

```text
Passing props through multiple nested components.
```

### Controlled component

```text
Form element controlled by React state.
```

### Key in lists

```text
Unique identifier for React to track list changes.
```

### Fragment

```javascript
<>
   <Component/>
</>
```

Group elements without extra DOM node.

---

# 2. Redux – Answers

### What is Redux?

```text
Redux is a predictable state management library used to manage global application state.
```

### Why Redux?

```text
To manage shared state across multiple components.
```

### Three principles

```text
Single source of truth
State is read-only
Changes made using reducers
```

### Store

```text
Central container holding application state.
```

### Action

```text
Object describing what happened.
```

Example

```javascript
{ type: "ADD_TODO" }
```

### Reducer

```text
Function that updates state based on action.
```

### Dispatch

```text
Function used to send actions to reducer.
```

### Middleware

```text
Functions executed between action dispatch and reducer.
```

### Redux Thunk

```text
Middleware for handling asynchronous actions.
```

### Redux Saga

```text
Middleware for managing complex async flows using generators.
```

### Redux Toolkit

```text
Official modern way to write Redux code with less boilerplate.
```

---

# 3. React Native – Answers

### What is React Native?

```text
React Native is a framework for building cross-platform mobile apps using JavaScript and React.
```

### React vs React Native

```text
React → Web apps
React Native → Mobile apps
```

### Core components

```text
View
Text
Image
ScrollView
FlatList
TextInput
```

### ScrollView vs FlatList

```text
ScrollView renders all items.
FlatList renders only visible items (better performance).
```

### AsyncStorage

```text
Local storage system for saving small key-value data.
```

### Navigation

```text
Library used to move between screens in mobile apps.
```

Example libraries

```text
React Navigation
React Native Navigation
```

### Native modules

```text
Bridge JavaScript code with platform specific native code.
```

### Deep linking

```text
Open specific screen in app using URL.
```

---

# 4. React Performance Optimization

### Why React re-renders?

```text
When state or props change.
```

### React.memo

```javascript
export default React.memo(Component)
```

Prevents unnecessary re-renders.

### useMemo

```javascript
const value = useMemo(()=>compute(),[dep])
```

Memoizes expensive calculations.

### useCallback

```javascript
const fn = useCallback(()=>{},[])
```

Prevents function recreation.

### Virtualization

```text
Rendering only visible items in large lists.
```

### Bundle optimization

```text
Reducing app size using code splitting and tree shaking.
```

---

# 5. NodeJS – Answers

### What is NodeJS?

```text
NodeJS is a JavaScript runtime built on Chrome V8 engine for server-side development.
```

### Non-blocking I/O

```text
Node executes operations asynchronously without blocking main thread.
```

### Event loop

```text
Handles asynchronous callbacks in NodeJS.
```

### npm

```text
Node package manager used to install libraries.
```

### ExpressJS

```text
Minimal NodeJS framework for building APIs and servers.
```

Example

```javascript
const express = require("express")
const app = express()

app.get("/", (req,res)=>{
  res.send("Hello")
})
```

### Middleware

```text
Functions executed during request processing.
```

Example

```javascript
app.use(express.json())
```

### REST API

```text
API architecture using HTTP methods (GET POST PUT DELETE).
```

### JWT Authentication

```text
Token-based authentication system.
```

### CORS

```text
Cross-Origin Resource Sharing allows APIs to be accessed from different domains.
```

### Clustering

```text
Using multiple CPU cores to scale NodeJS application.
```

---

# 6. MySQL – Answers

### What is MySQL?

```text
MySQL is a relational database management system used to store structured data.
```

### Primary key

```text
Unique identifier for each row in table.
```

### Foreign key

```text
Reference to primary key in another table.
```

### SQL vs NoSQL

```text
SQL → relational structured database
NoSQL → non relational flexible schema
```

### Normalization

```text
Process of organizing data to reduce redundancy.
```

### Index

```text
Improves database query performance.
```

### Join

```text
Combine data from multiple tables.
```

Types

```text
INNER JOIN
LEFT JOIN
RIGHT JOIN
FULL JOIN
```

### ACID

```text
Atomicity
Consistency
Isolation
Durability
```

---

# 7. WebRTC – Answers

### What is WebRTC?

```text
Technology enabling real-time peer-to-peer audio, video and data communication.
```

### Peer-to-peer

```text
Direct connection between two clients without intermediate server.
```

### RTCPeerConnection

```text
API that establishes connection between peers.
```

### getUserMedia()

```text
Access camera and microphone.
```

### DataChannel

```text
Send arbitrary data between peers.
```

### STUN server

```text
Helps find public IP address.
```

### TURN server

```text
Relay server when direct connection fails.
```

### Signaling server

```text
Used to exchange connection information between peers.
```

### ICE candidate

```text
Possible network path for peer connection.
```

---

# 8. HTML / CSS – Answers

### Semantic HTML

```text
HTML elements that describe meaning (article, section, header).
```

### Flexbox

```text
Layout system for one-dimensional layouts.
```

### CSS Grid

```text
Two-dimensional layout system.
```

### Responsive design

```text
Design that adapts to different screen sizes.
```

### Media query

```css
@media (max-width:768px)
```

### Box model

```text
Content
Padding
Border
Margin
```

### Margin vs Padding

```text
Margin → outside spacing
Padding → inside spacing
```

---

# 9. App Deployment

### APK vs AAB

```text
APK → installable Android package
AAB → Android App Bundle optimized by Play Store
```

### Keystore

```text
File used to sign Android apps before publishing.
```

### Play Store upload

```text
Create app → upload AAB → fill details → release.
```

### Provisioning profile

```text
Certificate used for iOS app signing.
```

### TestFlight

```text
Apple tool for beta testing iOS apps.
```

---

# 10. Project Questions – Sample Answers

### Explain your project

```text
I developed a car service management system that allows users to book vehicle services, track repair status, and view service history. The system includes a frontend interface, backend API and database for service management.
```

### Problems faced

```text
Handling real-time updates and optimizing database queries.
```

### Solution

```text
Implemented API optimization and caching.
```

### Database design

```text
Used relational tables for users, services, bookings and status tracking.
```

---

# 11. Rapid Fire Answers

### let vs var vs const

```text
var → function scoped
let → block scoped
const → block scoped and immutable
```

### Promise vs async/await

```text
Async/await is syntactic sugar over promises for cleaner async code.
```

### Map vs forEach

```text
map returns new array
forEach does not
```

### null vs undefined

```text
null → intentional empty value
undefined → variable not assigned
```

### == vs ===

```text
== compares value
=== compares value and type
```

### REST vs GraphQL

```text
REST → multiple endpoints
GraphQL → single endpoint flexible queries
```

### HTTP vs HTTPS

```text
HTTPS is encrypted using SSL/TLS.
```

### JWT vs Session

```text
JWT → stateless token authentication
Session → server stored authentication
```

---

✅ If you want **next-level preparation**, I can also give:

- **50 React Native coding interview problems**
    
- **NodeJS backend coding questions**
    
- **System design questions startups ask**
    
- **Exact questions asked in React Native startup interviews in India**
    

This will **increase your chances of clearing the interview by 3–4x.**