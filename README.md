# 🔍 Python TCP Port Scanner

A fast, multi-threaded TCP port scanner written in Python.
This tool scans a target host for open ports and identifies common services running on them.

---

## 🚀 Features

* ⚡ Multi-threaded scanning for high performance
* 🎯 Custom port range scanning
* ⏱️ Configurable timeout
* 🧠 Service detection (e.g., HTTP, SSH, HTTPS)
* 🖥️ Command-line interface (CLI) using argparse
* 🛡️ Error handling and input validation

---

## 📦 Requirements

* Python

---

## ▶️ Usage

```bash
py scanner.py <target> [options]
```

### 🔹 Example

```bash
py scanner.py 127.0.0.1 --start 1 --end 1000 --threads 50
```

---

## ⚙️ Arguments

| Argument  | Description              | Default  |
| --------- | ------------------------ | -------- |
| target    | Target IP or hostname    | required |
| --start   | Starting port            | 1        |
| --end     | Ending port              | 1024     |
| --timeout | Socket timeout (seconds) | 0.5      |
| --threads | Number of threads        | 50       |

---

## 🧠 How It Works

1. The user provides a target and port range.
2. The hostname is resolved into an IP address.
3. A queue is created containing all ports to scan.
4. Multiple threads are launched to scan ports concurrently.
5. Each thread:

   * Retrieves a port from the queue
   * Attempts a TCP connection
   * Marks the port as open if successful
6. Open ports are collected and displayed to the user.

---

## 📊 Sample Output

```text
Scanning 127.0.0.1 (127.0.0.1) from port 1 to 1000 using 50 threads...

Scan complete in 0.42s
Open ports found: 3

22/tcp open (ssh)
80/tcp open (http)
443/tcp open (https)
```

---

## ⚠️ Disclaimer

This project is for educational purposes only.
Only scan systems you own or have explicit permission to test.

---

## 🛠️ Future Improvements

* Banner grabbing (detect service versions)
* UDP scanning
* Export results to JSON/CSV
* Progress bar
* Web interface (dashboard)

---

## 👨‍💻 Author
Charalampos Kounnapis
