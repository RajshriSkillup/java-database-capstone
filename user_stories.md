### **Admin User Stories**

---

**Title:**
*As an admin, I want to log into the portal with my username and password, so that I can manage the platform securely.*

**Acceptance Criteria:**

1. Admin can access login page.
2. Admin can input valid credentials.
3. System grants access upon successful authentication.

**Priority:** High
**Story Points:** 2
**Notes:**

* Handle invalid login attempts gracefully.

---

**Title:**
*As an admin, I want to log out of the portal, so that I can protect system access.*

**Acceptance Criteria:**

1. Admin sees logout option post-login.
2. Logout ends the session securely.
3. Post-logout, admin is redirected to login page.

**Priority:** High
**Story Points:** 1
**Notes:**

* Clear all session tokens on logout.

---

**Title:**
*As an admin, I want to add doctors to the portal, so that I can onboard them into the system.*

**Acceptance Criteria:**

1. Admin can fill doctor profile form.
2. System validates and stores the data.
3. Doctor is listed after addition.

**Priority:** High
**Story Points:** 3
**Notes:**

* Validate unique email and license details.

---

**Title:**
*As an admin, I want to delete a doctor’s profile from the portal, so that I can manage outdated or invalid records.*

**Acceptance Criteria:**

1. Admin can select a doctor profile.
2. Admin confirms deletion.
3. System removes profile and updates records.

**Priority:** Medium
**Story Points:** 2
**Notes:**

* Ensure confirmation before permanent deletion.

---

**Title:**
*As an admin, I want to run a stored procedure in MySQL CLI to get the number of appointments per month, so that I can track usage statistics.*

**Acceptance Criteria:**

1. Stored procedure returns accurate monthly data.
2. Procedure can be executed with a simple command.
3. Output is easy to interpret and export.

**Priority:** Medium
**Story Points:** 3
**Notes:**

* Document SQL procedure execution steps.

---

### **Patient User Stories**

---

**Title:**
*As a patient, I want to view a list of doctors without logging in, so that I can explore options before registering.*

**Acceptance Criteria:**

1. Doctors list is publicly accessible.
2. List shows names, specializations, and contact info.
3. Option to proceed to sign-up is available.

**Priority:** High
**Story Points:** 2
**Notes:**

* Do not expose sensitive doctor details.

---

**Title:**
*As a patient, I want to sign up using my email and password, so that I can book appointments.*

**Acceptance Criteria:**

1. Sign-up form validates required fields.
2. Confirmation email is sent post-registration.
3. Account is created successfully.

**Priority:** High
**Story Points:** 3
**Notes:**

* Ensure unique email validation.

---

**Title:**
*As a patient, I want to log into the portal, so that I can manage my bookings.*

**Acceptance Criteria:**

1. Login page accepts valid credentials.
2. User is redirected to dashboard post-login.
3. Sessions are managed securely.

**Priority:** High
**Story Points:** 2
**Notes:**

* Ensure encryption for credentials.

---

**Title:**
*As a patient, I want to log out of the portal, so that I can secure my account.*

**Acceptance Criteria:**

1. Logout option is easily accessible.
2. Logout clears session and redirects to login page.
3. Account cannot be accessed without re-login.

**Priority:** High
**Story Points:** 1
**Notes:**

* Auto-logout after inactivity.

---

**Title:**
*As a patient, I want to book an hour-long appointment, so that I can consult with a doctor.*

**Acceptance Criteria:**

1. Patients can select available slots.
2. Booking confirms duration and doctor.
3. Confirmation is visible on dashboard.

**Priority:** High
**Story Points:** 3
**Notes:**

* Validate appointment conflicts.

---

**Title:**
*As a patient, I want to view my upcoming appointments, so that I can prepare accordingly.*

**Acceptance Criteria:**

1. Dashboard shows list of future appointments.
2. Details include date, time, doctor, and location.
3. Ability to cancel if needed.

**Priority:** High
**Story Points:** 2
**Notes:**

* Include reminder notifications.

---

### **Doctor User Stories**

---

**Title:**
*As a doctor, I want to log into the portal, so that I can manage my appointments.*

**Acceptance Criteria:**

1. Login page accepts valid credentials.
2. Doctor is directed to appointments dashboard.
3. Session management is secure.

**Priority:** High
**Story Points:** 2
**Notes:**

* Follow security best practices.

---

**Title:**
*As a doctor, I want to log out of the portal, so that I can protect my data.*

**Acceptance Criteria:**

1. Logout ends the session cleanly.
2. Redirect to login page post-logout.
3. Data access is blocked after logout.

**Priority:** High
**Story Points:** 1
**Notes:**

* Include session timeout for inactivity.

---

**Title:**
*As a doctor, I want to view my appointment calendar, so that I can stay organized.*

**Acceptance Criteria:**

1. Calendar view shows upcoming appointments.
2. Appointments include patient and timing details.
3. Ability to navigate between dates.

**Priority:** High
**Story Points:** 3
**Notes:**

* Sync with external calendar optional.

---

**Title:**
*As a doctor, I want to mark my unavailability, so that patients only see my available slots.*

**Acceptance Criteria:**

1. Doctors can set unavailable dates/times.
2. System updates scheduling options for patients.
3. Calendar reflects changes in real-time.

**Priority:** High
**Story Points:** 3
**Notes:**

* Prevent booking conflicts during unavailable periods.

---

**Title:**
*As a doctor, I want to update my profile with specialization and contact information, so that patients have up-to-date information.*

**Acceptance Criteria:**

1. Editable profile fields for specialization and contacts.
2. Changes saved and reflected publicly.
3. Admin approval optional.

**Priority:** Medium
**Story Points:** 2
**Notes:**

* Profile completeness indicator.

---

**Title:**
*As a doctor, I want to view patient details for upcoming appointments, so that I can be prepared.*

**Acceptance Criteria:**

1. Appointment details include patient name and medical history.
2. Data access restricted to assigned appointments.
3. Secure handling of patient data.

**Priority:** High
**Story Points:** 3
**Notes:**

* Follow HIPAA or similar compliance.
