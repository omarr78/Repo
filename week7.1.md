# JSF & GlassFish 7

## Task1:

### 1. Download GlassFish 7 & Start the server

* You will see file name looks like `glassfish-7.x.x.zip`
* Then unzip it

<img width="653" height="270" alt="01 unzip" src="https://github.com/user-attachments/assets/a3b88a02-88d8-465b-9123-72fbe31faf67" />

* Start GlassFish server by `./asadmin start-domain`

<img width="1093" height="312" alt="02 start_server" src="https://github.com/user-attachments/assets/2cbad726-a63e-4ae4-b7fd-85dfa1677852" />

* You should see `Command start-domain executed successfully.`

* Test GlassFish open `http://localhost:8080` and GlassFish welcome page should appears

<img width="1366" height="768" alt="03 glassfish_page" src="https://github.com/user-attachments/assets/7e8bd438-ffe6-4a61-94ed-6a4ea75b0540" />

---

### 2. Deploy hello.war

* Download `hello.war` from My Studies
* Copy it to GlassFish autodeploy directory

<img width="1322" height="50" alt="04 copy_war" src="https://github.com/user-attachments/assets/c1d852e7-98a8-4169-91d9-7a66a65de6be" />

* Test hello.war by opening `http://localhost:8080/hello`

<img width="1366" height="768" alt="05 test_hello_war" src="https://github.com/user-attachments/assets/2192ac24-80e8-480c-bf3e-a31448ad8db9" />

---

### 3. Your First JSF Application (helloworld)

* unzip helloworld.zip

<img width="630" height="377" alt="06 unzip_helloworld" src="https://github.com/user-attachments/assets/13110e45-92d6-4aa2-80f0-3f94e77470c1" />

* WEB-INF is REQUIRED for JSF apps


* Build the WAR file Go inside helloworld directory
* And run this command `jar -cvf helloworld.war *`

<img width="789" height="201" alt="07 build_war" src="https://github.com/user-attachments/assets/43c00392-0bed-4c54-aca6-5a035b933322" />

* Then WAR file created

* Deploy helloworld.war

<img width="1357" height="71" alt="08 deploy_helloworld_war" src="https://github.com/user-attachments/assets/3d43d0ba-a96b-4da5-82f0-69b8b5fec70c" />

* Run the JSF application by opening `http://localhost:8080/helloworld/home.jsf` 
* “Hello World” appears

<img width="1366" height="317" alt="09 test_helloworld" src="https://github.com/user-attachments/assets/14e07787-17ef-45d8-a5d4-897e5a67b676" />


