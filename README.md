# Operating system Project: Secure Multi-threaded Chat Application

This repository contains a secure, multi-threaded chat application developed in C using named pipes (FIFOs) that enables multiple clients to communicate through a central server with robust synchronization mechanisms to prevent concurrency issues.

## Project Features

- **Named Pipe Communication**: Client-server architecture using FIFOs for inter-process communication.
- **Multi-threading Management**: Thread pool system for efficient handling of concurrent client connections.
- **Synchronization Mechanisms**: Semaphores and locks to prevent deadlocks and ensure thread-safe access.
- **Security Features**: Authentication system to prevent unauthorized access.
- **Concurrency Control**: Protection mechanisms against race conditions, deadlocks, and thread starvation.

## Requirements

- Linux operating system
- GCC compiler
- POSIX threads library (pthread)

## Installation

### Clone the repository:
```bash
git clone https://github.com/yourusername/secure-chat-app.git
```

### Compile the server:
```bash
gcc -o server server.c -lpthread
```

### Compile the client:
```bash
gcc -o client client.c -lpthread
```

## Usage

### Starting the Server

1. Open a terminal window and navigate to the project directory.
2. Run the server:
   ```bash
   ./server
   ```
3. The server will initialize and wait for client connections.

### Connecting Clients

1. Open a new terminal window for each client you want to connect.
2. Navigate to the project directory.
3. Run the client:
   ```bash
   ./client
   ```
4. The client will automatically connect to the server.
5. After successful authentication, you can start sending messages.

### Sending Messages

1. When prompted with `Enter message:`, type your message and press Enter.
2. Your message will be broadcast to all other connected clients.
3. Messages from other clients will be displayed automatically.

### Disconnecting

1. To disconnect from the server, type `exit` when prompted for a message.
2. The client will close the connection and terminate.

### Running Multiple Clients

You can run up to 10 concurrent clients (as defined by `MAX_CLIENTS` in the server code). For each new client:

1. Open a new terminal window.
2. Navigate to the project directory.
3. Run the client:
   ```bash
   ./client
   ```
4. Start communicating with other connected clients.

## Important Notes

- The server must be running before any clients attempt to connect.
- The system uses named pipes for communication, which will be created in the project directory.
- Authentication is handled via a token system (currently using "secret_token").
- The server can handle up to 10 concurrent clients by default.

## Troubleshooting

If you encounter any issues:

- Ensure the server is running before starting clients.
- Check that you have the necessary permissions to create pipes in the directory.
- If a client fails to connect, try running it again.
- If pipes persist after abnormal termination, manually remove them using: `rm *_pipe`.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

Created by Fadi Louise, 2024.
