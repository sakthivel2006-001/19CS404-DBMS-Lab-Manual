# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - Student Name

## Scenario Chosen:
Hospital

## ER Diagram:

![image](https://github.com/user-attachments/assets/57832114-fbe9-46d3-ae1c-e544b355a297)

## Entities and Attributes:
Patient:
1. PatientID (PK)
2. FullName
3. DateOfBirth
4. Gender
5. Address
6. PhoneNumber
7. Email
8.InsuranceDetails

Doctor:
1. DoctorID (PK)
2. FullName
3. Specialization
4. PhoneNumber
5. Email
6. WorkSchedule

Department:
1. DepartmentID (PK)
2. DepartmentName
3. DepartmentHead

Appointment:
1. AppointmentID (PK)
2. AppointmentDate
3. AppointmentTime
4. ReasonForVisit
5. AdditionalNotes
6. PatientID (FK)
7. DoctorID (FK)

MedicalRecord:
1. MedicalRecordID (PK)
2. Diagnosis
3. PrescribedMedications
4. Treatments

TestResults:
1. OtherMedicalInformation
2. PatientID (FK)
3. DoctorID (FK)

Billing:
1. BillingID (PK)
2. AppointmentID (FK)
3. TotalAmount
4. BillingDate

Payment:
1. PaymentID (PK)
2. BillingID (FK)
3. PaymentDate
4. PaymentAmount
5. PaymentMethod

...

## Relationships and Constraints:
1. Patient (1) --- schedules --- (M) Appointment
2. Doctor (1) --- conducts --- (M) Appointment
3. Patient (1) --- has --- (M) MedicalRecord
4. Doctor (1) --- creates --- (M) MedicalRecord
5. Department (1) --- employs --- (M) Doctor
6. Appointment (1) --- generates --- (1) Billing
7. Billing (1) --- receives --- (1) Payment
   
Cardinality and Participation Constraints:
A patient can have multiple appointments (1:M Relationship), but an appointment is linked to only one patient (M:1 Relationship). A doctor can have multiple appointments (1:M Relationship), but each appointment involves one doctor (M:1 Relationship). A department has multiple doctors (1:M Relationship). Each appointment leads to one billing record (1:1 Relationship). Each billing can receive exactly one payment (1:1 Relationship).

...

## Extension (Billing):
Billing entity records the amount charged for an appointment.
Payment entity records the payment made against a bill, including the method(cash, card, insurance, etc.).
Each billing must be associated with one appointment.
Each payment must correspond to one billing record.

...

## Design Choices:
Entities: Separate entities for Patient, Doctor, Appointment, MedicalRecord, Billing, and Payment ensure modularity and better data management. Attributes: Chosen based on the essential data needed for hospital operations. Relationships: Clearly define which entity relates to another and how, ensuring integrity and traceability. Billing and Payment: Introduced as separate entities to allow flexibility in
handling different payment methods and billing adjustments.

...

## RESULT
A Database to Hospital Management is created Successfully
