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

