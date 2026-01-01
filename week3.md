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

### 4. Run the server on other machine and run the client your machine

### Use `192.168.1.10` instead of `localhost` in HelloClient.java

<img width="359" height="86" alt="06 localhost" src="https://github.com/user-attachments/assets/13c71f7c-4e91-4bf1-8a86-531f5546e456" />

### Since `System.setSecurityManager(new RMISecurityManager());` is deprecated 

### The modern approach is to use a policy file without ever calling `System.setSecurityManager`

### Create server.policy & client.policy

<img width="413" height="91" alt="07 client policy" src="https://github.com/user-attachments/assets/5fc8d58e-d08c-47e6-93d5-0699873ba927" />

### Then run your server

<img width="1131" height="164" alt="08 run_policy_server" src="https://github.com/user-attachments/assets/8d4ab305-9d30-41d5-8da6-a0df90c847e5" />

### and run the client on another machine

<img width="1129" height="96" alt="09 run_policy_client" src="https://github.com/user-attachments/assets/49a32401-0404-41cc-91f2-7c92c7b4d5af" />

---

## Task 2 - passing parameter when calling method over the network and returning a custom response

- instead of only `sayHello()`
- you add `sayHelloTo(String name)`

### 1. Update HelloInterface.java to make the method accept name parameter

``` java
//    public String sayHello() throws java.rmi.RemoteException;
    public String sayHello(String name) throws java.rmi.RemoteException;
```

<img width="661" height="104" alt="10 update_Hello_Interface" src="https://github.com/user-attachments/assets/126299fb-81bf-42ab-9c7c-90746d17df36" />

### 2. Update HelloServer.java to make the method accept name parameter

``` java
//    public static final String MESSAGE = "Hello World";
    public static final String MESSAGE = "The Server says hello to";

//    @Override
//    public String sayHello(String name) throws RemoteException {
//        return MESSAGE;
//    }

    @Override
    public String sayHello(String name) throws RemoteException {
        return MESSAGE + " " + name;
    }
```

<img width="637" height="233" alt="11 update_Hello_Server" src="https://github.com/user-attachments/assets/fbcd2c2a-f81c-43c9-8dbe-9c3ca82371fe" />

### 3. Update HelloClient.java to pass the name as an argument in method

``` java
//            String message = stub.sayHello();
            String message = stub.sayHello("Omnia");
```

<img width="456" height="41" alt="12 update_Hello_Client" src="https://github.com/user-attachments/assets/72419764-3cde-48dd-ad75-0f63de2b6b9f" />

### 4. Run the server

<img width="755" height="136" alt="04 RMI_server" src="https://github.com/user-attachments/assets/12630b25-f62d-45b2-817a-5a194aca3589" />

### 5. Run the client

<img width="759" height="96" alt="13 client_sends_name" src="https://github.com/user-attachments/assets/ccfa94fb-7e15-454e-ae80-d1a6f6ef534e" />











