 # Part 2: Hadoop Configuration

## What Is Hadoop Configuration?

### Hadoop uses XML configuration files to know:

* Where the file system is

* How many copies of data to keep

* How to run on your machine

### Right now, we are telling Hadoop:

* Use HDFS instead of local filesystem

* Run on one machine (localhost)
  
## Step 1: Go to Hadoop config directory

* Command: `cd ~/Downloads/week11/hadoop-3.4.1-lean/etc/hadoop`

<img width="763" height="23" alt="01 cd_config_files" src="https://github.com/user-attachments/assets/16bcc271-611d-4ca7-bfbe-3e952b8eeab5" />

* This folder contains all Hadoop configuration files.

-- 

## STEP 2: Edit core-site.xml

### What is core-site.xml?

* This file tells Hadoop:

### “What file system should I use?”

* By default, Hadoop uses local filesystem.
* We want HDFS.

* Open the file with `nano core-site.xml`

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/90408335-72e1-45f1-a526-68d4bed58ab2" />

* Save and Exit


* fs.defaultFS ->	Default file system
* hdfs://localhost:9000 -> Use HDFS on this machine

---

## STEP 3: Edit hdfs-site.xml

### What is hdfs-site.xml?

* This file controls how HDFS stores data.
* Open the file with `nano hdfs-site.xml`

<img width="1366" height="768" alt="03 modify_hdfs_site" src="https://github.com/user-attachments/assets/c803f41f-b452-47ec-b099-d8f7d6c89ed6" />


* dfs.replication ->	Number of copies of data
* value = 1	-> Only 1 copy (because you have 1 machine)

---

# part 3 : Execution


## STEP 1: Format the HDFS (ONE TIME ONLY)

### What does “format” mean?

* It initializes HDFS
* Creates metadata for NameNode Like formatting a hard disk
* Do this ONLY ONCE

* Command: `cd ~/Downloads/week11/hadoop-3.4.1-lean`
* after that: `bin/hdfs namenode -format`

<img width="640" height="49" alt="04 format_command" src="https://github.com/user-attachments/assets/8be9bb9d-f19f-4037-9936-7a8ee124f9b6" />

* Expected result:

* Lots of text

* Ends with something like: `Storage directory has been successfully formatted`

 <img width="770" height="26" alt="05 successful_format" src="https://github.com/user-attachments/assets/79f0a41e-6b69-4de0-a127-85b2fd5e0a57" />

* That means HDFS is ready

---

## STEP 2 : Start HDFS Daemons

### What are daemons?

* Background services:
 * NameNode → Master (metadata)
 * DataNode → Stores data

* Start HDFS: `sbin/start-dfs.sh` & Check running services: `jps`

<img width="554" height="19" alt="06 start_hdfs" src="https://github.com/user-attachments/assets/3e62d2c0-53cd-4406-9360-156556e5f0ae" />
<img width="1035" height="88" alt="Screenshot from 2026-01-12 09-28-50 (5)" src="https://github.com/user-attachments/assets/11ed613f-6c09-4012-bc72-98b81a6986ee" />
<img width="483" height="69" alt="Screenshot from 2026-01-12 09-28-50 (1)" src="https://github.com/user-attachments/assets/badf76c1-bcf3-4f80-9b9d-492cb2323253" />
<img width="235" height="91" alt="09 jps_result" src="https://github.com/user-attachments/assets/72e49298-171d-4b12-8e56-8e96c13715b4" />


* You should see:
  * NameNode
  * DataNode
  * SecondaryNameNode
  * Jps


* This means Hadoop is running correctly.


## STEP 3: Open Hadoop Web Interface -> To visually confirm Hadoop is running.

* Open browser and go to: `http://localhost:9870/`
* You should see: Hadoop NameNode web UI
* Cluster status = Active

 <img width="1285" height="614" alt="10 hadoop_status" src="https://github.com/user-attachments/assets/dc9a9e78-a0c5-4393-91c3-ce466b1c0106" />

* Live Nodes = 1

<img width="1143" height="37" alt="11 live_node" src="https://github.com/user-attachments/assets/3d0dcb89-1751-48c0-a474-3aba258e3b56" />

---

STEP 4: Create User Directory in HDFS -> Hadoop requires a home directory for each user.

Command: `bin/hdfs dfs -mkdir -p /user/root`

<img width="724" height="26" alt="12 home_directory" src="https://github.com/user-attachments/assets/ec378835-fb71-4704-a53f-aa6c6ffa249c" />

* dfs ->	HDFS command
* -mkdir ->	create directory
* /user/root ->	home directory

