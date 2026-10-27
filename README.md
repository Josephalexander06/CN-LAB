# Computer Networks Laboratory (CN-LAB)

Structured Java implementations for Computer Networks Laboratory experiments without comments, formatted for clean execution.

---

## Repository Structure

```
CN-LAB/
├── Experiment-01-UDP-Client-Server/
│   ├── UDPServer.java
│   └── UDPClient.java
├── Experiment-02-Concurrent-UDP-Time-Server/
│   ├── TimeServer.java
│   └── TimeClient.java
├── Experiment-03-Multi-User-Chat-Server-TCP/
│   ├── ChatServer.java
│   └── ChatClient.java
├── Experiment-04-Concurrent-File-Server-TCP/
│   ├── FileServer.java
│   └── FileClient.java
└── Experiment-05-Matrix-Classification-TCP/
    ├── Server.java
    └── Client.java
```

---

## Experiments Overview & Sample Outputs

### 1. Experiment 01: UDP Client-Server Program
- **Description:** A UDP client sends a sentence to the server. The server expands common chat abbreviations (e.g., `tbh` -> `to be honest`, `idk` -> `I don't know`) and replies to the client.
- **Port:** `9876`
- **Execution:**
  ```bash
  cd Experiment-01-UDP-Client-Server
  javac UDPServer.java UDPClient.java
  java UDPServer    # In Terminal 1
  java UDPClient    # In Terminal 2
  ```
- **Sample Output:**
  - **Server Terminal:**
    ```text
    Server Started...
    Received: tbh idk what to do rn
    Translation Sent.
    ```
  - **Client Terminal:**
    ```text
    Enter a sentence: tbh idk what to do rn

    Translated Sentence:
    to be honest I don't know what to do at the moment
    ```

---

### 2. Experiment 02: Concurrent UDP Time Server
- **Description:** A concurrent UDP time server using multithreading (`RequestHandler`). Handles multiple client requests simultaneously and sends the current server date and time.
- **Port:** `9876`
- **Execution:**
  ```bash
  cd Experiment-02-Concurrent-UDP-Time-Server
  javac TimeServer.java TimeClient.java
  java TimeServer   # In Terminal 1
  java TimeClient   # In Terminal 2
  ```
- **Sample Output:**
  - **Server Terminal:**
    ```text
    Concurrent UDP Time Server Started...
    Request received from /127.0.0.1:52344
    Time sent to /127.0.0.1:52344 -> Tue Sep 22 11:04:37 IST 2026
    Request received from /127.0.0.1:52350
    Time sent to /127.0.0.1:52350 -> Tue Sep 22 11:04:41 IST 2026
    ```
  - **Client 1 Terminal:**
    ```text
    Enter server IP address: 127.0.0.1
    Enter server port number: 9876
    Time received from server: Tue Sep 22 11:04:37 IST 2026
    ```
  - **Client 2 Terminal:**
    ```text
    Enter server IP address: 127.0.0.1
    Enter server port number: 9876
    Time received from server: Tue Sep 22 11:04:41 IST 2026
    ```

---

### 3. Experiment 03: Multi-User Chat Server (TCP)
- **Description:** A multi-client chat server using TCP and multithreading (`ClientHandler`). Clients join by entering a username and broadcast messages to all connected participants in real time.
- **Port:** `5000`
- **Execution:**
  ```bash
  cd Experiment-03-Multi-User-Chat-Server-TCP
  javac ChatServer.java ChatClient.java
  java ChatServer   # In Terminal 1
  java ChatClient   # In Terminal 2
  java ChatClient   # In Terminal 3 (additional client)
  ```
- **Sample Output:**
  - **Server Terminal:**
    ```text
    Chat Server Started...
    New client connected
    New client connected
    ```
  - **Client 1 (Alice):**
    ```text
    Enter your name: Alice
    Bob joined the chat
    Bob: Hello Alice
    ```
  - **Client 2 (Bob):**
    ```text
    Enter your name: Bob
    Alice: Hi Bob
    ```

---

### 4. Experiment 04: Concurrent File Server (TCP)
- **Description:** A concurrent TCP file server that accepts file name requests from clients, verifies file existence, reports server Process ID (PID), and streams file contents line by line.
- **Port:** `6000`
- **Execution:**
  ```bash
  cd Experiment-04-Concurrent-File-Server-TCP
  javac FileServer.java FileClient.java
  java FileServer   # In Terminal 1
  java FileClient   # In Terminal 2
  ```
- **Sample Output:**
  - **Server Terminal:**
    ```text
    Concurrent File Server Started on port 6000 (PID: 8421)
    New client connected: /127.0.0.1
    Requested file: notes.txt from /127.0.0.1
    New client connected: /127.0.0.1
    Requested file: missing.txt from /127.0.0.1
    ```
  - **Client 1 (File exists):**
    ```text
    Enter server IP address: 127.0.0.1
    Enter server port number: 6000
    Enter the name of the file to request: notes.txt

    Response from server (PID:8421)
    ----- File Contents -----
    Computer Networks Lab
    Concurrent programming using sockets and threads.
    ```
  - **Client 2 (File does not exist):**
    ```text
    Enter server IP address: 127.0.0.1
    Enter server port number: 6000
    Enter the name of the file to request: missing.txt

    Response from server (PID:8421)
    Requested file "missing.txt" does not exist on the server.
    ```

---

### 5. Experiment 05: TCP Matrix Type Identification (Program No. 6)
- **Description:** A TCP client inputs order $N$, generates a random square matrix of order $N$, assigns a structure (Upper Triangular, Lower Triangular, Diagonal, or Normal), and sends it to the server. The server determines the matrix category and returns the result.
- **Port:** `9002`
- **Execution:**
  ```bash
  cd Experiment-05-Matrix-Classification-TCP
  javac Server.java Client.java
  java Server       # In Terminal 1
  java Client       # In Terminal 2
  ```
- **Sample Output:**
  - **Server Terminal:**
    ```text
    Server waiting for connection...
    Client Connected.

    Received Matrix:
    15 0 0 
    23 42 0 
    11 8 39 

    Matrix Type : Lower Triangular Matrix
    ```
  - **Client Terminal:**
    ```text
    Enter order of matrix : 3

    Generated Matrix
    15 0 0 
    23 42 0 
    11 8 39 

    Matrix Type : Lower Triangular Matrix
    ```
