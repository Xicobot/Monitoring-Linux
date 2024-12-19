# Concept map

## Process System

### **PS (Process System)**
This tool is used to display information about active processes in the system. It can show both system-level and user-level processes.

#### **Concepts:**
- **USER:** User who started the process.
- **PID:** Process identification number.
- **%CPU:** Percentage of CPU usage by the process.
- **%MEM:** Percentage of memory usage by the process.
- **TTY:** Terminal where the process is running.
- **STAT:** Status of the process:
  - **S (Sleeping):** Currently inactive.
  - **R (Running):** Currently executing.
  - **T (Stopped):** Process is stopped.
- **START:** Time when the process started.
- **TIME:** Total CPU time consumed by the process since it started.

#### **Examples:**
- `ps u -C nano`:
  - Displays user-specific processes filtering for the `nano` text editor.
  
- `ps -er user,pid,%cpu,%mem,time --sort=%cpu | head -n 6`:
  - Shows processes sorted by CPU usage in descending order.
  - Displays only the first six entries.

- `ps aux`:
  - Lists all processes, including those running in the background (TTY shown as `?`).

### **TOP**
An interactive tool to monitor system processes in real-time. It displays a header with system-wide statistics such as overall CPU usage, memory usage, and the number of processes.

#### **Shortcuts:**
- `Ctrl + M`: Sort by memory usage.
- `Ctrl + P`: Sort by CPU usage.
- `Ctrl + P`: Sort by PID.
- `Q`: Exit the program.

#### **Batch Mode:**
- `top -b -o %CPU -n 3 | head -n 17 > 10procesos.txt`
  - Runs `top` in batch mode, sorting processes by CPU usage, and saves the first 17 lines to a file.

### **HTOP**
A more visual and user-friendly version of `top`. It offers an interactive interface to manage processes.

#### **Shortcuts:**
- `F1`: Open help documentation.
- `F2`: Setup and edit configuration.
- `F3`: Search for a process.
- `F4`: Apply filters (e.g., by CPU or memory usage).
- `F5`: View processes in a tree structure.
- `F6`: Sort by specific criteria.
- `F7/F8`: Adjust process priority (nice value).
- `F9`: Kill a process.

### **ATOP**
Another visual tool for monitoring processes and system performance. Configurations can be customized by editing `/etc/default/atop`. Restart the service with:
- `systemctl restart atop`

---

## Memory

### **FREE**
This command displays memory usage in the system, including total, used, and available memory.

#### **Examples:**
- `free`:
  - Shows memory usage in bytes.
- `free -h`:
  - Displays memory in human-readable format (e.g., MB, GB).
- `free -s 3`:
  - Updates memory usage every 3 seconds.

---

## Hard Disks

### **DF (Disk Free)**
Displays the amount of used and available disk space for all mounted filesystems.

#### **Examples:**
- `df`:
  - Outputs disk usage in KB.
- `df -h`:
  - Displays disk usage in a human-readable format (e.g., MB, GB).

### **DU (Disk Usage)**
Analyzes disk space usage of directories and files.

#### **Examples:**
- `du -hs /<directory>`:
  - Summarizes the total space used by a specific directory.
  - `-h`: Formats output in human-readable sizes.
  - `-s`: Displays only the summary without listing every file.

### **IOSTAT**
Provides statistics on CPU usage, disk I/O, and partitions.

#### **Examples:**
- `iostat -mh`:
  - Outputs statistics in MB/GB format.
- `iostat -xh <device>`:
  - Shows detailed statistics for a specific device.
- `iostat -s <number>`:
  - Limits the number of columns displayed.

---

## Network

### **TCPDUMP**
A command-line packet analyzer for monitoring network traffic. It captures and displays data packets being transmitted or received over a network interface.

#### **Examples:**
- `tcpdump -i <adapter>`:
  - Captures traffic for a specific network adapter.
- `tcpdump -w <file>`:
  - Saves captured traffic to a file.
- `tcpdump -r <file>`:
  - Reads and analyzes a saved capture file.
- `tcpdump | grep -w "<keyword>"`:
  - Filters output for specific keywords.

### **TCPTRACK**
A real-time monitoring tool that tracks active network connections.

#### **Example:**
- `tcptrack -i <adapter>`:
  - Displays established connections on a specified network adapter.

### **IPTRAF**
A graphical tool to monitor network traffic in real-time.

#### **Steps:**
1. Run `iptraf` in the terminal.
2. Select "IP traffic monitor."
3. Choose the desired Ethernet interface.
4. Observe network traffic statistics.

### **BMON**
A bandwidth monitoring tool with graphical representations of network flow and usage.

#### **Installation:**
- `apt update && apt install bmon`

#### **Usage:**
- Run `bmon` to see real-time network traffic and bandwidth graphs.

# Monitoring Systems

## Grafana
- **Purpose:** Data visualization platform.
- **Features:**
  - Customizable dashboards.
  - Integrates with tools like Prometheus and Zabbix.
  - Alerting system for performance thresholds.

---

## Nagios
- **Purpose:** Open-source monitoring for hosts, services, and networks.
- **Features:**
  - Tracks system metrics and service health.
  - Sends notifications via email/SMS.
  - Scalable with plugins for additional capabilities.

---

## Zabbix
- **Purpose:** Advanced monitoring solution.
- **Features:**
  - Collects performance data from multiple sources.
  - Custom alerts and notifications.
  - Detailed reports and trend analysis.

---

## Prometheus
- **Purpose:** Monitoring and alerting for dynamic environments.
- **Features:**
  - Time series data storage for detailed analysis.
  - Powerful PromQL query language.
  - Integrated alerting and efficient local storage.

---

## Relationships
- Grafana integrates with Prometheus and Zabbix for visualization.
- Prometheus focuses on dynamic environments, complementing Grafana.
- Zabbix and Nagios handle comprehensive infrastructure monitoring.


---

Thank you very much for visiting this document. If you notice anything I might have missed, feel free to contact me. Thank you!


[Previews page](doc.md) --- [Next page](Monitorizacion_clases_Xicobot.pdf)
