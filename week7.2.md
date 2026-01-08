## Task2:

### What is JSF Navigation

In JSF:

* Buttons call methods in Managed Beans

* Those methods return a string

* The string decides which page JSF forwards to

* Example: `return "page2";` this is goes to `page2.xhtml`

* JSF uses forward, not redirect So the URL does not change

### 1. BASIC NAVIGATION (navigate.zip)

* Download `navigate.zip` from My Studies
* Unzip navigate.zip

<img width="1366" height="768" alt="01 unzip_navigation" src="https://github.com/user-attachments/assets/6044712f-c7ee-4234-a8e6-ff0cecb88bb9" />

* cd navigate
* Check directory structure

 <img width="458" height="326" alt="02 check_directory_structure" src="https://github.com/user-attachments/assets/d7487658-73f6-40f5-a8f9-b2a3f3c5601e" />

* Compile the Bean
* Go above ci502 directory:

<img width="768" height="47" alt="03 compile_navigation" src="https://github.com/user-attachments/assets/6c89766b-279f-488c-97ee-3ef58a030609" />

* Create WAR file

* Go back to navigate root:

<img width="819" height="354" alt="04 create_war" src="https://github.com/user-attachments/assets/aa397b32-9624-4e66-b2ba-d0ed2521e716" />


* Deploy to GlassFish

<img width="672" height="49" alt="05 Deploy_to_glassfish" src="https://github.com/user-attachments/assets/2de7a7f3-0aaa-4caa-8e84-e4ff2ff9afd7" />

* Test in browser
* open: `http://localhost:8080/navigate`
* it will redirect to `http://localhost:8080/navigate/page-a.jsf`

<img width="1366" height="659" alt="06 page-a" src="https://github.com/user-attachments/assets/b32c12b3-d552-48ec-8ced-784fbd493aee" />

* Click on `Go to Page B`

<img width="1366" height="604" alt="07 page-b" src="https://github.com/user-attachments/assets/868374ce-2de7-4411-ae92-9cbc556779ec" />

---

### 2. BUILD YOUR OWN NAVIGATION GAME

* Navigation Flow You Must Build

<img width="649" height="131" alt="image" src="https://github.com/user-attachments/assets/d6303d41-2b29-4e10-bba9-07795a404338" />

* Create new application directory

<img width="684" height="65" alt="09 create_app_dir" src="https://github.com/user-attachments/assets/ded997c8-9000-422c-b154-4ab0eb7339b2" />

* Create Managed Bean with `nano WEB-INF/classes/ci502/game/GameBean.java`

<img width="1366" height="768" alt="10 create_gamebean" src="https://github.com/user-attachments/assets/93a9e5f8-a658-48ad-8475-39a1bf52b5c9" />

* Exit and save

* Compile Bean

<img width="812" height="47" alt="11 compile_game_bean" src="https://github.com/user-attachments/assets/31019552-ebaf-4fa8-acaa-1c30030266bb" />

* Create JSF pages

* Create `a.xhtml` with `nano a.xhtml`
<img width="1366" height="768" alt="12 a_xhtml" src="https://github.com/user-attachments/assets/fcfae924-5b4c-472f-b493-de4506aac0cb" />

* Create `b.xhtml` with `nano b.xhtml`
<img width="1366" height="768" alt="13 b_xhtml" src="https://github.com/user-attachments/assets/c916276d-9d33-4e6a-90ad-86e8c0877917" />

* Create `c.xhtml` with `nano c.xhtml`
 <img width="1366" height="768" alt="14 c_xhtml" src="https://github.com/user-attachments/assets/afb026d4-9ee5-4f08-84fc-e40038e4f2cb" />

* Create `victory.xhtml` with `nano victory.xhtml`
<img width="1366" height="768" alt="15 victory_xhtml" src="https://github.com/user-attachments/assets/22e24237-6eec-4ede-983c-2579d299dcd0" />

* Create `defeat.xhtml` with `nano defeat.xhtml`
<img width="1366" height="768" alt="16 defeat_xhtml" src="https://github.com/user-attachments/assets/a6a42e59-cc96-45c1-8988-f60b55dd0332" />

* Create WAR with `jar -cvf jsf-game.war *`

<img width="847" height="289" alt="17 create_war" src="https://github.com/user-attachments/assets/5244134f-564a-41fe-9b83-7ccd03cf5bc8" />

* Deploy

<img width="1166" height="26" alt="18 deploy" src="https://github.com/user-attachments/assets/d571d4c6-c68b-4379-87bd-949af8a36eb4" />