---

## STEP 5: Create Input Directory in HDFS

### Important Difference

* mkdir → local filesystem
* hdfs dfs -mkdir → HDFS

### Create input folder in HDFS: `bin/hdfs dfs -mkdir input`

<img width="261" height="24" alt="13 create_input" src="https://github.com/user-attachments/assets/38348b2e-3115-4968-8f94-05d7b0707976" />

### Copy XML files into HDFS: `bin/hdfs dfs -put etc/hadoop/*.xml input`

<img width="411" height="25" alt="14 fill_input" src="https://github.com/user-attachments/assets/75ff2c68-2555-4411-9430-59924d8bbb03" />

### Your data is now in HDFS, not local disk.

---

## STEP 6 : Run MapReduce on HDFS

### Command: `bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-3.4.1.jar grep input output 'dfs[a-z.]+'`

<img width="1346" height="46" alt="image" src="https://github.com/user-attachments/assets/09f8e9d7-ebc6-4d04-8aaf-0724089b1bf9" />

### What happens?

* Hadoop reads files from HDFS
* Runs MapReduce
* Stores result in HDFS output directory

---

## STEP 7: View Output

### View Directly from HDFS `bin/hdfs dfs -cat output/*`

<img width="660" height="26" alt="image" src="https://github.com/user-attachments/assets/a8b6005a-3581-4fae-a45f-5b56cd5eb488" />

### Result

<img width="237" height="49" alt="17 view_output" src="https://github.com/user-attachments/assets/c632a878-6122-4c9c-9323-512eb1633d70" />

---

# Part 3: Counting words with Hadoop

## What Is “WordCount” in Hadoop?

### WordCount is the classic Hadoop example:

* It reads text files
* Counts how many times each word appears
* Uses MapReduce
* Stores results in HDFS


### Example:

* the     5231
* and     4890
* holmes  387

## STEP 1: Put the Text File on Your Local Machine

### What to do?

* Download SherlockHolmes.txt from My Studies

* Save it locally inside: `hadoop-3.4.1-lean/input/`

<img width="632" height="27" alt="18 copy_text_file" src="https://github.com/user-attachments/assets/81a6acc5-2565-44ae-ba88-44aed8b1a069" />

## STEP 2: Copy the Text File into HDFS

### Why?

* Hadoop processes files only from HDFS, not local disk.

* Command: `bin/hdfs dfs -put input/SherlockHolmes.txt input`

<img width="690" height="26" alt="19 put_into_hdfs" src="https://github.com/user-attachments/assets/3e8fd555-6f14-4155-81aa-4d85d71d72b1" />

## STEP 3: Remove Old Output Directory (IMPORTANT)

## Why?

Hadoop will not overwrite output directories.

Command: `bin/hdfs dfs -rm -r output`

<img width="281" height="23" alt="20 remove_output_file" src="https://github.com/user-attachments/assets/a2f9c8d1-0997-43df-b6cb-810df5d79703" />

<img width="161" height="26" alt="21 output_deleted" src="https://github.com/user-attachments/assets/3416f652-55e5-4290-8031-55d85497e6b9" />


## STEP 4: Run WordCount MapReduce Job

* Command: `bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-3.4.1.jar wordcount input output` 

<img width="1345" height="47" alt="22 run_wordCount" src="https://github.com/user-attachments/assets/1ef7a17c-9bfb-47dd-88e8-503ec36374db" />

## STEP 5: View WordCount Results (HDFS)

* Command: `bin/hdfs dfs -cat output/*`

<img width="1366" height="768" alt="23 output" src="https://github.com/user-attachments/assets/ee036b4e-1463-4ca5-b094-96deb4013ff8" />


* Words are alphabetically sorted
* Numbers = word frequency


## STEP 6: Copy Results from HDFS → Local Machine

### Why?

* To read, save, or submit results.

* Command: `bin/hdfs dfs -get output output`

 <img width="325" height="27" alt="24 move_to_local" src="https://github.com/user-attachments/assets/f2fc5b71-1411-4635-8938-2e89e1e6a1f9" />

* This creates a local directory: `hadoop-3.4.1-lean/output/`

* To View locally: `cat output/*`

<img width="138" height="26" alt="25 view_locally" src="https://github.com/user-attachments/assets/1db467cb-2b67-4b3c-8382-18984139d8d7" />

<img width="1366" height="768" alt="23 output" src="https://github.com/user-attachments/assets/50be5dc6-5946-4cbd-9c81-81e4b982c8ea" />

