# JPA EXERCISES
## PART I — JPA STANDALONE APPLICATION

### Task1: MySQL Database Setup

### Step 1: Create database and user (Brighton MySQL)

* Database name will be `atma14_testdb`

<img width="1125" height="190" alt="01 create_database" src="https://github.com/user-attachments/assets/bfaa2b13-ed75-4e56-a68d-8db8b6c3a18a" />


* User will be `atma14_user1`

<img width="1097" height="150" alt="02 create_user" src="https://github.com/user-attachments/assets/63afe866-b7f5-47e9-ae37-f6a7b7a1bba4" />

* Add User To Database and give him ALL PRIVILEGES

<img width="575" height="229" alt="5 add_user_to_database" src="https://github.com/user-attachments/assets/ef200188-4637-4de8-b7ea-be909df98f4a" />

---

### Step 2: Enable Remote Access

* Add Access Host

<img width="555" height="281" alt="03 add_access_host" src="https://github.com/user-attachments/assets/7456e3e7-0d9e-42a1-a495-f7e26499f28f" />

* And this is the added access host

<img width="1085" height="257" alt="04 result_access_host" src="https://github.com/user-attachments/assets/0a72c65b-f585-4f97-b14d-cf0d39da628f" />

* This allows Java programs (outside MySQL) to connect


### Step 3: Import import.sql

* Download import.sql from My Studies

* In MySQL web interface:

  * Select your database
  * Choose Import
  * Upload import.sql
  * Click Import

<img width="1366" height="649" alt="6 import_sql" src="https://github.com/user-attachments/assets/d3d8a7ab-375a-4d14-afbc-0dba3c9d93fb" />

* This creates tables and inserts sample data

---

### Task2: MySQL JDBC DRIVER

### Step 1: Download JDBC Driver

* Java needs a driver to talk to MySQL

* Download `mysql-connector-java-8.0.28.jar`

---

### Step 2: Set CLASSPATH

* Go to your home directory: `cd`

* Open `.bash_profile` with `nano .bash_profile`: 

<img width="267" height="30" alt="07 bash_profile" src="https://github.com/user-attachments/assets/cc3c567d-e661-4fbf-b426-44b53f6bfd39" />

* Add classpath

<img width="791" height="45" alt="08 add_classpath" src="https://github.com/user-attachments/assets/eede1aa4-ee84-40bc-a7ab-262d7a0ac4a1" />

* Save and exit

* Apply changes & Check

<img width="1354" height="91" alt="09 apply_check" src="https://github.com/user-attachments/assets/ca9a7e54-4923-40c0-8545-4e5e47438823" />

---

### TASK 3 — Simple Java MySQL Connection (JDBC)

* Download `MySqlConnect.java`
* Update java file to set your database values with `nano MySqlConnect.java`

<img width="932" height="184" alt="10 update_values" src="https://github.com/user-attachments/assets/294dfd7c-654a-4310-a650-eb99c48a06cd" />

* Compile `MySqlConnect.java`

<img width="489" height="22" alt="11 compile" src="https://github.com/user-attachments/assets/3fc20453-a263-4cb4-9025-b20d3a081933" />

* Run

<img width="1366" height="768" alt="12 run" src="https://github.com/user-attachments/assets/0412f12e-2b6f-4b81-927c-b1e7603df8bc" />

* You see that rows printed 

---

### TASK 4 — FIRST JPA APPLICATION (MAVEN)

### Step 1: Create Project Structure

<img width="695" height="45" alt="13 create_project_structure" src="https://github.com/user-attachments/assets/6012d4c3-5a8e-4740-a04a-35039cba44aa" />

* Required Files

* You must have:

<img width="378" height="335" alt="14 project_structure" src="https://github.com/user-attachments/assets/4e6ab219-8ad6-4a4d-b4b1-d7f2a0a6bb27" />


* From My Studies,  download Book.java and Main.java and save them in the ci502 directory
* Also, save the file persistence.xml in META-INF directory and pom.xml in the firstJPA directory
* Open these files and try to understand the code

<img width="887" height="619" alt="19 java_code" src="https://github.com/user-attachments/assets/ef47b287-25eb-4667-a70f-ca51e5225569" />

* open persistence.xml and modify it to represent your own details

<img width="1366" height="768" alt="15 modify_presistance" src="https://github.com/user-attachments/assets/5f977d20-92ce-4428-8f2d-1bf4620a38d7" />

* Compile and Package

<img width="448" height="27" alt="16 compile" src="https://github.com/user-attachments/assets/0e87850c-a153-41fb-a3e3-c14b275527fa" />

<img width="448" height="26" alt="17 package" src="https://github.com/user-attachments/assets/c50ce8f3-2f85-4ea3-b7e6-b1f7c0427148" />


* Run JPA Application

<img width="821" height="26" alt="18 run" src="https://github.com/user-attachments/assets/953933f5-f0bc-41ba-bf0a-dfed46bbed09" />

* Book should be inserted into database

* Verify in MySQL with `SELECT * FROM book;`

<img width="1124" height="648" alt="20 see_inserted_book" src="https://github.com/user-attachments/assets/6e116cf8-cb0e-4367-b79b-9f1550708e0c" />