* test open `http://localhost:8080/jsf-game/a.jsf` in browser

<img width="1366" height="371" alt="19 start_game" src="https://github.com/user-attachments/assets/d4a970e5-a9f5-42c6-86a1-8078e754297b" />

<img width="1366" height="366" alt="20 level_B" src="https://github.com/user-attachments/assets/ffda24e3-ffe3-4923-b19e-f1d15ef6e7ff" />
<img width="1366" height="360" alt="21 level_C" src="https://github.com/user-attachments/assets/9c68390a-17f3-4f6b-ad3a-16527bb30b02" />

<img width="1366" height="239" alt="22 you_lost" src="https://github.com/user-attachments/assets/e9f4a888-9657-4f7e-8bbc-99e2e4d4c289" />

---

### 3. USER REGISTRATION (register.zip)

* unzip register.zip

<img width="1354" height="707" alt="23 unzip_register" src="https://github.com/user-attachments/assets/4ee299bd-d5b8-4227-ad66-228ebf343435" />

* Compiler User.java

<img width="832" height="25" alt="24 compile_user_java" src="https://github.com/user-attachments/assets/26c783b3-048f-4bad-84e9-e00d5573752c" />

* Create WAR & Deploy

<img width="1245" height="423" alt="25 create_war_deploy" src="https://github.com/user-attachments/assets/41057840-5e25-44ed-9767-0dbddbb795ac" />

* Test register
* Open `http://localhost:8080/register`

<img width="1366" height="407" alt="25 test_register" src="https://github.com/user-attachments/assets/bc5e09d5-ce47-417d-9b6e-7472f28ee470" />

---

### 4. YOUR OWN REGISTRATION APP

### Requirements

#### 1. First name

#### 2. Last name

#### 3. If missing → error page

#### 4. If OK → results page with <ul>


* Create Application Directory

<img width="827" height="64" alt="27 create_app_directory" src="https://github.com/user-attachments/assets/cb0717a4-4e16-4342-ab1d-d2d559b34cc1" />

* Your structure should now be:

<img width="468" height="333" alt="28 app_structure" src="https://github.com/user-attachments/assets/0b6cbf84-2367-426f-8aab-8434385f025a" />

* Create RegisterBean.java with `nano WEB-INF/classes/ci502/register/RegisterBean.java`

<img width="1855" height="1050" alt="29 create_register_bean" src="https://github.com/user-attachments/assets/48196055-e436-49b3-ae0b-963ca09b9665" />

* Save and exit

* Compile the Bean

<img width="976" height="46" alt="30 compile_bean" src="https://github.com/user-attachments/assets/5207d260-e3e9-408a-bad7-250e5f02f7a9" />

* Create index.xhtml (Input Form) with `nano index.xhtml`

<img width="1366" height="768" alt="31 create_index_xhtml" src="https://github.com/user-attachments/assets/424ddc8e-be66-42ac-9b3d-61bb69dcab21" />

* Create result.xhtml with `nano result.xhtml`

<img width="1366" height="768" alt="32 result_xhtml" src="https://github.com/user-attachments/assets/b620715a-1625-4ffb-b186-56eafd90b3ec" />

* Create error.xhtml with `nano error.xhtml`


<img width="1366" height="768" alt="33 error_xhtml" src="https://github.com/user-attachments/assets/bee692b8-85b4-4c0c-b163-b5874a2cf46c" />

* Create WAR file & Deploy

<img width="1267" height="312" alt="34 create_war_deploy" src="https://github.com/user-attachments/assets/1a7509a4-47c4-4690-a8e7-e26e657775e5" />

* Test in Browser open `http://localhost:8080/register2/index.jsf`

* first we leave firstname and lastname and click on submit

<img width="1366" height="562" alt="35 input_form" src="https://github.com/user-attachments/assets/15a0ce77-8ceb-4dd6-ad2e-01f395208f7e" />

<img width="1366" height="381" alt="36 error_page" src="https://github.com/user-attachments/assets/b8ab6874-a4a4-4fdf-9000-950017a0467b" />

* Then we enter the firstname and the lastname

<img width="1366" height="556" alt="37 enter_test" src="https://github.com/user-attachments/assets/21e6dadd-68aa-449c-b166-bc6276cf04f4" />

<img width="1366" height="396" alt="38 regestration_successful" src="https://github.com/user-attachments/assets/e178c5c9-76e2-4c17-9e46-aa515176af12" />

---





