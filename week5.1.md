## Task1:

### 1. Install Apache Tomcat & Run Tomcat & Create folders

* Run Tomcat

<img width="1359" height="221" alt="01 start_tomcat" src="https://github.com/user-attachments/assets/6651e826-b337-4f9d-9752-5966640682f7" />

* Create folders `ci502` `jsp`

<img width="1354" height="179" alt="02 create_folders" src="https://github.com/user-attachments/assets/5b686e19-f1c2-483f-b7a2-0a9b64c9e43a" />

### 2. Create `Order.jsp` with `nano Order.jsp`

<img width="1354" height="720" alt="03 create_order_jsp" src="https://github.com/user-attachments/assets/88ff92c8-bc66-4b53-8395-b1c223ee65ea" />

### 3. Access the JSP

* `http://localhost:8080/ci502/jsp/Order.jsp`
* You will see `Thanks for ordering null!`

<img width="1366" height="210" alt="04 open_order_jsp" src="https://github.com/user-attachments/assets/04b39ff6-ef00-460e-ae26-0660fb509787" />

* why it is null ?
* Request.getParameter("title") looks for a URL parameter
* No parameter was sent → result is null
* To make it show `Thanks for ordering a yacht.`
* You don't change JSP
* Instead, change the url `http://localhost:8080/ci502/jsp/Order.jsp?title=a+yacht`
* You will see `Thanks for ordering a yacht!`

<img width="1366" height="224" alt="05 change_the_output" src="https://github.com/user-attachments/assets/b6ac9ed1-4374-4650-9fd2-952c2779356f" />

* `?title=a+yacht` sends a request parameter
* JSP reads it using request.getParameter("title")


### 4. Processing a Form with JSP

* Create `form1_get.html` with `nano form1_get.html`

<img width="1354" height="720" alt="06 from1_get_html" src="https://github.com/user-attachments/assets/66a396cf-9a3d-4e43-9b13-9e70cb9464a8" />

* Create `doForm1.jsp` with `nano doForm1.jsp`

<img width="1354" height="720" alt="07 doForm1_jsp" src="https://github.com/user-attachments/assets/262f8123-d0e5-47b3-a9d6-a857e43e866d" />

* Test the form `http://localhost:8080/ci502/jsp/form1_get.html`

* Enter `Java Book` and click `submit`

<img width="1366" height="476" alt="08 order_form" src="https://github.com/user-attachments/assets/38d286fa-f8ce-454f-bff2-cc2371c3edd3" />


* The result should be `Thanks for ordering: Java Book`

<img width="1366" height="341" alt="09 order_confirmation" src="https://github.com/user-attachments/assets/05dfd61c-b78e-4d1e-a9c0-6ec70dc2cfef" />


### 5. Scriptlets (Java Code Inside JSP)

* Create Date.jsp with `nano Date.jsp`

 <img width="1354" height="720" alt="10 date_jsp" src="https://github.com/user-attachments/assets/90870ed7-3ffe-4e84-b68e-543e0ad57fb2" />

* Access Date.jsp open `http://localhost:8080/ci502/jsp/Date.jsp`

<img width="1366" height="263" alt="11 open_date_jsp" src="https://github.com/user-attachments/assets/e86280ae-83fa-4c55-b79c-a42af31a55f4" />

* Output Current date & time and IP address (not 127.0.0.1)
* Why not 127.0.0.1 ?
* `request.getRemoteAddr()` shows client IP
* Tomcat sees your browser as a network client

### 6. Mixing Scriptlets and HTML

* Goal: Generate an HTML table with numbers 1 to N
* Create `Table.jsp` with `nano Table.jsp`

<img width="1354" height="720" alt="12 table_jsp" src="https://github.com/user-attachments/assets/9aacc8d6-5573-4cb6-8090-ade5f5446c65" />

* Test Table.jsp by open `http://localhost:8080/ci502/jsp/Table.jsp`

<img width="1366" height="490" alt="13 open_table_jsp" src="https://github.com/user-attachments/assets/3c79843a-1954-4855-ae33-6cc9584e5dab" />







