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

