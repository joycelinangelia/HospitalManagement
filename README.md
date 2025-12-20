# Hospital Management System
This system is designed to help hospitals manage patients, doctors, and other critical information effectively and simply. It features a robust database backend with normalized tables and a set of core administrative and medical functionalities.



## 🚀 System Features
The system provides tailored functionalities for three main user roles:

### 1. Patient Features
* **Account Registration**: Patients can register in the system to obtain a unique **Patient ID**.
* **Profile Management**: Patients can update their contact information (though they cannot modify their medical treatment records).

### 2. Doctor Features
* **Secure Login**: Doctors use a **Doctor ID** to access the system.
* **Medical Record Management**: Doctors can add, modify, or view treatment records for the patients they are responsible for.
* **Patient Search**: Ability to query specific patient data and medical history.

### 3. Admin Features
* **Personnel Management**: Admins can add, modify, or view information related to doctors within the hospital.




## 📊 Database Architecture

### Entity-Relationship Diagram (ERD)
The system's logic is built upon the following key entities and relationships:

* **Departments**: Contain multiple Doctors (**Have** relationship).
* **Doctors**: Treat Patients and generate medical Records (**Treat** relationship).
* **Patients**: Have personal records and contact details.
* **Records**: Store diagnosis, treatment details, and appointment dates.
* **Admin**: Manages the creation and maintenance of Doctor profiles (**Create** relationship).



### Normalization & Integrity

To ensure data integrity and reduce redundancy, all tables are designed to meet **3NF (Third Normal Form)** and **BCNF (Boyce-Codd Normal Form)** standards.

| Table | Primary Key | Description |
| --- | --- | --- |
| `departments` | `dpt_ID` | Stores hospital department names.

 |
| `doctors` | `doc` | Stores doctor profiles, specialties, and credentials.

 |
| `patients` | `pat` | Stores patient personal data and contact info.

 |
| `record` | `case_ID` | Stores medical history including diagnosis and treatment.

 |



## 💻 Implementation Details

### Technology Stack
* **Database**: MySQL (InnoDB Engine).
* **Character Set**: `utf8mb4` for full Unicode support.
* **Backend Interface**: Node.js/JavaScript (using `Server.query` for DML operations).


### Core SQL Operations
The project implements standard CRUD and advanced join/aggregation queries:

* **Add Functions**: Procedures for registering new patients, doctors, and medical records .
  
* **Join Queries**:
* Fetching doctors based on their specific department .
* Retrieving comprehensive patient records by joining `record`, `doctors`, and `patients` tables .

* **Search Functionality**: A complex `LEFT JOIN` query that allows searching medical records by patient name, ID, room, or diagnosis .

* **Aggregation**: Using `COUNT(*)` to verify if a patient exists before adding a new record .
