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


























