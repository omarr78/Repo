## Task2: 

### 1. Change the directory to the classes folder, compile the servlets and excpecting error

<img width="1156" height="113" alt="01 compilation_error" src="https://github.com/user-attachments/assets/0666cc74-8003-43c5-b4a9-9e55f9754495" />

### Why this happens ?

* Servlets are not normal Java programs and They need `servlet-api.jar`
* Java compiler does not know where this library is
* Solution → Set CLASSPATH

### 2. Set CLASSPATH

* Go to Home Directory `cd`

<img width="447" height="27" alt="open_bash_profile" src="https://github.com/user-attachments/assets/69f8f2fb-339e-4fac-9848-9ab2ea778597" />

* open `.bash_profile` with nano and add these 2 lines at the bottom

<img width="1284" height="690" alt="03 nano_bash_profile" src="https://github.com/user-attachments/assets/cc69baae-22b1-4d70-8989-74ceccb5a398" />

* Save and exit nano
* Apply the Changes with `source .bash_profile` and Verify CLASSPATH

<img width="706" height="64" alt="04 verify_classPath" src="https://github.com/user-attachments/assets/e06d93da-0969-456f-9748-83f8f8b9a9a9" />




