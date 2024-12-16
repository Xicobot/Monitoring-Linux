1. Process
2. Memory Ram
3. Hard Disks
4. Network

### 1. Process
```
ps <aux>
ps <aux -S>
ps <aux -T>
ps <u -C "ProcessName">
ps <-eo user,pid,%cpu,%mem,time --sort=%$cpu | head -n 6>
top ( control + m = order by memory, control + p = order by cpu, EXIT = q )
htop
atop (It has his own file, /etc/default/atop)
```
Concepts:
In process, we need to know some concepts that maybe we can see it in the shell and dont know what it means:
1. USER: User who started the process.
2. PID: Process identification.
3. %CPU: CPU Usage.
4. %MEM: Memory Usage.
5. TTY: Terminal that is running that process.
6. STAT: Status of the process.
   a. Sleeping (S): Currently unactive.
   b. Running (R): Currently running.
   c. Stopped (T): Indicates a stopped process.
8. START: Time it has started the process.
9. TIME: Time it has been running since started.




ps a (It shows a page that shows all the process generated manually by the user.)



### 2. Memory Ram

```
free <-h, -s 3>
```

### 3. Hard disks
```
df -h <Directory>
du <-hs> <Directory>
iostat <-m, -h, -x> <Hard Disk Device>
iostat <-3> <Hard Disk Device>
iostat <-s, -x 1> <Hard Disk Device>
```
### 4. Network
```
tcpdump <-i> <Ethernet> <-w> <"Recording File Name">
tcpdump <-r> <"File Name Recorded"> | grep -w <"Service name of the output">
tcptrack <-i> <Ethernet>
iptraf (Graphical interface)
bmon (Another graphical interface)
