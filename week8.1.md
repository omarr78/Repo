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

