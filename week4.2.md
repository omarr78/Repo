## Task2: 

### 1. Change the directory to the classes folder, compile the servlets and excpecting error

<img width="1156" height="113" alt="01 compilation_error" src="https://github.com/user-attachments/assets/0666cc74-8003-43c5-b4a9-9e55f9754495" />

### Why this happens ?

* Servlets are not normal Java programs and They need `servlet-api.jar`
* Java compiler does not know where this library is
* Solution → Set CLASSPATH

