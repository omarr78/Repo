# Task 1 - understanding how one server and one clinet talk using sockets

## 1- Write simple socket server then compile and run the server

``` java
import java.net.*;
import java.io.*;
class SimpleSocketServer {
  public static void main(String args[])
    throws java.io.IOException {
    DataOutputStream out;
    InputStreamReader isr;
    System.out.println("Server running...");
    ServerSocket srvSocket= new ServerSocket(8421);
    Socket cliSocket = srvSocket.accept();
    out = new DataOutputStream(cliSocket.getOutputStream());
    out.writeUTF("Hello client, the connection with the Socket Server established, bye now!");
    srvSocket.close();
    cliSocket.close();
  }
}
```

<img width="963" height="101" alt="run_the_server" src="https://github.com/user-attachments/assets/425f42c7-06b1-4e83-af9b-06a68ef36745" />

> Now the server is blocked at accept() and waits for the client

## 2- Write the ONE-SHOT client then Compile and run the client

``` java
import java.io.*;
import java.net.*;

public class CliSocketReading{
  public static void main(String[] args) throws Exception{
    Socket cliSocket;
    DataInputStream is=null;
    String host="localhost";

    cliSocket = new Socket(host,8421);
    System.out.println(" Connection with the server established!");

    is = new DataInputStream(cliSocket.getInputStream());
    System.out.println(is.readUTF());
    cliSocket.close();
  }
}
```

* the client should connect to the server with ip address and port number
* client should read the message and then print it
* after that the client should exit


<img width="963" height="91" alt="02 run_simple_client" src="https://github.com/user-attachments/assets/22492156-43c5-4199-90cd-1baa9a1a3d16" />

* after that the Server terminal exits
* Connection is finished

> [!NOTE]
> Server must start first after that the Client connects second and the Communication happens once


---

## 3- Run the server in background & Find your ip address and trying to connect using it

### Run the server in the background

<img width="927" height="114" alt="Run_in_the_background" src="https://github.com/user-attachments/assets/5efe809d-a1a6-4b92-92b5-edac23137f39" />

### Then find the ip address using `ip addr`

<img width="1040" height="470" alt="04 find_ip_address" src="https://github.com/user-attachments/assets/58b6fcc6-594b-4b18-919d-18eb20b784d0" />

### Change `localhost` to ip address to simulate the remote communication

<img width="256" height="46" alt="05 change_localhost" src="https://github.com/user-attachments/assets/4c75991a-5784-4ca7-9c14-0978b5deacde" />

### when you test it, you should see that it works like before 

<img width="963" height="91" alt="02 run_simple_client" src="https://github.com/user-attachments/assets/22492156-43c5-4199-90cd-1baa9a1a3d16" />

---

## 4- Echo Server & Echo Client

### 1.Echo Server

### what is the Echo server

* Client sends message
* Server sends the same message back
* Can happen many times

### Server should does:

* Accept the client
* Reads a message from the client 
* Write the same message back
* Repeats (until client stops)

### EchoServer code (text)

``` java

import java.net.*;
import java.io.*;

public class EchoServer {
    public static void main(String[] args) throws java.io.IOException {
        try{
            System.out.println("Echo Server running...");
            
            ServerSocket srvSocket= new ServerSocket(8421);
            Socket cliSocket = srvSocket.accept();

            DataInputStream in = new DataInputStream(cliSocket.getInputStream());
            DataOutputStream out = new DataOutputStream(cliSocket.getOutputStream());

            while (true) {
                String clientMessage = in.readUTF();

                if(clientMessage.equals("exit")) {
                    out.writeUTF("Goodbye");
                    out.flush();
                    break;
                }

                System.out.println("Received from client: " + clientMessage);
                out.writeUTF("Echo -> " + clientMessage);
                out.flush();    
            }
            in.close();
            out.close();
            srvSocket.close();
            cliSocket.close();
        }catch(Exception e){
            System.out.println("Error: " + e.getMessage());
        }
    }
}

```
### EchoServer code (picture)

<img width="782" height="692" alt="08 server_code" src="https://github.com/user-attachments/assets/5fe69d55-99ee-4015-857d-d79b46e7475c" />


### 2.Echo Client

### what this client should do:

* Read input from keyboard
* Send to the server
* Read echoed reply
* Print it
* Repeat it until the input entered is `exit`

### EchoClient code (text)

``` java

import java.util.*;
import java.net.*;
import java.io.*;

public class EchoClient {
    public static void main(String[] args) throws java.io.IOException {
        try{
            Socket cliSocket = new Socket("localhost", 8421);

            DataInputStream in = new DataInputStream(cliSocket.getInputStream());
            DataOutputStream out = new DataOutputStream(cliSocket.getOutputStream());

            Scanner scanner = new Scanner(System.in);

            while (true) {
                System.out.print("Enter message to send to server (type 'exit' to quit): ");
                String userInput = scanner.nextLine();

                out.writeUTF(userInput);
                out.flush();

                String serverResponse = in.readUTF();
                System.out.println("Received from server: " + serverResponse);

                if (userInput.equals("exit")) {
                    break;
                }
            }
            in.close();
            out.close();
            cliSocket.close();
            scanner.close();
        }catch(Exception e){
            System.out.println("Error: " + e.getMessage());
        }
    }
}
```
### EchoClient code (picture)

<img width="829" height="711" alt="09 client_code" src="https://github.com/user-attachments/assets/2ad458be-1ba1-42d6-89fe-82ce6890a066" />















