## Task4: Setting Payara Secure Administration & Realm Users

### Step 1: Start Payara / GlassFish

<img width="1267" height="264" alt="01 start_server" src="https://github.com/user-attachments/assets/c1d12292-654a-4865-81b8-1436c005493e" />

### Step 2: Open Admin Console

* Open browser and go to: `http://localhost:4848`
* This opens the Administration Console

<img width="1366" height="768" alt="02 admin_console_page" src="https://github.com/user-attachments/assets/756d97da-adac-4cdf-9947-712e06dd8f97" />

### Step 3: Navigate to Security Realms

* In the left menu: expand this

      Configurations
       └── server-config
           └── Security
               └── Realms
                   └── admin-realm

  <img width="237" height="458" alt="03 navigate_to_admin_realm" src="https://github.com/user-attachments/assets/b22bc92b-14e8-4976-81ec-dc75263181ac" />

### Step 4: Set Admin Password

* Click admin-realm
* Click Manage Users

<img width="1366" height="768" alt="04 click_on_manage_users" src="https://github.com/user-attachments/assets/5259c72f-d443-456a-a4c1-4a055f28c881" />

* Click New

* Enter:
  * User ID: admin
  * Password: (choose a password)
  * Confirm Password

* Click OK

<img width="1366" height="768" alt="06 enter_data_click_ok" src="https://github.com/user-attachments/assets/cbfb4585-d3c3-49b5-a8ee-dcda4901a5f8" />

* This user is:
  * The administrator
  * Used to log into the admin console

### Step 5: Restart GlassFish

* Scroll to the top
* Click Server (left side)
* Click Restart

<img width="1366" height="768" alt="07 click_server_and_restart" src="https://github.com/user-attachments/assets/34ff170f-222c-4d29-ac61-f974c13d9284" />

### Step 6: Login Again

* After restart: Browser will ask for credentials
* Enter Username: admin & your Password

<img width="1005" height="642" alt="08 enter_username_pass" src="https://github.com/user-attachments/assets/a66e28ef-df4d-45df-8932-b1f2644d5a87" />


---

## TASK 5: Adding Users to the File Realm

### What is the File Realm?

* A realm stores users & passwords
* file realm is the default user database
* Groups control authorization


### Step 1: Go to File Realm

    Configurations
     └── server-config
         └── Security
             └── Realms
                 └── file

<img width="242" height="567" alt="09 file_realm" src="https://github.com/user-attachments/assets/52f8e467-dc1d-4d73-a79f-a821c1232881" />



Step 2: Add Admin User (adm)

* Click file
* Click Manage Users

<img width="1366" height="723" alt="10 click_on_manage_users_again" src="https://github.com/user-attachments/assets/71a08776-2439-428c-820c-7207b3260e7e" />

* Click New

<img width="1366" height="721" alt="11 click_on_new" src="https://github.com/user-attachments/assets/67e60683-045b-4f88-92d2-4478af806dfa" />

* Fill in:

  * User ID: adm
  * Group List: AdminUser
  * Password: (choose one)
  * Confirm Password

* Click Save

<img width="1366" height="683" alt="12 enter_data_click_ok_again" src="https://github.com/user-attachments/assets/bd505b5c-2d2e-490e-a0f8-582c912c5510" />

* This user:

  * Belongs to admin group  
  * Can access admin pages

Step 3: Add Application User (appuser)

* Repeat New User:

* Fill in:

  * User ID: user1
  * Group List: appuser
  * Password: (choose one)
  * Confirm Password

* Click OK

<img width="1366" height="768" alt="13 add_new_user" src="https://github.com/user-attachments/assets/7848b9e4-ed16-414c-b747-37d545971f73" />

* This user:
* Can access non-admin pages
* Used for application login

### Step 4: Verify Groups

* You should now have users like:

<img width="1117" height="145" alt="14 users_list" src="https://github.com/user-attachments/assets/d9f122d2-d02e-4af2-b625-37608ef2bdb2" />


---

## TASK 6: BASIC Authentication (web.xml + glassfish-web.xml)

### What is BASIC Authentication?

* Browser shows a popup login dialog
* Username + password
* Controlled via XML
* No Java code changes

### Step 1: Download `filerealmbasicauth.zip`

<img width="1366" height="768" alt="15 unzip_project" src="https://github.com/user-attachments/assets/445f384b-bbf6-492e-b5f9-5080b99e1ebe" />


### Step 2: Create the WAR File

<img width="808" height="134" alt="16 create_war_file" src="https://github.com/user-attachments/assets/8c035659-be89-49de-b765-3fda9f0ae5ce" />


### Step 3: Deploy the Application to GlassFish

<img width="1366" height="680" alt="17 click_deploy" src="https://github.com/user-attachments/assets/25bc9228-48b2-4a13-a7ec-974de9568bfd" />

* Browse -> Choose target/war file

<img width="1366" height="682" alt="18 browse_ok" src="https://github.com/user-attachments/assets/d8ab511c-06bf-4833-94da-5a035b2b77d7" />


### Step 4: Run the Application

* Open browser and go to: `http://localhost:8080/filerealmbasicauth`


<img width="1366" height="768" alt="19 popup" src="https://github.com/user-attachments/assets/d5a9456e-e032-497a-8955-e8413d4a5df1" />

* We will sign in with `user1` : `appuser`

<img width="1366" height="201" alt="20 filerealmbasicauth_page" src="https://github.com/user-attachments/assets/1393cf24-ecb7-4562-b656-165d7d2cdccf" />

* But if we want to access some admin page the respone will be `HTTP Status 403 - Forbidden`

<img width="1366" height="537" alt="21 forbidden" src="https://github.com/user-attachments/assets/c3703bf2-a07c-4f61-a152-d96cd436696f" />


* But if we sign in with `adm` : `AdminUser` it will open

<img width="1366" height="768" alt="22 popup_again" src="https://github.com/user-attachments/assets/379e2425-cb46-4d8b-9d73-3fec7c0f2a01" />

<img width="1366" height="197" alt="23 admin_page" src="https://github.com/user-attachments/assets/c5b1dffb-abe0-422d-a681-828377af3d86" />

