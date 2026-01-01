# Java RMI (Remote Method Invocation)

### what the RMI

* RMI lets one java program call a method that runs on another computer as if it a normal local method
* calling a method in a different program, possibly on a different machine

---

## Task 1

### 1. create the files

* HelloInterface.java
* HelloServer.java
* HelloClient.java

### HelloInterface.java (code)

``` java
import java.rmi.Remote;

public interface HelloInterface extends Remote {
    public String sayHello() throws java.rmi.RemoteException;
}
```
### HelloInterface.java (picture)

<img width="563" height="119" alt="01 Hello_interface" src="https://github.com/user-attachments/assets/cf79a6df-5382-4a99-9e17-46d909e5e250" />


### HelloService.java (code)

``` java
import java.rmi.Naming;
import java.rmi.RemoteException;
import java.rmi.registry.LocateRegistry;
import java.rmi.registry.Registry;
import java.rmi.server.UnicastRemoteObject;

public class HelloServer implements HelloInterface {
    public static final String MESSAGE = "Hello World";

    // No args constructor
    public HelloServer() {
    }

    @Override
    public String sayHello() throws RemoteException {
        return MESSAGE;
    }

    public static void main(String[] args) {
        System.out.println("RMI Hello Server started");
        // Create the server object
        try {
            HelloInterface server = new HelloServer();

            // stub is a fake object that given to the client and forwards calls to the real server
            HelloInterface stub = (HelloInterface) UnicastRemoteObject.exportObject(server, 0);
            System.out.println("Stub created and object exported");

            // create Registry on make it listen on port 1099
            Registry registry = LocateRegistry.createRegistry(1099);
            System.out.println("Registry created");

            // this looks for Registry on localhost:1099
            // and register "HelloInterface" to stub
            Naming.bind("HelloInterface", stub);
            System.out.println("Hello Server is bound and ready to receive requests.");
        } catch (final Exception e) {
            System.out.println("HelloServer failed: " + e);
        }
    }
}

```
### HelloService.java (picture)

<img width="894" height="806" alt="02 HelloService" src="https://github.com/user-attachments/assets/eac0aaa3-e831-43bc-9f2f-81e73db4364f" />

### HelloClient.java (code)

``` java
import java.rmi.registry.LocateRegistry;
import java.rmi.registry.Registry;

public class HelloClient {
    public static void main(String[] args) {
        String host = "localhost";

        try {
            Registry registry = LocateRegistry.getRegistry(host);
            HelloInterface stub = (HelloInterface) registry.lookup("HelloInterface");

            String message = stub.sayHello();
            System.out.println("Response from RMI server: " + message);
        } catch (Exception e) {
            System.out.println("Exception in main: " + e);
        }
    }
}
```
### HelloClient.java (picture)

<img width="772" height="371" alt="03 HelloClient" src="https://github.com/user-attachments/assets/58786191-ae44-47c2-b7a8-b4c3e317d970" />

---

### 2. Open Terminal and compile the Java files using the javac compiler and start the server: java HelloServer

<img width="755" height="136" alt="04 RMI_server" src="https://github.com/user-attachments/assets/bfb23ee5-6ef1-4bfb-b93b-e2c40fb63db0" />

### 3. Run your client program that will invoke the remote method

<img width="757" height="97" alt="05 RMI_client" src="https://github.com/user-attachments/assets/49db7e55-7b00-4a9b-a8e4-e75963402f49" />



