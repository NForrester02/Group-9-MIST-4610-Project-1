# Group-9-MIST-4610-Project-1



# Team Members
Rohan Gehani [@RohanGeh]()

TJ Anderson: [@sta64960]()

Nick Forrester: [@NForrester02]()

Zackary Williams : [@zackwilliams10]()

Karan Sampath: [@ksampath0]()

# Prompt A

Pretend you are the owner/operator of an emergency healthcare clinic needing to build a relational database. You hired some students from the MIST 4610 class at the University of Georgia to create the database for you. They need to know more about your organization to identify which entities, attributes, and relationships are important for you. Start by describing your business as a real client

# Problem Description:

Part of the challenge given to us is to model and create a database that manages a healthcare clinic. The heart of the database is the Patient entity. We started with this entity as it is the core of the clinic. The people represented are the ones who seek medical attention and the services provided by the clinic. The patient’s entity correlates with many other entities such as Appointments, Medical Records, Billing, and Insurance Companies, Emergency Contacts, Referrals, and Appointments. All of these entities ensure the health clinic has all the appropriate information about the patient properly stored. We also have entities that help the clinic operate such as Staff, Shift Schedules, Emergency Cases, Medical Tests, and Medical Procedures. The other tasks include accurately modeling these entities into a database. We also have to create sample data to populate the databases. Lastly, we have to create practical and useful queries on this data to extract meaningful insight.

# Explanation of data model:

We created a model based on a hypothetical emergency clinic. The heart of our model centered around the patient entity which stores information about each patient that came to visit the clinic. Inside this entity, there is a foreign key that correlates to the primary key of emergency contacts, expressing a one-to-one relationship between the two, showing that each patient has one emergency contact. 
	
There is a visit record made for each time a patient makes a visit to the clinic, with its attributes expressing the arrival, departure, treatment, prescription, and other relating to that patient's stay at the clinic during that visit. There is a one-to-many relationship between these entities to express that each visit record is associated with just one patient, while a patient may have multiple visit records attached to them for each different time they visit the clinic. 

Branching from the Visit Records table, there is an Emergency Arrival table that indicates instances in which patients arrived for emergency reasons, and quickly had to be set up with appointments with the clinic staff. This entity has attributes that express that emergency type and triage of the emergency visit. There is a one-to-one relationship between this Emergency Arrival table and Visit Records table to show that an emergency arrival is linked to one instance of a patient visiting the clinic, if they arrived for emergency reasons. 

Branching from the patients table, there exists a one-to-many relationship with an Insurance Company table, to illustrate that each patient has an insurance company and an insurance company covers many patients. 

When patients come in and are seen by a staff member, it is logged inside a table called Appointments. A patient may have many appointments with the clinic and different staff members may take care of these appointments. Because of this, there is a one-to-many relationship between Patients and Appointments, as well as a one-to-many relationship between Appointments and Staff, an entity capturing each staff member working at the clinic.

When a patient is seen by a staff member, captured in Appointments, there may be multiple tests that the patient undergoes. The tests that the clinic can offer to Patients is captured through the Medical Tests Entity, which describes each medical test and the cost associated with it. Between the Appointments and Medical Tests Entities there exists a many-to-many relationship captured through the associative entity Administered Test. This highlights each instance of a test being administered during the appointment. This Entity captures data such as which test was performed, the date and time it occurred on, and the results of the test.

Similarly, there may be one or many procedures that a patient may undergo during an appointment. The types of procedures that the clinic can perform is captured in the Medical Procedures table, indicating the name, a description, and the cost associated with each medical procedure. This entity is connected to the Appointments entity in a many-to-many relationship through the associative entity Administered Procedure. This relationship expresses each instance of a procedure being performed during an appointment, with the length, time, and result all being traits expressed through the entity's attributes.

The model also captures when a staff member is scheduled to work a shift. There exists a Shift Schedule entity that holds each instance of the day and time that the medical staff may be scheduled for. This entity and the Staff entity are connected between a many-to-many relationship through the associative entity Staff_has_Shift. This entity captures each specific instance of a staff member clocking in and working the shift, as well as when they clocked out.                     
                        


# Data Model


<img width="498" alt="Screenshot 2024-03-27 at 5 14 44 PM" src="https://github.com/RohanGeh/Group-9-MIST-4610-Project-1/assets/150191828/27248576-7cce-4b49-96f0-74f5721c76b1">



# Data Dictionary


<img width="500" alt="Screenshot 2024-03-27 at 4 51 50 PM" src="https://github.com/RohanGeh/Group-9-MIST-4610-Project-1/assets/150191828/6fdde76c-7664-497e-9087-b8e53bb85e8e">

<img width="491" alt="Screenshot 2024-03-27 at 4 53 29 PM" src="https://github.com/RohanGeh/Group-9-MIST-4610-Project-1/assets/150191828/496bfa10-3e51-474f-9858-8a36c3a70f3c">

<img width="504" alt="Screenshot 2024-03-27 at 4 54 17 PM" src="https://github.com/RohanGeh/Group-9-MIST-4610-Project-1/assets/150191828/e97006fd-ef4e-44c1-8339-4d3f6d6522bc">

<img width="498" alt="Screenshot 2024-03-27 at 4 55 10 PM" src="https://github.com/RohanGeh/Group-9-MIST-4610-Project-1/assets/150191828/f79911d6-47d4-42fc-b511-f838d3756e47">

