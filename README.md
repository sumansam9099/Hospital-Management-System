# Hospital-Management-System
This project is a Hospital Management System designed to store and manage information about patients, doctors, appointments, treatments, and prescriptions. The database helps the hospital maintain accurate medical records, track patient visits, and organize doctor activities in an efficient way.

# Purpose of the Project

The main purpose of this project is to:

 =>Organize hospital data in a structured way

 =>Easily retrieve information using SQL queries

 =>Keep track of patient medical history

 =>Help doctors manage treatments and prescriptions

 =>Provide a simple model of how real hospital databases work


# Key Features

 =>Add and store patient and doctor details

 =>Schedule and manage appointments

 =>Record treatments for each patient

 =>Issue and track prescriptions

 =>Generate reports using SQL queries (basic, join, medium, advanced)



# Why This Project Is Useful

 =>This database project demonstrates how hospitals store and manage huge amounts of medical data. It shows relationships between important entities and teaches how SQL can be used to manage real-life systems.


# Disadvantage

 =>Manual Data Entry : All data must be entered manually, which can lead to errors or inconsistencies. 

 =>Not Web-Based or User-Friendly : The system relies purely on SQL queries; it doesn’t have a GUI for easy access by staff.

 =>Scalability Issues : With large data (hundreds of patients, doctors, and prescriptions), query performance might slow down.

 =>Limited Security : Sensitive patient information may not be fully protected unless advanced security measures are added.



# Working Flow

 =>Patient Registration : A new patient provides personal information (name, gender, DOB, contact, address).

   Data is stored in the Patient table.

 =>Doctor Registration : Doctor details such as name, specialization, and phone number are added.

   Stored in the Doctor table.

 =>Appointment Scheduling : Patients book appointments with a doctor.

   Appointment details (date, time, status) are stored in the Appointment table.

 =>Treatment Recording : During the appointment, the doctor diagnoses the patient and provides treatment.

   Treatment details (diagnosis, treatment details, treatment date) are stored in the Treatment table.

 =>Prescription Issuing : If medicines are required, the doctor prescribes them.

   Prescription details (medication, dosage, duration) are stored in the Prescription table and linked to the treatment.

 =>Data Retrieval and Reports : The system can generate reports like Patient medical history, Doctor activity, Prescription details, Appointments and treatments

   SQL queries fetch this data from the database.

 =>Updates and Maintenance : Patient details, appointment status, treatments, and prescriptions can be updated as needed.

   Old or irrelevant records can be deleted if necessary.

# STEP 1: Create and Use Database

 create database Hospital;
 use Hospital;

 # STEP 2: Create Patient Table

 create table Patient (patient_id INT PRIMARY KEY, name VARCHAR(100),gender VARCHAR(10),dob DATE, phone VARCHAR(20),address VARCHAR(255));

 # Insert Data into Table

  INSERT INTO Patient VALUES(1,'Virat', 'Male', '1988-11-05', '9988770018', 'Delhi'),(2,'Rohit', 'Male', '1987-04-30', '9998880045', 'Mumbai'),(3,'Seema','Female','1995-11-17','8809734512','Agra'),(4,'Aditiya','Male','1993-09-12','7839004215','Jaipur'),(5,'Smriti','Female','1995-12-27','7008231972','Dispur'),(6,'Kiran','Female','1990-02-01','7008657483','Chennai');

  # STEP 3: Create Doctor Table

create table Doctor (doctor_id INT PRIMARY KEY, name VARCHAR(100),specialization VARCHAR(100),phone VARCHAR(20));

# Insert Data into Table

INSERT INTO Doctor VALUES(1,'Dr Mayur', 'Cardiologist', '5550101'),(2,'Dr Rishabh', 'Neurologist', '5550102'),(3,'Dr Maya', 'General Physician','5550103');

# STEP 4: Create Appointment Table

create table Appointment (appointment_id INT PRIMARY KEY,patient_id INT,doctor_id INT,appointment_date DATETIME,status VARCHAR(50),FOREIGN KEY (patient_id) REFERENCES Patient(patient_id), FOREIGN KEY (doctor_id) REFERENCES Doctor(doctor_id));

# Insert Data into Table

INSERT INTO Appointment VALUES(1,1,1,'2025-01-18 09:00:00','Scheduled'),(2,2,2,'2025-01-18 08:00:00','Completed'),(3,3,3,'2025-01-19','Scheduled'),(4,4,3,'2025-01-20','Scheduled'),(5,5,1,'2025-01-19','Completed'),(6,6,2,'2025-01-17','Completed');

# STEP 5: Create Treatment Table

create table Treatment (treatment_id INT PRIMARY KEY, patient_id INT, doctor_id INT, treatment_date DATE , diagnosis TEXT, treatment_details TEXT,FOREIGN KEY (patient_id) REFERENCES Patient(patient_id),FOREIGN KEY (doctor_id) REFERENCES Doctor(doctor_id));

# Insert Data into Table

INSERT INTO Treatment VALUES(1,1,1,'2025-01-18','High blood pressure', 'Prescribed lifestyle changes'),(2,2,2,'2025-01-18','Migraine','Recommended MRI and medication'),(3,3,3,'2025-01-19','Common cold','Get plenty of rest and drink more fuilds'),(4,4,3,'2025-01-20','Fever','Stay at home avoid going outside'),(5,5,1,'2025-01-19','Mild chest pain','Recommended ECG and medication'),(6,6,2,'2025-01-17','Fits(seziures)','Avoid stress as much as possible');

# STEP 6: Create Prescription Table

create table Prescription (prescription_id INT PRIMARY KEY,treatment_id INT,medication VARCHAR(100),dosage VARCHAR(50),duration VARCHAR(50),FOREIGN KEY (treatment_id) REFERENCES Treatment(treatment_id));

# Insert Data into Table

INSERT INTO Prescription VALUES(1,1,'Amlodipine','5mg','30 days'),(2,2,'Ibuprofen','200mg','7 days'),(3,3,'Montelukast','10mg','5 days'),(4,4,'Paracetomol','500mg','2 days'),(5,5,'Aspirin','325mg','15 days'),(6,6,'Carbamazepine','800mg','90 days');
