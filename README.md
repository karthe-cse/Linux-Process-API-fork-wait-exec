# Linux-Process-API-fork-wait-exec-
Ex02-Linux Process API-fork(), wait(), exec()
# Ex02-OS-Linux-Process API - fork(), wait(), exec()
Operating systems Lab exercise


# AIM:
To write C Program that uses Linux Process API - fork(), wait(), exec()

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - fork(), wait(), exec()

### Step 3:

Test the C Program for the desired output. 

# PROGRAM:

## C Program to create new process using Linux API system calls fork() and getpid() , getppid() and to print process ID and parent Process ID using Linux API system calls

```
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>   

int main() {
    int pid;

    pid = fork();

    if (pid == 0) {
        printf("I am child, my pid is %d\n", getpid());
        printf("My parent pid %d\n", getppid());
    } else {
        printf("I am parent, my pid is %d\n", getpid());
    }

    sleep(100);
    return 0;
}
```











##OUTPUT

<img width="462" height="196" alt="Screenshot 2026-08-18 184837" src="https://github.com/user-attachments/assets/4eeea103-21d4-411c-8a7c-e93cdde75a0d" />









## C Program to execute Linux system commands using Linux API system calls exec() , exit() , wait() family

```

#include <stdio.h>
#include <unistd.h>
#include <sys/wait.h>
#include <stdlib.h>

int main()
{
    pid_t pid = fork();

    if (pid == 0)
    {
        printf("Child process executing ls command\n");
        execlp("ls", "ls", NULL);
        perror("Exec failed");
        exit(1);
    }
    else
    {
        wait(NULL);
        printf("Parent process: Child execution completed\n");
    }

    return 0;
}
```






















##OUTPUT

<img width="889" height="233" alt="Screenshot 2026-08-18 185927" src="https://github.com/user-attachments/assets/7e0b03dc-ed65-4604-8067-ccf097d63a50" />

















# RESULT:
The programs are executed successfully.
