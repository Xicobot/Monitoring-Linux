# Monitoring-Linux

1. Process
2. Memory Ram
3. Hard Disks
4. Network
---

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
