# Database-Normalization-Postgres-Installation-and-Application-Insight

Case Study File Link: https://lily-plate-b6a.notion.site/Case-Study-082bcd700e034e0b85a54bf82ba590ab?pvs=4

# Case Study

A Medical Database System is needed to enhance the efficiency and effectiveness of healthcare services. This system will be able to seamlessly integrates the information of patients, doctors, appointments, medical records, and medical facilities.

**Entities:**

1. **Patients:**
   - Attributes: PatientID (Primary Key), FirstName, LastName, DateOfBirth, Gender, ContactNumber, Email
2. **Doctors:**
   - Attributes: DoctorID (Primary Key), FirstName, LastName, Specialization, ContactNumber, Email
3. **Appointments:**
   - Attributes: AppointmentID (Primary Key), PatientID (Foreign Key), DoctorID (Foreign Key), AppointmentDate, AppointmentTime, Status
4. **Medical Records:**
   - Attributes: RecordID (Primary Key), AppointmentID (Foreign Key), Diagnosis, Prescription, TestResults, createdAt
5. **Medical Facilities:**
   - Attributes: FacilityID (Primary Key), FacilityName, Location, ContactNumber

**Relationships:**

- Patients can have multiple appointments with different doctors.
- Doctors can have multiple appointments with different patients.
- Each appointment may have a corresponding medical record, and vice versa.
- A medical facility can have multiple doctors, and a doctor can work in multiple medical facilities.
- This relationship is represented through a junction table.

## 6-1 Understanding Anomalies

- Anomalies in database refer to inconsistency or unexpected issues that can occur during data manipulation and retrieval

##### Anomalies are main three Types

1. Update anomalies
   ![alt text](<WhatsApp Image 2025-05-12 at 18.31.51_41f3ea48.jpg>)
2. Delete anomalies
   ![alt text](<WhatsApp Image 2025-05-12 at 18.33.04_c734c463.jpg>)
3. Insert Anomalies
   ![alt text](<WhatsApp Image 2025-05-12 at 18.33.37_5aee9460.jpg>)
   ![alt text](<WhatsApp Image 2025-05-12 at 18.35.54_a5742ffd.jpg>)

- Data Reparation Is also one kind of anomalies
- To Avoid these anomalies we have to understand what data should be separate. Like user info will be one table branch will be in one table and address will be in one table and rference the data to required table.
  ![alt text](<WhatsApp Image 2025-05-12 at 18.38.51_883594ef.jpg>)
- Here comes the Normalization Concept.

##### What is Normalization?

- Makes database structure nice and if there is any anomalies and redundancies these are step by step removed.

![alt text](<WhatsApp Image 2025-05-12 at 18.41.39_c75434e3.jpg>)

- User Info are separated and branch info are separated and the branch id (primary key) is placed inside the user information as foreign key.
