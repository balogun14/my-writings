## **1. Overview**
The ride-tracking application, **Mauvigo**, is designed to provide real-time ride updates, seamless user experiences, and robust backend infrastructure. The system supports web and mobile platforms, focusing on scalability, performance, and integration with modern technologies. It aims to connect international travelers with vetted local drivers, ensuring safe, reliable, and culturally immersive transportation experiences.

---

## **2. Key Features**
- **Real-Time Ride Tracking**: Track rides in real-time using WebSockets.
- **Payment Processing**: Secure payments via Stripe.
- **Map Integration**: Use Google Maps API and Leaflet.js for location visualization.
- **Cloud Storage**: Store ride-related files (e.g., invoices, images) in MinIO.
- **Database**: Use Redis for caching and PostgreSQL for structured data storage.
- **Cross-Platform Support**: Web (Next.js) and Mobile (Flutter).
- **Scalability**: Handle high traffic and concurrent users with cloud-based infrastructure.

---

## **3. Tech Stack**

### **Frontend**
- **Web**: Next.js (React-based framework)
  - Leverages server-side rendering (SSR) and static site generation (SSG) for SEO and performance.
  - Integrates with Google Maps API and Leaflet.js for map rendering.
- **Mobile**: Flutter
  - Cross-platform framework for iOS and Android apps.
  - Reuses business logic and APIs from the backend.

### **Backend**
- **APIs**: Built using Nest.js API routes.
  - Handles RESTful APIs for ride management, user authentication, and payment processing.
- **Real-Time Communication**: WebSocket for live updates.
- **Authentication**: JWT (JSON Web Tokens) for secure authentication.

### **Database**
- **Primary Database**: PostgreSQL
  - Stores structured data like user profiles, ride history, and payment details.
- **Caching**: Redis
  - Caches frequently accessed data like driver locations and session tokens.

### **Cloud Storage**
- **MinIO**:
  - Self-hosted object storage solution for storing ride-related files (e.g., invoices, receipts).

### **Payment Gateway**
- **Stripe**:
  - Handles secure online payments, including credit cards and digital wallets.

### **Maps**
- **Google Maps API**:
  - Provides geocoding, routing, and traffic data.
- **Leaflet.js**:
  - Lightweight library for rendering interactive maps.

### **Real-Time Updates**
- **WebSocket**:
  - Enables real-time communication between the backend and frontend for features like live ride tracking.

---

## **4. High-Level Architecture**

```plaintext
+---------------------------+
|       Frontend Layer      |
|  - Web: Next.js           |
|  - Mobile: Flutter        |
+---------------------------+
             |
             v
+---------------------------+
|       API Gateway         |
|  - Next.js API Routes     |
|  - WebSocket Integration  |
+---------------------------+
             |
             v
+---------------------------+
|       Backend Services    |
|  - Ride Management        |
|  - Payment Processing     |
|  - Real-Time Updates      |
+---------------------------+
             |
             v
+---------------------------+
|       Data Layer          |
|  - PostgreSQL (Primary DB)|
|  - Redis (Caching)        |
|  - MinIO (Cloud Storage)  |
+---------------------------+
             |
             v
+---------------------------+
|       Infrastructure      |
|  - AWS / GCP (Cloud Hosting)|
|  - Docker (Containerization)|
+---------------------------+
```

---

## **5. UML Use Case Diagram (Mermaid Format)**

```mermaid
usecaseDiagram
    actor Traveler
    actor Driver
    actor Admin

    Traveler -- (Register & Create Profile)
    Traveler -- (Book Ride)
    Traveler -- (Negotiate Fare)
    Traveler -- (Make Payment via Stripe)
    Traveler -- (Track Ride in Real-Time)
    Traveler -- (Rate Driver & Provide Feedback)
    Traveler -- (View Trip History & Receipts)

    Driver -- (Register & Complete Vetting)
    Driver -- (Receive Ride Requests)
    Driver -- (Accept/Counter Fare)
    Driver -- (Navigate to Pickup/Drop-off)
    Driver -- (View Earnings & Payouts)

    Admin -- (Manage Users & Drivers)
    Admin -- (Approve/Suspend Accounts)
    Admin -- (Monitor Analytics & Reports)
    Admin -- (Handle Disputes & Support)

    (Book Ride) --> (Negotiate Fare)
    (Negotiate Fare) --> (Make Payment via Stripe)
    (Make Payment via Stripe) --> (Track Ride in Real-Time)
    (Track Ride in Real-Time) --> (Rate Driver & Provide Feedback)
    (Rate Driver & Provide Feedback) --> (View Trip History & Receipts)

    (Receive Ride Requests) --> (Accept/Counter Fare)
    (Accept/Counter Fare) --> (Navigate to Pickup/Drop-off)
    (Navigate to Pickup/Drop-off) --> (View Earnings & Payouts)
```

---

## **6. Explanation of the UML Use Case Diagram**
The **UML Use Case Diagram** captures the primary interactions between actors (Traveler, Driver, Admin) and the system's core functionalities:

### **Traveler Use Cases**
- **Register & Create Profile**: Sign up via email, phone, or social media.
- **Book Ride**: Enter destination details, propose a fare, and select a driver.
- **Negotiate Fare**: Engage in fare negotiation with drivers.
- **Make Payment via Stripe**: Process payments securely using Stripe.
- **Track Ride in Real-Time**: Monitor the ride's progress on an interactive map.
- **Rate Driver & Provide Feedback**: Post-ride rating and detailed feedback.
- **View Trip History & Receipts**: Access past rides and export receipts.

### **Driver Use Cases**
- **Register & Complete Vetting**: Undergo background checks, license verification, and vehicle inspection.
- **Receive Ride Requests**: Get notified of ride requests with traveler details.
- **Accept/Counter Fare**: Accept or counter the proposed fare.
- **Navigate to Pickup/Drop-off**: Use GPS navigation with real-time traffic updates.
- **View Earnings & Payouts**: Access earnings dashboard and choose payout methods.

### **Admin Use Cases**
- **Manage Users & Drivers**: Approve, suspend, or modify traveler/driver accounts.
- **Monitor Analytics & Reports**: Generate insights into rides completed, revenue, and user growth.
- **Handle Disputes & Support**: Resolve disputes and provide customer support.

