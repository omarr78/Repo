## Task3:

* In this task we will build a classic MVC web application.

* MVC means:

| Layer          | Technology | Responsibility                                    |
| -------------- | ---------- | ------------------------------------------------- |
| **Model**      | Java Bean  | Holds data (email, password)                      |
| **View**       | JSP        | Displays HTML to user                             |
| **Controller** | Servlet    | Handles request, talks to model, forwards to view |

* Flow:

* user.jsp (form) → UserServlet (controller) → UserBean (model) → valid_user.jsp (view)

### 1. Project Structure

<img width="694" height="359" alt="Screenshot from 2026-01-04 20-09-26" src="https://github.com/user-attachments/assets/beebddd8-7614-4e04-acf1-b77c0181f4c7" />

* Java files go in WEB-INF/classes
* JSP files go outside WEB-INF

### 2. Create JSPs

* Create directory `mkdir mvc`
* Create users.jsp with `nano users.jsp` 

<img width="1352" height="713" alt="02 create_user_jsp" src="https://github.com/user-attachments/assets/7d38e09b-893d-4edf-a173-8a7b075b4a33" />

* Create vaild_user.jsp with `nano vaild_user.jsp`

<img width="1352" height="713" alt="03_create_valid_user_jsp" src="https://github.com/user-attachments/assets/c4215142-973b-4f79-a372-b128d0d55d11" />


### 3. Create the model (UserBean)

* Create directory `mkdir mvc`
* Create UserBean.java with `nano UserBean.java`

<img width="1352" height="713" alt="04 create_user_bean" src="https://github.com/user-attachments/assets/281941c9-cc66-496a-b421-d045a25e1c76" />

### 4. Create the controller

* Create UserServlet.java with `nano UserServlet.java`

<img width="1844" height="997" alt="5 create_user_servlet" src="https://github.com/user-attachments/assets/9f39fa42-ecbb-453d-b6bb-fb2b42358912" />

### 5. Compile java classes

<img width="1211" height="49" alt="06 compile_java_classes" src="https://github.com/user-attachments/assets/6695cfca-4ee7-4860-8555-d10962423bf4" />

### 6. Restart Tomcat

<img width="1358" height="376" alt="07 restart_tomcat" src="https://github.com/user-attachments/assets/4f3f1838-b200-44bb-80e4-7c6a77ed6de2" />

### 5. Run the Application

* Open your browser and go to `http://localhost:8080/ci502/mvc/users.jsp`
* Enter your email and password

<img width="1366" height="768" alt="10 enter_data" src="https://github.com/user-attachments/assets/b93efada-90ba-4e82-b789-2145b2fcbabd" />


* Click submit

* Final Output

      User Validated!

      Welcome, admin@test.com

<img width="1366" height="612" alt="11 result" src="https://github.com/user-attachments/assets/a95d0b43-5aa8-46d3-ab7e-8a790ffc7f52" />





