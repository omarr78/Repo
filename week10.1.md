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


