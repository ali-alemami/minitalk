*This project has been created as part of the 42 curriculum by aalemami.*

# minitalk

---

## Description

minitalk is an inter-process communication project using UNIX signals. The goal is to transmit arbitrary strings from a client process to a server process by encoding each byte as eight individual signals (`SIGUSR1` representing bit 1, and `SIGUSR2` representing bit 0).

The server reconstructs characters bit-by-bit from the incoming signal stream and displays the complete message upon receiving the null terminator byte. The project demonstrates low-level POSIX signal handling, asynchronous execution, and signal safety.

---

## Instructions

### Compilation

Compile the client and server binaries using `make`:

```bash
make
```

Additional rules:
```bash
make clean   # Remove object files
make fclean  # Remove object files and binaries
make re      # Rebuild from scratch
```

### Execution

1. Start the server in one terminal:
   ```bash
   ./server
   ```
   The server prints its Process ID (PID) and awaits signals.

2. In a second terminal, send a message using the client:
   ```bash
   ./client <SERVER_PID> "Hello, 42!"
   ```

---

## Resources

- [signal(7) — Linux manual page](https://man7.org/linux/man-pages/man7/signal.7.html)
- [sigaction(2) — Linux manual page](https://man7.org/linux/man-pages/man2/sigaction.2.html)
- [kill(2) — Linux manual page](https://man7.org/linux/man-pages/man2/kill.2.html)

### AI Usage

AI tools were used for assistance in structuring and formatting this README documentation. The core project logic and signal handlers were implemented manually.
