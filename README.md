## **🏥 Hospital Management System**

### **📋 Project Description**

This project is a comprehensive database management system designed for hospitals to efficiently track and manage patient data, appointments, medical records, staff information, billing, and inventory. The database schema provides a foundation for a complete hospital information system that can be implemented in any healthcare facility.

---

### **🛠️ Setup Instructions**

Prerequisites
MySQL Server 5.7+ or MariaDB 10.2+
MySQL Workbench (recommended for easy import)
How to Import the SQL Database
Clone this repository to your local machine
Connect to your MySQL server using your preferred client
Import the hospital_management_system.sql file using one of these methods:
mysql -u username -p < hospital_management_system.sql
Or use MySQL Workbench's data import feature:
Open MySQL Workbench
Connect to your MySQL server
Go to Server > Data Import
Choose "Import from Self-Contained File" and select the SQL file
Start Import
The database will be created with all tables, relationships, and constraints

---

### **📊 Entity Relationship Diagram (ERD)**

/Users/brendaamunga/Desktop/ERD_Hotel_Management.png 

The ERD shows the complete database structure with all entities and their relationships:

20+ interconnected tables
Proper primary and foreign key relationships
Fields with appropriate data types
One-to-one, one-to-many, and many-to-many relationships
✨ Database Features
👤 Patient registration and management
👨‍⚕️ Doctor and staff information management
📅 Appointment scheduling and tracking
📝 Medical records management
💊 Medication and inventory tracking
💵 Billing and payment processing
🔒 Insurance claims management
🛏️ Room allocation and management
🔬 Laboratory test ordering and results tracking
⏰ Doctor scheduling and availability management

---

### **🗄️ Key Database Entities**

Patients: Personal and medical information about patients
Staff: Information about all hospital staff members
Doctors: Extended information about medical practitioners
Departments: Hospital departments and specialties
Appointments: Scheduled patient visits
Medical Records: Patient diagnosis and treatment history
Medications: Drugs available at the hospital pharmacy
Rooms: Hospital rooms for patient stays
Laboratory Tests: Available diagnostic procedures
Billing & Invoicing: Financial transaction records

---

**📝 Usage Examples**

Once installed, connect to the hospital_management database to run queries like:

sql
-- Find all appointments for a specific patient
SELECT a.appointment_id, a.appointment_date, a.start_time, 
       CONCAT(d.first_name, ' ', d.last_name) AS doctor_name,
       dep.department_name, s.status_name
FROM appointments a
JOIN patients p ON a.patient_id = p.patient_id
JOIN doctors doc ON a.doctor_id = doc.doctor_id
JOIN staff d ON doc.staff_id = d.staff_id
JOIN departments dep ON a.department_id = dep.department_id
JOIN appointment_status s ON a.status_id = s.status_id
WHERE p.patient_id = 1
ORDER BY a.appointment_date, a.start_time;

---

**📄 License**

This project is licensed under the MIT License - see the LICENSE file for details.

