# ProcessManagement Programs

This file includes all source files from the ZIP archive as-is for GitHub display.

## `execvefunction.c`

```c
#include<stdio.h>
#include<unistd.h>

int main()
{
	char *argv[] = {"/bin/ls","-l","NULL"};
	char *envp[] = {NULL};
	execve("/bin/ls",argv,envp);
return 1;
}
```

## `forkcreation.c`

```c
#include<stdio.h>
#include<unistd.h>

int main()
{
	pid_t pid = fork();

	if( pid < 0)
	{
		perror("Fork Failed");
	}
	else if( pid == 0)
	{
		printf("Child Process. PID: %d \n",getpid());
	}
	else
	{
		printf("Parent Process . PID : %d ,Child Process PID %d\n", getpid(),pid);
	}
	return 0;
}
```

## `multiplechild.c`

```c
#include<stdio.h>
#include<unistd.h>
int main()
{
	for(int i=0; i < 3; i++)
	{
	pid_t pid = fork();
	if(pid == 0)
	{
		printf("Child Process %d PID  %d : \n",i+1,getpid());
		return 0;
	}
	}
return 0;
}
```

## `useofexecvpfunction.c`

```c
#include<stdio.h>
#include<unistd.h>

int main()
{
	char *args[] = {"ls","-l",NULL};
	execvp("ls",args);
// This line execute when execvp fails	

	perror("Execvp() Function failed");
	return 1;
}
```

