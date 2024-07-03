# Network Recon Script

This script automates the process of checking the installation of necessary tools, verifying the anonymity of the local server, and performing network reconnaissance tasks on a remote server.

## Features

- **Log File Creation**: Checks if a log file exists; if not, creates one.
- **Tool Installation Check**: Verifies if `tor`, `sshpass`, and `nipe` are installed; installs them if not.
- **IP Anonymity Check**: Determines the country of the current IP address and verifies anonymity.
- **Remote Server Connection**: SSH into a remote server if the local server is spoofed.
- **Nmap Scan**: Performs an Nmap scan on the remote server to check for open ports.
- **Whois Scan**: Executes a Whois scan on a target domain or IP on the remote server.
- **File Transfer**: Retrieves the saved Whois scan file from the remote server via FTP.
- **Activity Logging**: Logs the date and time of the Whois data collection in a log file.

## Prerequisites

- **tor**
- **sshpass**
- **nipe**
- **nmap**
- **whois**

Ensure these tools are installed on your system.

## Usage

1. Save the script to a file, e.g., `network_recon.sh`.
2. Make the script executable:
    ```bash
    chmod +x network_recon.sh
    ```
3. Run the script:
    ```bash
    ./network_recon.sh
    ```

## Script Workflow

1. **Log File Creation**:
    - Checks if `nr.log` exists in the current directory. If not, it creates the log file.

2. **Tool Installation Check**:
    - Verifies the installation of `tor`, `sshpass`, and `nipe`. If any tool is not installed, the script installs it.

3. **IP Anonymity Check**:
    - Retrieves the current IP address and checks its country. If the IP address is from Singapore (SG), the script exits.

4. **Remote Server Connection**:
    - Prompts the user for the remote server's IP, user, password, and the target domain/IP for the Whois scan.
    - Performs an Nmap scan on the remote server to check for open ports.
    - SSH into the remote server and performs a Whois scan on the target domain/IP.
    - Retrieves the Whois scan file from the remote server via FTP.

5. **Activity Logging**:
    - Logs the date and time of the Whois data collection in `nr.log`.
