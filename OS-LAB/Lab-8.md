# Linux Process Management Cheat Sheet

## Process

### Foreground Process
- A process that requires a user to start them and interact with them.

### Background Process
- A process that runs in the background without user interaction.

## Process Attributes

- **UID (User ID):** User ID of the user who started the process.
- **PID (Process ID):** Process ID.
- **PPID (Parent Process ID):** Parent Process ID.
- **TTY (Terminal):** Terminal associated with the process.
- **CMD (Command):** Command that started the process.
- **STIME (Start Time):** Start time of the process.
- **TIME (Total Time):** Total time the process has been running.
- **C (CPU Utilization):** CPU utilization of the process.

## Managing Processes

- **`pwd &`:** Run a command in the background.
- **`ps`:** List all the processes.
    - **`ps 1234`:** List the process with the given PID.
    - **`ps -f`:** List all the processes with full details.
    - **`ps -A` or `ps -e`:** List all the processes with extended information.
    - **`ps -x`:** List all the processes for the current user.
    - **`ps -fU myUser`:** List all the processes for a given user.
    - **`ps -fG myGroup`:** List all the processes for a given group.
- **`kill 1234`:** Kill the process with the given PID.

## Linux Scheduler

### 1. Preemptive Scheduler
- A scheduler that can interrupt a process and allocate the CPU to another process.

### 2. Non-Preemptive Scheduler
- A scheduler that cannot interrupt a process and allocate the CPU to another process.

## Short Job First (SJF) - Script Example

```bash
#!/bin/bash

read -p "Enter Processes: " -a Processes
read -p "Enter Burst Times: " -a BurstTimes

for (( i=0; i<${#Processes[@]}; i++ )); do
    for (( j=((i+1)); j<${#Processes[@]}; j++ )); do
        if [[ ${BurstTimes[i]} -gt ${BurstTimes[j]} ]]; then
            temp=${BurstTimes[i]}
            BurstTimes[i]=${BurstTimes[j]}
            BurstTimes[j]=$temp
        fi
    done
done

echo "Processes: ${Processes[@]}"
echo "Burst Times: ${BurstTimes[@]}"
