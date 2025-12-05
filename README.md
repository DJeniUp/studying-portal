# studying-portal

A realtime educational platform for communication between teachers and students, integrating a video call API, assignment management, and realtime progress tracking.The platform provides multiple frontends for web(student and teacher side), a backend for authentication and lesson management, and external integrations for video conferencing and notifications.

1. System Elements

Users:
Students: Could view lessons, submit assignments, and participate in video calls.
Teachers/tutor: Could create lessons, assign tasks, track student progress, and start video calls
Customer Service 

Frontend:
Web application for teachers and students.

Backends:
AuthN and AuthZ: Manages user registration, login, roles, and permissions
Lesson and Assignment Service: Manages lessons, tasks, submission tracking, and real-time progress updates
RealTime Communication Service: Integrates with external video call API and handles live updates
Notification Service: Sends email/push notifications

Data Stores:
PostgreSQL: users, lessons, assignments, submissions

2. Architectural Patterns
Microservices

3. How Components Communicate

Frontend → API Gateway
  REST (HTTPS)
  WebSockets for real-time updates
  JWT in Authorization header
API Gateway → Backend Services
  Internal REST calls
  Uses service-to-service authentication
Lesson Service → Real-Time Service
  Publishes events via message queue (async)
  e.g.
  assignment.completed,
  student.joined,
  teacher.startedLesson
RealTime Service → Frontend
  WebSocket push updates
  Sends:
    progress bars
    “student submitted answer”
    presence changes
Backend → External Services
  HTTPS to:
    Video API
    Email provider
  Webhook support for video session events

4. AuthN and AuthZ
AuthZ — Authorization
  Model used:
    Role-Based Access Control (RBAC)
      Student
      Teacher
      Admin
  Examples:
    Only teachers may create assignments
    Students can only update their own submissions
    Admins can manage users but not content

