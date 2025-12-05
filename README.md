# studying-portal

A realtime educational platform for communication between teachers and students, integrating a video call API, assignment management, and realtime progress tracking.The platform provides multiple frontends for web(student and teacher side), a backend for authentication and lesson management, and external integrations for video conferencing and notifications. <br>

1. System Elements <br>

Users: <br>
Students: Could view lessons, submit assignments, and participate in video calls. <br>
Teachers/tutor: Could create lessons, assign tasks, track student progress, and start video calls <br>
Customer Service  <br>

Frontend: <br>
Web application for teachers and students. <br>

Backends: <br>
AuthN and AuthZ: Manages user registration, login, roles, and permissions <br>
Lesson and Assignment Service: Manages lessons, tasks, submission tracking, and real-time progress updates <br>
RealTime Communication Service: Integrates with external video call API and handles live updates <br>
Notification Service: Sends email/push notifications <br>

Data Stores: <br>
PostgreSQL: users, lessons, assignments, submissions

2. Architectural Patterns <br>
Microservices

3. How Components Communicate

Frontend → API Gateway <br>
  REST (HTTPS) <br>
  WebSockets for real-time updates <br>
  JWT in Authorization header <br>
API Gateway → Backend Services <br>
  Internal REST calls <br>
  Uses service-to-service authentication <br>
Lesson Service → Real-Time Service <br>
  Publishes events via message queue (async) <br>
  e.g. <br>
  assignment.completed, <br>
  student.joined, <br>
  teacher.startedLesson <br>
RealTime Service → Frontend <br>
  WebSocket push updates <br>
  Sends: <br>
    progress bars <br>
    “student submitted answer” <br>
    presence changes <br>
Backend → External Services <br>
  HTTPS to: <br>
    Video API <br>
    Email provider <br>
  Webhook support for video session events <br>

4. AuthN and AuthZ <br>
AuthZ — Authorization <br>
  Model used: <br>
    Role-Based Access Control (RBAC) <br>
      Student <br>
      Teacher <br>
      Admin <br>
  Examples: <br>
    Only teachers may create assignments <br>
    Students can only update their own submissions <br>
    Admins can manage users but not content <br>

