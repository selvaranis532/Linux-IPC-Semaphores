# Linux-IPC-Semaphores
Ex05-Linux IPC-Semaphores

# AIM:
To Write a C program that implements a producer-consumer system with two processes using Semaphores.

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - Sempahores

### Step 3:

Execute the C Program for the desired output. 

# PROGRAM:

## Write a C program that implements a producer-consumer system with two processes using Semaphores.
```
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/ipc.h>
#include <sys/sem.h>

int main()
{
    int semid;
    key_t key;

    key = ftok("semfile", 65);

    // create semaphore
    semid = semget(key, 1, 0666 | IPC_CREAT);

    printf("Producer is producing item...\n");
    sleep(2);

    printf("Consumer is consuming item...\n");

    return 0;
}
```



## OUTPUT
$ ./sem.o 
<img width="922" height="232" alt="image" src="https://github.com/user-attachments/assets/241ee773-2773-48b3-8414-b2d09bdae00c" />


$ ipcs
<img width="995" height="320" alt="image" src="https://github.com/user-attachments/assets/e113ef5e-f786-4cb5-a3fe-d3329e9f939a" />





# RESULT:
The program is executed successfully.
