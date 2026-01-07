# Maven: Project building exercises

## Task 1:

* Check if Maven is installed

<img width="667" height="68" alt="01 check_maven_installation" src="https://github.com/user-attachments/assets/4a18904e-1789-4342-b9f6-c4e993553474" />

* So you can see maven not installed
* Install maven
* Set Path with `nano ~/.bash_profile`

<img width="1354" height="721" alt="02 add_maven_classpath" src="https://github.com/user-attachments/assets/a3b15a91-65fb-426b-b4c3-daf1f1a44af5" />

* Save and exit
* Then `source ~/.bash_profile` and check installation

<img width="820" height="182" alt="03 check_mvn_installation_again" src="https://github.com/user-attachments/assets/6a3ccd2d-fbb7-47f4-8ae6-0bfea1609483" />


### 1. First Maven project

* Generate project

      mvn archetype:generate \
      -DgroupId=brighton.ci502.app \
      -DartifactId=ci502-app \
      -DarchetypeArtifactId=maven-archetype-quickstart \
      -DarchetypeVersion=1.5 \
      -DinteractiveMode=false

<img width="1357" height="709" alt="04 generate_project" src="https://github.com/user-attachments/assets/595ff1d1-23fc-4214-ae07-39825172d95a" />

* Success Build and Structure

<img width="830" height="709" alt="05 build structure" src="https://github.com/user-attachments/assets/c75153a3-cc84-41d1-979e-1ef667e4de82" />

* Build project with `mvn package`

<img width="798" height="138" alt="06 mvn_package" src="https://github.com/user-attachments/assets/9b42bbe3-8e0e-4397-8068-98baad792f29" />

* Then Jar created

<img width="918" height="160" alt="07 export_jar" src="https://github.com/user-attachments/assets/c7a35296-7280-4ed4-a3c1-e9d6a771ac7d" />

* Run program `java -cp target/ci502-app-1.0-SNAPSHOT.jar brighton.ci502.app.App`

<img width="1176" height="43" alt="08 run_program" src="https://github.com/user-attachments/assets/56c1a1c5-1a1b-4118-9a9c-d0f726f0c788" />

* Run tests with `mvn test`

<img width="1119" height="838" alt="09 run_test" src="https://github.com/user-attachments/assets/f099d2eb-595f-4f1f-9831-a49ed9e3e326" />

* Generate site with `mvn site`

<img width="796" height="179" alt="10 generate_site" src="https://github.com/user-attachments/assets/6bda645f-09eb-4ada-95e5-4e0303e8c45c" />

* This the result of generating a site

<img width="1357" height="311" alt="11 result_from_site" src="https://github.com/user-attachments/assets/340775ca-2f7d-4c52-bc3f-6d45117ff393" />

* Site generated in: `target/site`

<img width="1006" height="91" alt="12 files_generated_from_site" src="https://github.com/user-attachments/assets/dad551ee-5b42-4cb5-85a1-391ba5b4b3dc" />

### 2. Building Existing Project with Maven (NumOps)

* Generate Maven structure

<img width="1766" height="795" alt="13 generating_project_again" src="https://github.com/user-attachments/assets/6cb27141-929d-4db7-ba4c-2b570c92fd40" />

* Move Java files
* Go to: `cd NumOps/src/main/java/bton/ci502`
* Then copy files

<img width="889" height="69" alt="14 copy_files" src="https://github.com/user-attachments/assets/65455e6b-5710-4575-81b8-e4e46408b8ee" />



* Delete App.java with `rm App.java`

<img width="676" height="21" alt="15 remove_app_java" src="https://github.com/user-attachments/assets/c33e7806-7004-4e44-a921-b208e304e781" />


* Delete AppTest.java with `rm AppTest.java`

<img width="727" height="19" alt="16 remove_AppTest_java" src="https://github.com/user-attachments/assets/7250a899-bd83-4943-8929-1cce509c6fd2" />

* Add Unit Test
* Copy NumOpsTest.java

<img width="961" height="23" alt="17 copy_tests" src="https://github.com/user-attachments/assets/29a04b00-095a-446a-a79c-9b92d895159a" />


* Run tests with `mvn test` if no error success

<img width="802" height="365" alt="18 test_result" src="https://github.com/user-attachments/assets/344fc213-de3a-4b43-b991-91f4998615a5" />

