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


