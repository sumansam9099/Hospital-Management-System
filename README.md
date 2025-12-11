# Hospital-Management-System
This project is a Hospital Management System designed to store and manage information about patients, doctors, appointments, treatments, and prescriptions. The database helps the hospital maintain accurate medical records, track patient visits, and organize doctor activities in an efficient way.

Purpose of the Project

The main purpose of this project is to:

 =>Organize hospital data in a structured way

 =>Easily retrieve information using SQL queries

 =>Keep track of patient medical history

 =>Help doctors manage treatments and prescriptions

 =>Provide a simple model of how real hospital databases work


Key Features

 =>Add and store patient and doctor details

 =>Schedule and manage appointments

 =>Record treatments for each patient

 =>Issue and track prescriptions

 =>Generate reports using SQL queries (basic, join, medium, advanced)



Why This Project Is Useful

 =>This database project demonstrates how hospitals store and manage huge amounts of medical data. It shows relationships between important entities and teaches how SQL can be used to manage real-life systems.


Disadvantage

 =>Manual Data Entry : All data must be entered manually, which can lead to errors or inconsistencies. 

 =>Not Web-Based or User-Friendly : The system relies purely on SQL queries; it doesn’t have a GUI for easy access by staff.

 =>Scalability Issues : With large data (hundreds of patients, doctors, and prescriptions), query performance might slow down.

 =>Limited Security : Sensitive patient information may not be fully protected unless advanced security measures are added.



Working Flow

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


