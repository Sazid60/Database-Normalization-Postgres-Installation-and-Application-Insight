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
- To Avoid these anomalies we have to understand what data should be separate. Like user info will be one table branch will be in one table and address will be in one table and reference the data to required table.
  ![alt text](<WhatsApp Image 2025-05-12 at 18.38.51_883594ef.jpg>)
- Here comes the Normalization Concept.

##### What is Normalization?

- Makes database structure nice and if there is any anomalies and redundancies these are step by step removed.

![alt text](<WhatsApp Image 2025-05-12 at 18.41.39_c75434e3.jpg>)

- User Info are separated and branch info are separated and the branch id (primary key) is placed inside the user information as foreign key.

## 6-2 Understanding the Functional Dependencies

#### Normalization in-depth and normalization Properties

- Normalization is a technique by using which we can remove the anomalies in the tables we can remove step by step.
- To understand the normalization we have to understand two topics
  1. Functional Dependencies
  2. Normal Forms

#### Functional Dependencies

- Functional Dependency in simple term means that the value of one attribute (or set of attributes) uniquely determines the value of another attribute(S) in a database.

![alt text](<WhatsApp Image 2025-05-12 at 18.57.23_6b1ebe9c.jpg>)

- According to the table if we know the value of x then we can determine y.

![alt text](<WhatsApp Image 2025-05-12 at 18.59.07_8168f568.jpg>)

- In This case as x value 2 is duplicate so it can give any value among the two. In This case there will be no functional dependency.

![alt text](<WhatsApp Image 2025-05-12 at 19.02.03_597c0991.jpg>)

- In this case as being duplicate but the values are same we can say this has functional dependency.

##### To determine the dependency we have a formula

![alt text](<WhatsApp Image 2025-05-12 at 19.22.24_6eabc25c.jpg>)
x-->y

###### Formula

- If duplication exists then we will use this formula
  for t1.x = t2.x
  then t1.y = t2.y
- Its telling 2 value of x if the corresponding values of 2 y is same then we can say its functionally dependent.

![alt text](<WhatsApp Image 2025-05-12 at 19.32.21_c09ecb04.jpg>)

- This is not a functional dependent table.

![alt text](<WhatsApp Image 2025-05-12 at 19.33.31_86b2c04d.jpg>)

- This is a Functional Dependent table if we consider EmployeeID and EmployeeName.
- If we Consider EmployeeName and Department its not functionally dependent.
