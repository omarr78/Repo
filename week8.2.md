## Task2:

### 1. Generate a Web Project with Maven

* Make sure that GlassFish is running

<img width="1093" height="312" alt="01 start_server" src="https://github.com/user-attachments/assets/bd85bc00-ecae-43c5-84fb-04985a85dbac" />

* then check it in browser `http://localhost:4848`
* You should see admin page opens

* Choose where to create the project

      cd ~
      mkdir maven-web
      cd maven-web

* Generate a Maven Web application

      mvn archetype:generate \
      -DgroupId=bton.ci502 \
      -DartifactId=maven-web-app \
      -DarchetypeArtifactId=maven-archetype-webapp \
      -DarchetypeVersion=1.5 \
      -DinteractiveMode=false

<img width="1677" height="968" alt="02 maven_generating_files" src="https://github.com/user-attachments/assets/05857a05-2f68-4619-b8ee-6c7040bb1896" />


* Check the generated structure

<img width="285" height="133" alt="03 folder_strucutre" src="https://github.com/user-attachments/assets/a2802890-d892-49fc-bcea-208180f1d7f7" />

* Verify WAR packaging

* Open `pom.xml` with `nano pom.xml`

* Make sure this exists: `<packaging>war</packaging>` 

<img width="1366" height="722" alt="04 package_war" src="https://github.com/user-attachments/assets/1616fb7c-55f5-44d3-a586-5c3fe58ad99a" />

* Save and exit

* Build the WAR file with `mvn package`
* You Should see `target/maven-web-app.war`

<img width="1177" height="246" alt="05 result_mvn_package" src="https://github.com/user-attachments/assets/c8189768-2269-42f4-a2dd-6a4d4a708500" />


* Deploy to GlassFish
* Copy WAR to GlassFish autodeploy folder:

      cp target/maven-web-app.war \
      ~/glassfish7/glassfish/domains/domain1/autodeploy/


<img width="1355" height="49" alt="06 copy_war" src="https://github.com/user-attachments/assets/53ef2d0f-e985-4525-a88a-604d67a6c2fc" />

* Test in browser
* Open `http://localhost:8080/maven-web-app`


<img width="1366" height="196" alt="07 test_web_app" src="https://github.com/user-attachments/assets/c1a7b57c-ba2a-4011-bcea-b91277843ab9" />

---

### 2. Build a JSF Project with Maven 

* Now we do the same thing, but for JSF
* Generate another web project

<img width="1355" height="750" alt="08 maven_generating_files" src="https://github.com/user-attachments/assets/5b6c2acc-8f90-428d-bcfd-7a3a83f77aa3" />

* Go into it: with `cd my-jsf-app`
* Build & deploy once (test first)

<img width="799" height="178" alt="09 mvn_package" src="https://github.com/user-attachments/assets/905a0ba4-0280-4829-9301-c365235e2f0c" />

<img width="761" height="47" alt="10 deploy_project" src="https://github.com/user-attachments/assets/a9913e8d-54bf-4bf8-a21c-00768079bdf0" />

* Test in browser
* Open `http://localhost:8080/my-jsf-app`

<img width="1366" height="264" alt="11 test_web_app" src="https://github.com/user-attachments/assets/bb03dcd0-0c51-4577-9822-210ec90963ac" />

---

### 3. Add JSF Dependencies

* JSF needs Jakarta libraries to compile managed beans

* Edit pom.xml with `nano pom.xml`
* And add dependencies

<img width="1366" height="768" alt="12 add_dependency" src="https://github.com/user-attachments/assets/ef59b430-9380-45e3-be94-b1a34ab3514b" />

* Save and exit

---

### 4. WEB-INF Configuration

* Copy JSF config files

* From your previous JSF project, copy: `web.xml`, `faces-config.xml` to `my-jsf-app/src/main/webapp/WEB-INF/`


<img width="1356" height="113" alt="13 copy_files" src="https://github.com/user-attachments/assets/97454228-8fe4-4003-970b-d4ff50b08584" />

---

### 5. Create a JSF Managed Bean

* Create Java package with `mkdir -p src/main/java/ci502/jsf`
* Create `WelcomeBean.java` with `nano WelcomeBean.java`

<img width="906" height="47" alt="14 mkdir_nano" src="https://github.com/user-attachments/assets/96180ee5-bbe5-47df-a968-c5558e5b1cf9" />

<img width="1366" height="768" alt="15 create_welcome_bean" src="https://github.com/user-attachments/assets/712ca9f2-924f-428c-9766-4ffe6784a8d7" />


* Save and exit

---

### 6. Create JSF View

* Create home.xhtml with `nano src/main/webapp/home.xhtml`

<img width="1366" height="768" alt="16 create_home_xhtml" src="https://github.com/user-attachments/assets/5b171c16-7da8-4569-9e6b-94173ec121e1" />

* Save and exit

---

### 7. Build, Deploy, Run

* Build with `mvn package`

<img width="801" height="136" alt="17 package_war" src="https://github.com/user-attachments/assets/130ecefa-f241-45e0-949d-6c2ccc1fcf78" />

<img width="425" height="26" alt="18 target_war" src="https://github.com/user-attachments/assets/da00c26c-687d-4fb0-b813-5b991103cf5e" />

* Deploy

<img width="1355" height="48" alt="19 deploy_jar" src="https://github.com/user-attachments/assets/eb2b40fd-6531-49b3-8393-38f1e2a4207f" />

* Run in browser `http://localhost:8080/my-jsf-app/home.jsf`

* You should see: `I am alive!`

<img width="1366" height="378" alt="20 run_war" src="https://github.com/user-attachments/assets/c9c20c21-fe2c-41fa-814d-1e634840435b" />
