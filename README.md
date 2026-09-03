# Python Socket Chat

A simple real-time chat application built with Python using TCP sockets, multithreading, and Tkinter.

## About the Project

I originally built this project during my 11th grade as a personal experiment and out of curiosity about computer networking and how applications communicate with each other.

At the time, I was exploring programming for fun and wanted to understand how a basic client-server communication system could be built from scratch.

I am publishing the project now during my BTech to document one of my earlier programming experiments and preserve the work I did while exploring computer science before formally studying it at university.

The application runs in a local environment and allows multiple client windows to connect to a Python server and exchange messages.

## Features

* TCP socket-based communication
* Client-server architecture
* Multiple client connections
* Real-time message broadcasting
* Username-based chat messages
* Multithreading for handling multiple clients
* Simple graphical interface using Tkinter
* Runs locally without external libraries

## Technologies Used

* Python
* TCP/IP Sockets
* Socket Programming
* Multithreading
* Tkinter
* Client-Server Architecture

## Project Structure

```text
python-socket-chat/
│
├── client.py       # Graphical chat client
├── server.py       # Chat server
├── README.md
└── .gitignore
```

## How It Works

The project follows a basic client-server architecture.

```text
              Client 1
            Tkinter GUI
                 │
                 │ TCP
                 ▼
          ┌───────────────┐
          │    Server     │
          │ 127.0.0.1:3108│
          └───────┬───────┘
                  │
              ┌───┴───┐
              │       │
             TCP     TCP
              │       │
              ▼       ▼
          Client 2  Client 3
```

### 1. Server

`server.py` creates a TCP socket and binds it to:

```text
127.0.0.1:3108
```

The server listens for incoming client connections.

When a client connects, the server creates a separate thread to handle that client.

### 2. Client

`client.py` provides a graphical interface using Tkinter.

The user enters a username and connects to the server.

The client then starts a separate thread to listen for incoming messages while the GUI remains available for user interaction.

### 3. Sending Messages

When a client sends a message, the server receives it and associates it with the client's username.

The server formats the message approximately as:

```text
username~message
```

The server then broadcasts the message to all currently connected clients.

For example:

```text
Alice~Hello everyone!
```

is displayed by the clients as:

```text
[Alice] Hello everyone!
```

## Running the Project

### Requirements

Python 3 is required.

The project uses Python's standard library, so no external packages need to be installed.

### Step 1: Start the Server

Open a terminal in the project directory and run:

```bash
python server.py
```

You should see:

```text
Running the server on 127.0.0.1 3108
```

### Step 2: Start a Client

Open another terminal in the same directory:

```bash
python client.py
```

A graphical chat window will open.

Enter a username and click **Join**.

### Step 3: Start Additional Clients

To test communication between multiple users, open additional terminals and run:

```bash
python client.py
```

Use a different username for each client.

Messages sent from one client will be broadcast through the server to the connected clients.

## Local Environment

The application is currently configured to use:

```text
Host: 127.0.0.1
Port: 3108
```

`127.0.0.1` refers to the local computer (localhost).

Therefore, the project is intended primarily as a local demonstration of socket-based client-server communication.

It is not designed as a production internet messaging application.

## What I Learned

This project was an early experiment that helped me explore several fundamental computer science concepts:

* How client-server architecture works
* TCP socket communication
* IP addresses and ports
* Sending and receiving data through sockets
* Handling multiple clients
* Basic multithreading
* Building a simple GUI with Tkinter
* How messages can be routed through a central server

## Limitations

This is an early learning project rather than a production-ready messaging system.

Some limitations include:

* Communication is configured for localhost.
* There is no authentication system.
* Messages are not stored in a database.
* There is no encryption.
* There is no persistent chat history.
* The server does not implement a sophisticated client-disconnection mechanism.
* The protocol is intentionally simple.

These limitations reflect the project's original purpose as a learning experiment.

## Future Improvements

Possible improvements include:

* Support for LAN-based communication
* User authentication
* Better client connection/disconnection handling
* Message timestamps
* Persistent chat history
* Database integration
* Encrypted communication
* Improved GUI
* Private messaging
* Online/offline user status

## Project Background

This project was originally created during my 11th grade as a personal experiment.

I was curious about programming and computer science and wanted to understand how computers could communicate with each other using code.

Although this is an older project, I am publishing it now during my BTech as part of documenting my learning journey and the projects I experimented with before and during university.

---

**Status:** Completed learning project / archived experiment

**Original development:** 11th grade

**Published to GitHub:** 2026
