## Task3:

### 1. Know where files go

* Java Servlet files go here `WEB-INF/classes`
* HTML files go here `webapps/ci502`

### 2. Copy the files to correct locations

* Copy `ThreeParams.java` and put it `WEB-INF/classes/forms`
* Copy `three-params-form.html` and put it into `webapps/ci502`

<img width="1358" height="176" alt="01 copy_files" src="https://github.com/user-attachments/assets/359ce01d-b21f-42ed-bf74-da518eb916cb" />

### 3. Open and understand `ThreeParams.java` using `nano forms/ThreeParams.java`

### 4. Compile the servlet and Restart Tomcat

<img width="1358" height="463" alt="02 compile_restart" src="https://github.com/user-attachments/assets/f5d17489-645e-4971-815d-9ed1233ae1b4" />

### 5. Invoke servlet directly without form

* Open browser and go to `http://localhost:8080/ci502/threeParams`
* And Expected output

``` text
param1 = null
param2 = null
param3 = null
```

<img width="1366" height="280" alt="03 invoke_servlet" src="https://github.com/user-attachments/assets/3223ce78-3127-4ff2-beb6-711660d47a31" />

### Invoke servlet using the form

* now open `http://localhost:8080/ci502/three-params-form.html`
* Enter values in the three text boxes
* Click Submit
* The form sends data to the servlet

<img width="1366" height="275" alt="04 enter_values" src="https://github.com/user-attachments/assets/28b4b9bb-b1f0-4095-b4a0-1e8a0652d97c" />

* now Expected output

``` text
param1 = value1
param2 = value2
param3 = value3
```

<img width="1366" height="264" alt="05 params_sent" src="https://github.com/user-attachments/assets/9151b2b1-69f3-417f-9288-a0e0de791a20" />

### 6. Create a new form & servlet package

* create a new directory inside classes
* copy servlet to new directory

<img width="1312" height="157" alt="06 new_servlet_directory" src="https://github.com/user-attachments/assets/8845ad1c-c66f-4e0e-979c-a8700fe7814c" />

* Modify the servlet for the new package with `nano new_forms/ThreeParams.java`
* change the line `package forms;` with new package `package new_forms;`
* and change `@WebServlet("/threeParams")` with `@WebServlet("/threeParamsNew")`

<img width="1354" height="718" alt="07 modify_on_servlet" src="https://github.com/user-attachments/assets/8038ef48-492c-4339-93fe-3923b3c5ef4f" />


* Save and exit

* Compile the new servlet

<img width="1354" height="27" alt="08 compile_newServlet" src="https://github.com/user-attachments/assets/39b4390b-05a7-4985-8806-0b3fa6854b55" />

* Copy and modify the html form with `nano three-params-form-new.html`

<img width="1354" height="112" alt="09 copy_edit_html" src="https://github.com/user-attachments/assets/81c97a77-cb2e-4098-aa2c-8a4068378813" />

* Change the form action

<img width="1354" height="718" alt="10 modify_html" src="https://github.com/user-attachments/assets/c1e0752d-ff73-47ec-8012-793a105699fe" />


* Restart Tomcat

<img width="1358" height="376" alt="11 restart_tomcat" src="https://github.com/user-attachments/assets/6f7cf901-2829-40fe-95c2-ceae531b04c6" />

### 7. Test the NEW servlet & form

* Direct servlet call `http://localhost:8080/ci502/threeParamsNew`
* And shows null values

<img width="1366" height="268" alt="12 invoke_servlet_again" src="https://github.com/user-attachments/assets/43c74e7f-b162-4349-9f7f-402cf25291e3" />

### Invoke servlet using the form

* now open `http://localhost:8080/ci502/three-params-form-new.html`
* Enter values in the three text boxes
* Click Submit
* The form sends data to the servlet

<img width="1366" height="273" alt="13 enter_values_again" src="https://github.com/user-attachments/assets/6a05d208-2b27-45da-8464-70c93d6ef322" />


* now Expected output

``` text
param1 = value1
param2 = value2
param3 = value3
```

<img width="1366" height="257" alt="14 params_sent_again" src="https://github.com/user-attachments/assets/348e9cb6-0d84-4b4b-9f56-6b5019b68546" />

---




