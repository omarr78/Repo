## Task1: Message digest (Hash Functions)

### What is a Message Digest?

### A message digest (hash) is like a digital fingerprint of a file or text:

* Small in size

* Unique to the content

* If the content changes even one letter, the digest changes completely

### We will use:

* md5sum
* sha1sum
* sha224sum, sha256sum, sha384sum, sha512sum

### 1. Create a file and generate MD5 & SHA-1 hashes

* Create a file with content “Hello World” & Check the file content

<img width="556" height="66" alt="01 create_show_content" src="https://github.com/user-attachments/assets/09662e47-5a59-425e-ae1e-1a72b45f7326" />

* Generate MD5 hash with `md5sum file1.txt`
<img width="439" height="48" alt="02 md5_sum" src="https://github.com/user-attachments/assets/ff48c65e-f3ea-478c-829a-b7384a9854db" />

* 32 hexadecimal characters
* This is the `MD5 digest`

* Generate SHA-1 hash with `sha1sum file1.txt`

<img width="514" height="48" alt="03 sha1_sum" src="https://github.com/user-attachments/assets/e688dd50-ea34-460c-8bf6-6ec74f9ee25c" />

* 40 hexadecimal characters
* This is the SHA-1 digest

### 2. Same file → Same digest | Different algorithms → Different sizes

* Run the same commands again `md5sum file1.txt`, `sha1sum file1.txt`

<img width="526" height="182" alt="04 same_output" src="https://github.com/user-attachments/assets/634dbcdb-2ab0-4795-b07f-3837dba6b271" />

* You’ll see exactly the same hash values

### 3. Try different SHA variants

* We now hash text directly (not files)

<img width="1325" height="223" alt="05 sha_variants" src="https://github.com/user-attachments/assets/92df5c9f-3db7-485f-b053-52731f8b663c" />

* Important note: `-n` prevents adding a newline

* `echo -n "HELLO" | sha1sum` 40 characters (20 bytes)

* `echo -n "HELLO" | sha224sum` 56 characters (28 bytes)

* `echo -n "HELLO" | sha256sum` 64 characters (32 bytes)

* `echo -n "HELLO" | sha384sum` 96 characters (48 bytes)

* `echo -n "HELLO" | sha512sum` 128 characters (64 bytes)


### What you should observe

| Algorithm | Output Size |
| --------- | ----------- |
| SHA-1     | 40 chars    |
| SHA-224   | 56 chars    |
| SHA-256   | 64 chars    |
| SHA-384   | 96 chars    |
| SHA-512   | 128 chars   |

* Stronger algorithms → Longer digests

---

### 3. Caesar Cipher & DES in Java

* Now we move to Java encryption programs

* 1. Caesar Cipher
* Download files from My Studies
  * Caesar.java
  * BIO.java

* Compile the Java files with `javac Caesar.java BIO.java`

* Run the Caesar Cipher program

* Program will ask for:
  * Shift value (e.g., 3)
  * Plain text

<img width="525" height="135" alt="06 test_caesar" src="https://github.com/user-attachments/assets/778aefb4-5b1f-43c8-9afe-877dc4099c47" />


### What Caesar Cipher does

* Shifts letters by a fixed number
* Simple but not secure
* Used for learning encryption basics

* 2. DES Algorithm

* Download EncryptDecryptDES Java file

* Create input text file with `nano Text.txt`

<img width="1366" height="768" alt="07 create_text_file" src="https://github.com/user-attachments/assets/882b3ce5-3c26-4ace-817f-8494b9fac7f0" />

* Save and exit

* Compile the Java program with `javac EncryptDecryptDES.java`

* Run the DES program with `java EncryptDecryptDES`

  <img width="540" height="42" alt="08 compile_run" src="https://github.com/user-attachments/assets/976e74f0-66cf-48b3-9405-a7091fd5ffea" />


* Outputs files

  * Encrypted.dat
  * Decrypted.txt

* Encrypted.dat
 
  * Binary encrypted data
  * Looks unreadable
  * You can try: `cat Encrypted.dat`
 
<img width="485" height="43" alt="09 encrypted_file" src="https://github.com/user-attachments/assets/fd60c647-2867-445b-b1f6-13adcf21e283" />


* Decrypted.txt

  * This is the decrypted output.
  * Check it: `cat Decrypted.txt`
  * Output `Matches original text` -> `This is secret text`

<img width="427" height="45" alt="10 decrypted_file" src="https://github.com/user-attachments/assets/2d8879ad-9211-446b-b638-6aa09ee55afb" />

