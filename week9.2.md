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





