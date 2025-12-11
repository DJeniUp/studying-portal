# System User Flows Documentation

## 1. Core User Flows 

### 1. User signs up

**Involves:** Web App -> API Gateway -> Auth Service -> Account Service -> Users DB

### 2. User logs in and establishes WebSocket connection

**Involves:** Web App -> API Gateway -> Auth Service -> Real-Time Service

### 3. Teacher creates a lesson

**Involves:** Web Teacher App -> API Gateway -> Lesson Service -> Lessons DB -> Notification Service

### 4. Teacher creates an assignment

**Involves:** Web Teacher App -> API Gateway -> Lesson & Assignment Service -> Lessons DB -> Notification Service -> Real-Time Service

### 5. Student joins a video lesson

**Involves:** Web Student App -> API Gateway -> Lesson Service -> Video Call API

### 6. Student submits assignment

**Involves:** Web Student App -> API Gateway -> Assignment Service -> Submissions DB -> Real-Time Service -> Notification Service

### 7. Teacher reviews a submission

**Involves:** Web Teacher App -> API Gateway -> Assignment Service -> Submissions DB

### 8. Real-time presence tracking

**Involves:** Web App <-> Real-Time Service <-> Lesson Service

### 9. System sends notifications

**Involves:** Notification Service -> Email/Push Provider

### 10. Customer support views data

**Involves:** Customer Service App -> Customer Service Backend -> Users DB / Lessons DB

---

## 2. Unique User Flows

### A. Real-time homework submission + updates

Student submits -> stored -> event -> teacher receives WebSocket update.

### B. Automatic assignment creation + notifications

Teacher creates assignment -> students notified -> real-time dashboard updates.

### C. Student joins live video lesson (external API)

Lesson service communicates with external video API -> provides join URL.

### D. Real-time presence tracking

WebSocket connection updates "who is online" across dashboards.

---


