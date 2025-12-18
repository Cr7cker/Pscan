
# Port Scanner Pro

A lightweight, Python-based network utility designed to scan a target domain or IP address for open ports and identify their associated services.

## 🚀 Features

* **Full Port Range Scan:** Scans all 65,535 possible TCP ports.
* **Service Identification:** Automatically attempts to resolve the service name (e.g., HTTP, FTP, SSH) for each open port.
* **Colorized Output:** Uses `termcolor` for easy-to-read, status-based console output.
* **Cross-Platform:** Automatically handles screen clearing for both Windows and Linux/Unix systems.

---

## 🛠️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/Cr7cker/Pscan.git
cd port-scanner
```

### 2. Install Dependencies

This tool requires Python 3.x and the `termcolor` library. You can install the requirements using pip:

```bash
pip install termcolor

```

---

## 💻 Usage

To run the scanner, use the `-d` or `--domain` flag followed by the target IP address or domain name.

### Basic Syntax:

```bash
python pscan.py -d <TARGET_IP_OR_DOMAIN>

```

### Example:

```bash
python pscan.py -d 192.168.1.1

```

---

## ⚙️ How It Works

The script utilizes the `socket` library to attempt a connection to every port on the target machine:

1. **Socket Initialization:** Creates an `AF_INET` (IPv4) and `SOCK_STREAM` (TCP) socket.
2. **Timeout:** Sets a 1-second timeout per port to ensure the scan moves efficiently.
3. **Connection Check:** Uses `connect_ex()`, which returns `0` if the port is open and an error code if it is closed or filtered.
4. **Service Lookup:** If a port is open, `socket.getservbyport()` fetches the standard service name associated with that port number.

---

## ⚠️ Disclaimer

**Educational purposes only.** This tool is intended for legal security testing and network administration. Scanning targets without explicit permission is illegal and unethical. Use responsibly.

---

## 👤 Credits

* **Author:** Cr7cker
* **Language:** Python

---

Would you like me to add a **Requirements.txt** file or suggest a way to make the scan faster using multi-threading?
