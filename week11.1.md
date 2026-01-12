## STEP 1: Download Hadoop

* First download the hadoop tar file from My Studies

## STEP 2: Unpack Hadoop

* We should extract it with `tar -xvf hadoop-3.4.1-lean.tar`

<img width="562" height="29" alt="01 unpack" src="https://github.com/user-attachments/assets/43e1ed6b-f45b-4489-a488-c695544147c3" />

## STEP 3: Find Java Location (JAVA_HOME)

### Why?

* Hadoop is written in Java.
* It must know where Java is installed.

<img width="436" height="52" alt="02 find_java_location" src="https://github.com/user-attachments/assets/7a6bec16-77b2-45f4-8a70-c7ab0e96a461" />

* Remove `/bin/java`
* So Your JAVA_HOME is: `/usr/lib/jvm/java-21-openjdk-amd64`

## STEP 4: Set JAVA_HOME in Hadoop

### Why?

* Without this, Hadoop will not start.

* Go to config folder: `cd hadoop-3.4.1-lean/etc/hadoop`

* Open config file: `nano hadoop-env.sh`

<img width="731" height="46" alt="03 open_config_file" src="https://github.com/user-attachments/assets/c19e993b-0849-44cf-ac3a-b49e4b385163" />

* Find this line (around line 54): `# export JAVA_HOME=`

* Change it to: `export JAVA_HOME=/usr/lib/jvm/java-21-openjdk-amd64`

<img width="1366" height="768" alt="04 add_classpath" src="https://github.com/user-attachments/assets/73c0e592-5690-456d-aed7-15b4e2cf497e" />


## STEP 5: Test Hadoop Installation

    cd ../../
    bin/hadoop

<img width="757" height="588" alt="05 test_hadoop" src="https://github.com/user-attachments/assets/cec989d7-8420-4aef-938e-4b48c2b85464" />

* If Hadoop works, you’ll see:
  * Hadoop usage instructions  
  * A long list of commands


---

## There are 3 modes:

### 1. Local (Standalone) Mode
### 2. Pseudo-Distributed Mode
### 3. Fully-Distributed Mode

---


## STANDALONE MODE (No Cluster)


### What is this?

* Hadoop runs as one Java program

* No HDFS

* Best for beginners

## STEP 6: Create Input Folder

### Why?

* Hadoop needs input data to process.
* command: `mkdir input`

<img width="368" height="24" alt="06 mkdir_input" src="https://github.com/user-attachments/assets/0ffb437b-2bbd-418b-ad38-199a1724dc1d" />


STEP 7: Copy XML Files as Input

### Why?

* We need sample data.
* Command: `cp etc/hadoop/*.xml input`

<img width="876" height="22" alt="7 copy_to_input" src="https://github.com/user-attachments/assets/9c1c0c0f-5367-4672-9394-44f9171cecb3" />

* Now input folder contains:

## STEP 8: View Example Programs

### Why?

* Hadoop provides ready-made MapReduce examples

* Command: `bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-3.4.1.jar`

<img width="1366" height="599" alt="09 view_example_program" src="https://github.com/user-attachments/assets/06db98d2-02b2-47c4-9768-fe16d18252db" />

### Output: List of programs like:

* wordcount
* grep
* pi
* sort

## STEP 9: Run Hadoop GREP Example

### What does this do?

* Searches text in files
* Similar to Linux grep
* Uses MapReduce

* Command: `bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-3.4.1.jar grep input output 'dfs[a-z.]+'`

<img width="1366" height="44" alt="10 grep" src="https://github.com/user-attachments/assets/959abdf3-89d3-4e05-b6f6-2a3b38cf5068" />

* grep → Program name
* input	→ Input folder
* output → Output folder
* dfs[a-z.]+ → Search pattern


### STEP 10: View Output

Command: `cat output/*`

* You’ll see: Words related to dfs

<img width="378" height="47" alt="11 search_result" src="https://github.com/user-attachments/assets/02506107-a9e1-4314-8421-d1b49e695e78" />

---

## PSEUDO-DISTRIBUTED MODE

### What is this?

* Looks like a real cluster
* Still on one machine
* Uses HDFS
* Each service runs in a separate process


### STEP 11: Enable Password-less SSH


### Why?

* Hadoop daemons communicate using SSH
* Even on the same machine.

* Check SSH Access

<img width="291" height="49" alt="13 asking_for_password" src="https://github.com/user-attachments/assets/79fff0a5-5bd7-4173-81a3-31063c9b84ff" />

* If it logs in without password → skip next steps.

* If Password Is Asked → Create SSH Keys
* Command: `ssh-keygen`

<img width="738" height="465" alt="13 create_ssh" src="https://github.com/user-attachments/assets/893155bb-7ea4-4d93-b97f-93bcf0cd9331" />

* Press ENTER for everything.

* Add Key & Set Permission & Test again

<img width="775" height="93" alt="14 add_set_test" src="https://github.com/user-attachments/assets/44b6fefd-7590-422d-bfd6-2e3e9ac84d90" />

* Now you should be able to ssh to localhost without a password.
