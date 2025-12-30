# Task 1

### From CI502 home page WEEK 1 Course Content, download Week1 exercise files.zip file and extract
### the following Java files:

* Semaphore.java
* Util.java
* Data.java
* P1.java
* P2.java
* P1P2s.java

<img width="707" height="210" alt="files" src="https://github.com/user-attachments/assets/0ac560bd-dc4c-4cf7-b279-ef64dfbcfba3" />

* `Semaphore.java` contains the implementation of P and V semaphore operations that will be used to
synchronize the processes P1 and P2.

* The `P1P2s` class is used to start P1 and P2 as independent processes.

---

## Step1: 

* open the terminal
* compile all java files with javac, and run P1P2s that starts the process P1 and P2.


<img width="1019" height="579" alt="run_without_semaphore" src="https://github.com/user-attachments/assets/cdc927e4-c4d9-4106-9216-525617687646" />


> [!NOTE]
> Note that these two processes don’t execute the P and V semaphore operations and the access to the
critical section is not synchronized
> This leads to P1 and P2 will run at the same time without any synchronization and both will enter the critical section together

* Modify the code in P1 and P2 (Add Semaphores) - Before entering lock and After finishing unlock

<img width="598" height="354" alt="run_with_semaphoreP1" src="https://github.com/user-attachments/assets/1cdf3472-8583-4645-8aff-9011b3ba1197" />
<img width="598" height="331" alt="run_with_semaphoreP2" src="https://github.com/user-attachments/assets/71de7e20-b612-499a-8e03-e44a18cc54f4" />

* Run again after modification


<img width="1020" height="513" alt="after_modification" src="https://github.com/user-attachments/assets/9bd1c5ad-582a-42f9-be16-6f3496b7c8e1" />

---

# Task 2

This exercise simulates trains travelling along a single rail track through critical sections. Your task is to insert
semaphore operation that will prevent train collisions. Two trains will collide if they happen to be in a critical
section at the same time.


<img width="466" height="159" alt="image" src="https://github.com/user-attachments/assets/31674e18-42bc-45ae-aeec-1a6d4171e946" />

Figure shows two train yards (A and B) with two trains in each yard ready to leave. You need the following files
which you have already downloaded in the zip file::
* Train1.java
* Trainc1.java
* Semaphore.java
* Util.java

## 1- Compile all Java files and run Trainc1

It will simulate the trains movement through the critical sections. It is
just a control program that starts trains from each yard.


<img width="1022" height="570" alt="result_from_trains_collisions2" src="https://github.com/user-attachments/assets/bbb06fa9-e7eb-4a7d-967a-cdcce720d762" />

## 2- Modying on code to fix the collision between trains

<img width="626" height="372" alt="fix_train_collision" src="https://github.com/user-attachments/assets/3a220ba9-0b32-496a-adb4-ec0df0e9a2c0" />

## 3- And this is the result after fix the collision

<img width="1021" height="571" alt="after_fix_collision" src="https://github.com/user-attachments/assets/2ee9dace-1f4f-4603-bf29-8c1133c0a103" />


