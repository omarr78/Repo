## Task4:

### 1. Copy your image file to `ci502/WEB-INF/classes/images`

<img width="1208" height="68" alt="01 copy_image" src="https://github.com/user-attachments/assets/7141b5d4-459a-463d-a414-6265a8d3498e" />

### 2. Create the ImgServlet.java file with `nano ImgServlet.java`

<img width="1353" height="718" alt="02 edit_on_ImgServlet" src="https://github.com/user-attachments/assets/afcd2cdb-58b1-44b5-89bb-8556a6b0bf5f" />

* Save and exit

### 3. Compile the servlet

<img width="1353" height="69" alt="03 compile_imgServlet" src="https://github.com/user-attachments/assets/06d48448-f6ce-4647-afe6-b435b014f4d4" />

### 4. Restart Tomcat

<img width="1358" height="376" alt="04 restart_tomcat" src="https://github.com/user-attachments/assets/9a67d4ed-b264-4c20-a413-d8f4286dca6d" />

### 5. Test servlet directly

* open browser and go to `http://localhost:8080/ci502/img`
* Expected result -> the image itself appears in the browser

<img width="1366" height="768" alt="05 test_servlet" src="https://github.com/user-attachments/assets/5407f86a-15fe-4ace-8853-b042da4946dc" />

### 6. Invoke the servlet from an HTML file

* create an HTML file with `nano ci502/show-image.html`
* Write HTML code

<img width="1353" height="719" alt="06 HTML_code" src="https://github.com/user-attachments/assets/90c28e6e-f8b3-4772-8fc4-0de9e198f397" />

* Save and exit

* Now test via HTML page

* Open your browser, go to `http://localhost:8080/ci502/show-image.html`

* Expected result, Page loads, Image is displayed

* Image is coming from the servlet, not directly from disk


<img width="1366" height="768" alt="07 open_html_page" src="https://github.com/user-attachments/assets/14596acb-09a2-444c-bbff-9aab8c32543c" />





