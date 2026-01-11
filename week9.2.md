## TASK 5:

### Step 1: Copy MySQL JDBC Driver to GlassFish

* Locate your downloaded .jar file `mysql-connector-j-9.5.0.jar`
* Copy it to these directories inside your GlassFish installation:
  * GlassFish_INSTALL_DIR/glassfish7/glassfish/domains/domain1/lib
  * GlassFish_INSTALL_DIR/glassfish7/glassfish/domains/domain1/lib/ext
 
<img width="1339" height="69" alt="01 copy_driver" src="https://github.com/user-attachments/assets/6d11f048-4254-40d3-8c3b-16a7e2ede994" />

### Step 2: Start GlassFish

<img width="1366" height="768" alt="02 start_server" src="https://github.com/user-attachments/assets/8c8de053-2761-44d4-a3bb-217089628772" />

### Step 3: Add Library (Optional Fix for Driver Class Name Error)

* Sometimes GlassFish doesn’t detect the driver automatically.
* If you see an error like “wrong class name for driver”, do this:

<img width="1330" height="47" alt="03 add_library" src="https://github.com/user-attachments/assets/bda0d67e-2979-47db-8a1a-02b871b4fbe7" />

### Step 4: Open GlassFish Admin Console

* Open your browser & Go to: `http://localhost:4848`

### Step 5: Create JDBC Connection Pool

* In the left menu, expand Resources → JDBC → JDBC Connection Pools
* Click New

<img width="2212" height="1248" alt="04 create_connection_pool" src="https://github.com/user-attachments/assets/8c087d42-94de-46f1-8c65-3489dd36d4d9" />

* Fill in the form:
  * Name: `MySqlDS`
  * Resource Type: `javax.sql.DataSource`
  * Database Vendor: `MySql`

<img width="1436" height="662" alt="05 fill_form" src="https://github.com/user-attachments/assets/a1956ed6-67e7-4f64-beed-e769f6c862c9" />


### Step 6: Set Datasource Class Name

* In the Datasource Classname field, enter: `com.mysql.cj.jdbc.MysqlDataSource`

<img width="1874" height="748" alt="06 set_datasource_classname" src="https://github.com/user-attachments/assets/a43e31ae-ce44-4fea-936b-87d781f03ed5" />

* Click Finish

### Step 7: Configure Additional Properties

* Go to the Additional Properties tab.

* If there are existing properties, click Select All → Delete.

* Add new properties (this is the typical set for MySQL):

<img width="1117" height="530" alt="07 set_propertise" src="https://github.com/user-attachments/assets/929aadc8-4857-4f8c-9597-85768870b7be" />

* Click Save

### Step 8: Test the Connection Pool


* In JDBC Connection Pools, click your pool name MySqlDS.

* Click Ping (top right corner).

* If everything is correct, you should see: `Ping Succeeded`

<img width="1120" height="527" alt="08 succed_ping" src="https://github.com/user-attachments/assets/6d0d3d1b-3a2c-479d-8539-cd5ce9e7d4ff" />


---

## TASK 6:

### Step 1: Open GlassFish Admin Console

* Open your browser Go to: `http://localhost:4848`

### Step 2: Navigate to JDBC Resources

* In the left menu, expand: Resources → JDBC → JDBC Resources

* You will see a list of existing JDBC resources.

<img width="1366" height="648" alt="09 jdbc_resource" src="https://github.com/user-attachments/assets/5beb1eea-6432-453c-a335-60c32dd1d154" />


### Step 3: Edit the Resource

* Look for the resource: jdbc/__default

<img width="1366" height="648" alt="10 select_jdbc_default" src="https://github.com/user-attachments/assets/b1030c33-94b6-437f-b701-47c0005316da" />


* Click the name jdbc/__default to open its settings.

* Look for the field Pool Name.

Change it from the old pool to: `MySqlDS`

<img width="1113" height="412" alt="11 edit_jdbc_resource" src="https://github.com/user-attachments/assets/d9c479f7-d112-4de5-8f07-9ac119ce6a3f" />


* This is the connection pool you created in Task 5

* Click Save

* After saving, your resource is now linked to the MySQL connection pool.

* Your web application can now safely use jdbc/__default to get a connection.

---

## TASK 7: A JPA Servlet application

### Step 1: Download and Unzip the Project & check that the directory structure is correct 

<img width="1366" height="768" alt="12 unzip_servletjpa" src="https://github.com/user-attachments/assets/4f95b264-d9e6-4e10-8021-2c8d739e9980" />

<img width="796" height="267" alt="13 validate" src="https://github.com/user-attachments/assets/de8b2a4f-a1e8-4765-b1a9-b46e42e5719f" />

### Step 2: Modify pom.xml

### Step 3: Compile the Project

<img width="475" height="23" alt="14 compile" src="https://github.com/user-attachments/assets/686fd52a-03dc-4c21-ba2c-a9f2c9b34986" />

### Step 4: Package the Project into a WAR

<img width="463" height="23" alt="15 package" src="https://github.com/user-attachments/assets/f34654e3-b37e-403e-ae7c-eed84cc01543" />

### Step 5: Deploy to Payara / GlassFish

<img width="1366" height="680" alt="16 click_deploy" src="https://github.com/user-attachments/assets/00b07426-98b9-4b62-899d-9cb5f19a2555" />

<img width="1366" height="682" alt="17 browse_ok" src="https://github.com/user-attachments/assets/16d68ad6-aa15-4e32-8db5-5a18408a90f4" />

### Step 6: Start the Application

* Open your browser Go to the servlet URL: `http://localhost:8080/servlet_jpa/jpaservlet`
* If everything is correct, you should see a message saying the database was updated

<img width="1366" height="283" alt="18 updated_database" src="https://github.com/user-attachments/assets/de539880-482e-4072-923c-6bba4c0ee70d" />

Step 7: Verify in MySQL

* Open MySQL

* Check that the table is created and records are inserted:

<img width="1122" height="652" alt="19 verify_inserted_row" src="https://github.com/user-attachments/assets/4a4b9764-adc8-4ec0-830c-4b7f2a9f4cc8" />

