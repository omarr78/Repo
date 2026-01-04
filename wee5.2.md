## Task2:

* In this task we will build a 3-page jsp application:
* 1- `UserName.jsp` → shows a form
* 2- `SaveName.jsp` → receives form data and stores it in a Java Bean
* 3- `NextPage.jsp` → reads data from the bean and displays it
* We will also create one java class (bean): `userData.java`

### 1. Folder Structure

<img width="423" height="304" alt="image" src="https://github.com/user-attachments/assets/38966e92-a596-4e51-8345-8f249087fad7" />

### 2. Create JSPs

* Create UserName.jsp (The Form) with `nano UserName.jsp`

<img width="1352" height="719" alt="01 create_UserName" src="https://github.com/user-attachments/assets/51f232f9-235b-404d-90bd-0aa2d385de8d" />

* Create `SaveName.jsp` (Save Form Data) with `nano SaveName.jsp`

<img width="1354" height="719" alt="Screenshot from 2026-01-04 17-19-55" src="https://github.com/user-attachments/assets/a8c155e0-c731-4dde-bd2e-67f57dd80843" />

* What is happening here?

* `<jsp:useBean id="user" class="user.UserData" scope="session"/>`

* Creates a bean object if it doesn't exist
* Or retrieve it if it already exists
* Stores it in session scope

* `<jsp:setProperty name="user" property="*"/>`
* Reads from fields
* Matches:

      username → setUsername()
      email → setEmail()
      age → setAge()

* and Automatically stores values into the bean


* Create NextPage.jsp (Read Bean Data) with `nano NextPage.jsp`

<img width="1354" height="719" alt="06 create_nextPage_jsp" src="https://github.com/user-attachments/assets/6bccb76f-0c50-4db4-bb95-7e29bb53ac13" />

* why use this again `<jsp:useBean id="user" class="user.UserData" scope="session"/>`

* To retrieves the same bean from session

* Makes it available as variable user

### 3. Create java bean `userData.java` with `nano userData.java` 

<img width="1843" height="998" alt="03 user_data_java" src="https://github.com/user-attachments/assets/bddad6ef-c979-42d1-afee-390a7a503588" />

### 4. Compile the Bean

<img width="1191" height="71" alt="04 compile_java_bean" src="https://github.com/user-attachments/assets/bc09ca92-d8a7-4b8b-a2b2-d008bb1e1f9a" />

* Tomcat loads Java classes only from WEB-INF/classes

### 4. Restart Tomcat

<img width="1358" height="376" alt="07 restart_tomcat" src="https://github.com/user-attachments/assets/6045d8e2-2d18-4a1e-b1cb-1ca16bfe0c75" />

### 5. Run the Application

* Open your browser and go to `http://localhost:8080/ci502/jsp/UserName.jsp`
* Enter your name, e-mail, age
<img width="1366" height="768" alt="08 enter_user_data" src="https://github.com/user-attachments/assets/def9eff3-7582-4ba2-bcfc-bb368a62db2f" />

* Click submit

* Click Continue

<img width="1366" height="351" alt="09 data_saved" src="https://github.com/user-attachments/assets/99712898-78bb-4b66-8cc6-718d5a06dde5" />

* Final Output

      Name: Omar
      Email: Omar@test.com
      Age: 22


<img width="1366" height="434" alt="10 data_result" src="https://github.com/user-attachments/assets/700b601c-c630-42f5-afde-e4052f9f16d3" />


