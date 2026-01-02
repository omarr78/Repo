# Java Servlets

## Task1: Tomcat Installation and deployment of web pages

### 1. Installation

* Download Tomcat from My Studies or from the Tomcat web site.
* Save it on a directory (for example TOMCAT).
* Unzip the file

### 2. After you install it, change to the Tomcat bin directory

<img width="825" height="56" alt="01 change_directory" src="https://github.com/user-attachments/assets/0665fc73-232e-4df0-ac91-889770086b0d" />

### 3. Check if startup.sh is executable

<img width="853" height="37" alt="02 is_executable" src="https://github.com/user-attachments/assets/7b157e46-2138-4f34-a77c-af2bd54f4610" />

you can see here it is not executable

### 4. To make it executable you need to execute chmod command

<img width="878" height="110" alt="03 after_chmod" src="https://github.com/user-attachments/assets/3d7b6c3c-d5e0-4867-ad3d-67290a2dad9f" />

### After chmod it is Executable

Before it is `rw-` it means no execute premission
After `rwx` it means Execute premission added

### 5. Do the same for catalina.sh

<img width="887" height="66" alt="04 catalina" src="https://github.com/user-attachments/assets/37c9d465-cdc0-4448-9c4c-deb66c6d9033" />

### 6. Start Tomcat

<img width="1357" height="199" alt="05 start_tomcat" src="https://github.com/user-attachments/assets/108d5af8-f239-43c0-8939-bc085b81212a" />

### 7. Open Tomcat in Browser

Open your browser and go to: `http://localhost:8080`

And you should see the Tomcat welcome page

### 8. Create Your Web Application (ci502)

* Go to `webapps` directory
* create a new folder for your project, You can call it `ci502`, for example.
* Create `WEB-INF` folder inside `ci502` and the `classes` folder inside `WEB-INF`.

<img width="1277" height="201" alt="06 set_up_project_folders" src="https://github.com/user-attachments/assets/55eff963-9aec-4f9c-a21f-f63449e8c551" />


* Download first-serv-app.zip
* go to Download Unzip it
* You will get files like: `hello.html`, `index.html`, `styles.css`, `HelloWorld.java`, `MyServletServlet.java`

<img width="668" height="551" alt="07 unzip_first_serv_app" src="https://github.com/user-attachments/assets/6eb58607-7106-48b0-9e9c-51b0c6cc1398" />

* Copy HTML & CSS files `hello.html`, `index.html`, `styles.css` to `webapps/ci502`

* Copy Java servlet files `HelloWorld.java`, `MyServlet.java` to `webapps/ci502/WEB-INF/classes`

<img width="1356" height="176" alt="08 copy_files" src="https://github.com/user-attachments/assets/43ec958c-83c8-46b8-ae00-02b7556494b9" />

### 9. Test Your Web Application

* Open browser and go to `http://localhost:8080/ci502` and you should see this page

<img width="839" height="451" alt="09 open_the_link" src="https://github.com/user-attachments/assets/af2d80d3-0478-46c7-a07f-710b8139c040" />

* Click link to `hello.html` and you should see that the page loads correctly

<img width="839" height="238" alt="10 hello html" src="https://github.com/user-attachments/assets/9a7305b8-3542-459f-812f-2532c858e082" />