<img width="512" alt="Screenshot 2024-03-27 at 4 55 32 PM" src="https://github.com/RohanGeh/Group-9-MIST-4610-Project-1/assets/150191828/e449262b-c1fc-4f8e-bde6-43bcf6237d3f">

# Queries

1. Write a query to list the patient's last name, first name, and appointment date. Order the results by last name in the descending alphabetical order.
##Query 1 allows staff to see all the appointments that have been made by last name in order to check on specific customer appointment dates if changes need to be made or just have an overall view of all appointments. 

<img width="491" alt="Screenshot 2024-03-27 at 5 03 45 PM" src="https://github.com/RohanGeh/Group-9-MIST-4610-Project-1/assets/150191828/61bd4c2f-d55b-4503-b457-a6fbdf6546bf">


2. Write a query to list patient last name, firstname, and phone number for patients that have phone numbers with area code in Athens, GA.
##Query 2 allows staff to see which customers are from Athens, GA. This allows them to contact them via phone number for additional promotional offers for Athens residents.
 
<img width="408" alt="Screenshot 2024-03-27 at 5 03 56 PM" src="https://github.com/RohanGeh/Group-9-MIST-4610-Project-1/assets/150191828/30ac49a2-177b-443f-a355-18e861d81cf7">


3. Write a query to list out the patient's last name, firstname, phone number, billing amount and payment status for patients who haven't paid their bill. 
##Query 3 allows staff to quickly identify who hasn't paid their bills and give their contact information. If bills aren't being paid the business loses money so it's important to keep track of these things.  
 
<img width="376" alt="Screenshot 2024-03-27 at 5 04 12 PM" src="https://github.com/RohanGeh/Group-9-MIST-4610-Project-1/assets/150191828/3be370c7-3cae-4c76-b338-7a0b35583a2d">


4. List Patients and a count of their visits, whose total visits is greater than 3.
This allows the hospital manager to find their repeat patients.
<img width="481" alt="Screenshot 2024-03-27 at 5 04 35 PM" src="https://github.com/RohanGeh/Group-9-MIST-4610-Project-1/assets/150191828/fb1ecf1e-445c-4ad1-ad15-1048412b48d1">


5. Write a query to list the patient last name, first name, the number of payments they have made and total amount of payments they have made expressed as a percentage. Do this for only patients with Geico insurance and express the total amount percentage based on the pool of Geico based patients.
##Query 5 allows an analyst to understand the payment behaviors of Geico insurance users. This is important in making insurance partnerships in the future and analyzing the percentage of payments paid that are owed based on what insurance you use. This can correlate to if insurance premiums of certain insurance companies are too high or not based on the percentage of payments that are due, that customers can make.

<img width="501" alt="Screenshot 2024-03-27 at 5 04 49 PM" src="https://github.com/RohanGeh/Group-9-MIST-4610-Project-1/assets/150191828/05510583-afd0-46da-9159-e9ae1e5ce9bd">


6. Find Patients who were born in 2022 or 2023 and have an emergency contact whose relationship is not mother or father.
This query would allow the hospital managers to identify patients at risk of misunderstood information and in need of Child Services

<img width="384" alt="Screenshot 2024-03-27 at 5 05 04 PM" src="https://github.com/RohanGeh/Group-9-MIST-4610-Project-1/assets/150191828/c9db6375-36ba-49f3-8fa3-c6f86256b139">


7. Show the names of each staff member and the number of appointments they have if their total number of appointments is less than 5. 
This query would allow the hospital manager to get a glimpse of which staff members have been underutilized and are available for a larger workload.
<img width="385" alt="Screenshot 2024-03-27 at 5 05 22 PM" src="https://github.com/RohanGeh/Group-9-MIST-4610-Project-1/assets/150191828/cea6494d-7c17-4dcb-9b29-5b836c0159c3">



8. List appointments that were not seen by doctors 8-15
These doctors were flagged for unsanitary practices and thus we want to separate the flagged appointments from those that do not carry legal risk.
<img width="397" alt="Screenshot 2024-03-27 at 5 05 40 PM" src="https://github.com/RohanGeh/Group-9-MIST-4610-Project-1/assets/150191828/d46ab0b2-2ad5-4321-9103-f2507e1d66ef">



9. Find patients who have paid a balance greater than 1.5x the average total amount, and have not paid in full.
This allows a hospital manager to see which patients are likely to have recurring, long-term financial payments, as the expensive treatments are often for chronic and severe conditions. Also, it shows the hospital which patients are at risk for major financial issues due to financial default.
<img width="470" alt="Screenshot 2024-03-27 at 5 06 18 PM" src="https://github.com/RohanGeh/Group-9-MIST-4610-Project-1/assets/150191828/ff551b62-f63e-4a54-aab6-81e919fd1ea0">



10. Lists Dermatology Staff Availability in October.
This is useful for Receptionists when scheduling appointments in a given department, as Staff are not always available

<img width="471" alt="Screenshot 2024-03-27 at 5 06 29 PM" src="https://github.com/RohanGeh/Group-9-MIST-4610-Project-1/assets/150191828/be817561-6acb-4e08-81b1-497891d18904">


<img width="534" alt="Screenshot 2024-03-27 at 5 28 24 PM" src="https://github.com/RohanGeh/Group-9-MIST-4610-Project-1/assets/150191828/32cbb2a3-1fe5-4bff-a717-94e9fdc42dc0">


