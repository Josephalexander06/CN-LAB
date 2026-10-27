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

## Experiments Overview

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
