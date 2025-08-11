# Schema Design – Smart Clinic Management System

## MySQL Database Design

Relational data like core records, user identities, appointments, and clinic operations are best handled in a structured SQL schema.

### Table: patients
- id: INT, Primary Key, AUTO_INCREMENT
- full_name: VARCHAR(100), NOT NULL
- date_of_birth: DATE
- gender: ENUM('Male', 'Female', 'Other')
- phone: VARCHAR(15), UNIQUE, NOT NULL
- email: VARCHAR(100), UNIQUE
- address: TEXT
- created_at: TIMESTAMP DEFAULT CURRENT_TIMESTAMP

### Table: doctors
- id: INT, Primary Key, AUTO_INCREMENT
- full_name: VARCHAR(100), NOT NULL
- specialization: VARCHAR(100), NOT NULL
- phone: VARCHAR(15), UNIQUE, NOT NULL
- email: VARCHAR(100), UNIQUE
- clinic_location: VARCHAR(255)
- created_at: TIMESTAMP DEFAULT CURRENT_TIMESTAMP

### Table: appointments
- id: INT, Primary Key, AUTO_INCREMENT
- patient_id: INT, Foreign Key → patients(id), NOT NULL
- doctor_id: INT, Foreign Key → doctors(id), NOT NULL
- appointment_time: DATETIME, NOT NULL
- status: ENUM('Scheduled', 'Completed', 'Cancelled') DEFAULT 'Scheduled'
- created_at: TIMESTAMP DEFAULT CURRENT_TIMESTAMP

> Appointments are tied to both doctor and patient. If a patient is deleted, their appointments should also be deleted (ON DELETE CASCADE). Doctors should not have overlapping appointment times – validate in application logic.

### Table: admin
- id: INT, Primary Key, AUTO_INCREMENT
- username: VARCHAR(50), UNIQUE, NOT NULL
- password_hash: VARCHAR(255), NOT NULL
- role: ENUM('Admin', 'Staff') DEFAULT 'Admin'
- created_at: TIMESTAMP DEFAULT CURRENT_TIMESTAMP

### Table: doctor_availability
- id: INT, Primary Key, AUTO_INCREMENT
- doctor_id: INT, Foreign Key → doctors(id), NOT NULL
- day_of_week: ENUM('Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday')
- start_time: TIME
- end_time: TIME

> Allows flexible setting of working hours per doctor.

### Table: payments
- id: INT, Primary Key, AUTO_INCREMENT
- appointment_id: INT, Foreign Key → appointments(id), NOT NULL
- amount: DECIMAL(8,2), NOT NULL
- status: ENUM('Pending', 'Paid', 'Failed') DEFAULT 'Pending'
- payment_method: ENUM('Cash', 'Card', 'Online')
- transaction_date: DATETIME

## MongoDB Collection Design

Use MongoDB for flexible or evolving data like prescriptions, doctor notes, logs, chat messages, etc.

### Collection: prescriptions
```json
{
  "_id": "ObjectId('64abc123456')",
  "appointmentId": 51,
  "patientId": 12,
  "doctorId": 7,
  "medications": [
    {
      "name": "Paracetamol",
      "dosage": "500mg",
      "instructions": "Take 1 tablet every 6 hours"
    },
    {
      "name": "Ibuprofen",
      "dosage": "200mg",
      "instructions": "After meals, if fever persists"
    }
  ],
  "doctorNotes": "Patient showing mild flu symptoms. Prescribed rest for 3 days.",
  "refillCount": 2,
  "pharmacy": {
    "name": "Wellness Pharmacy",
    "location": "Main Street, Building 2"
  },
  "issuedDate": "2025-08-10T10:30:00Z"
}
