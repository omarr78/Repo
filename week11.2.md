 # Part2: Hadoop Configuration

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
