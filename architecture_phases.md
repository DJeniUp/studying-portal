## MVP Architecture

This diagram represents the minimum components required for a fully functioning MVP learning platform. It includes essential backend services, frontend applications, real-time communication, and database storage.

**Included in MVP:**

* Web Student App / Web Teacher App
* API Gateway
* Auth Service & Account Service
* Lesson & Assignment Service
* Real-Time Service
* Notification Service
* External Video Call API
* Email/Push Provider
* Users, Lessons, Assignments, Submissions Databases
<img width="2140" height="1200" alt="diagram" src="https://github.com/user-attachments/assets/55187dba-8b16-462a-b5d1-8c48cd0fbf98" />


---

## Phase I Architecture

Phase I extends the MVP by adding the production-level features required to safely release and operate the system at scale.

**New components added in Phase I:**

* **Rate Limiting & WAF:** Protect API Gateway from overload/attacks
* **Admin Dashboard:** Manage users, lessons, reports
* **Customer Support Panel:** Extended beyond MVP
* **Task Queue / Worker Services:** For handling notifications, scheduled tasks, webhook processing
* **Email verification + password reset flows**

* <img width="2640" height="1460" alt="diagram (1)" src="https://github.com/user-attachments/assets/e8c4ab23-b758-491f-ab13-b3b87d4d3e8d" />




### **Planned Phase II Additions:**

* **Plagiarism Detection** – Compare answers across students.
* **Advanced Analytics Dashboard** – Engagement, progress, student performance trends.
* **Scheduling Engine** – Teacher availability, automatic lesson booking.
* **Group Lessons Support** – Multi-user video rooms.
* **Offline Mode (mobile/tablet)** – Local caching of lessons.
* **Payment Integration (Stripe)** – Subscriptions, paid lessons.
* **Caching Layer (Redis)** – Faster retrieval of lessons/assignments.
* **Load Balancers & Autoscaling** – Prepare for high-traffic usage.

### Why these are Phase II:

* They are not required for a functioning teaching workflow.
* They require larger engineering investment.
* Many depend on MVP + Phase I telemetry and usage patterns.
* They improve long-term retention and product quality.

---

## Future Phases

These are potential future developments based on user growth and long-term opportunities.

### **Potential future features:**

* **Adaptive Learning Engine** – Personalized lesson paths.
* **Recommendation System** – Suggest tasks, lessons, or teachers.
* **Integration with external LMS (Moodle, Canvas)** – Import/export lessons.

