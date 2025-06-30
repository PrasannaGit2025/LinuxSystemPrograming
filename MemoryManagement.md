## `bestfitmemoryallocation.c`

```c
#include<stdio.h>
#define SIZE 5
int main()
{
	int blocks[SIZE] = {200,123, 211,454,224};
	int best = -1;
	int process = 212;
	for( int i = 0 ; i < SIZE; i++)
	{
		if (blocks[i] >= process)
		{
			if( best == -1 || blocks[i] < blocks[best])
			best = i;
		}
	}
	if(best != -1)
	{
		printf("Process Allocation In Block %d",best);
		blocks[best] -= process;
	}
	else
	{
		printf("No suitable block Found ");
	}
	return 0;
}
\


```

## `callocprogram.c`

```c
#include<stdio.h>
#include<stdlib.h>
int main()
{
	int *arr = (int*) calloc(5,sizeof(int));
	if (arr == NULL)
	{
		printf("Memory Not allocated \n");
		return 1;
	}
	for( int i =0 ; i < 5; i++)
	{
		printf("%d",arr[i]);
	}
	free(arr);
	return 0;
}

```

## `firstfitallocation.c`

```c
#include<stdio.h>
#define SIZE 5
int main()
{
	int blocks[SIZE] = {100, 200, 300, 400,500};
	int process = 212;
	for( int i = 0 ; i < SIZE ; i++)
	{
		if (blocks[i] >= process)
		{
			printf("PROCESS ALLOCATED IN BLOCK %d ",i);
			blocks[i] -= process;
		       break;
		}
	}
return 0;
}

```

## `linkedlistnode.c`

```c
#include<stdio.h>
#include<stdlib.h>
struct Node
{
	int data;
	struct Node *net;
};
int main()
{
	struct Node* head = (struct Node*)malloc(sizeof(struct Node));
	head -> data = 100;
	head -> net = NULL;
	printf("Data : %d \n",head -> data);
	free(head);
	return 0;
}


```

## `mallocprogram.c`

```c

#include <stdio.h>
#include <stdlib.h>
int main()
{
	int *ptr = (int *)malloc(sizeof(int));
		if(ptr == NULL)
		{ 
			printf("Memory not allocated \n");
			return 1;

		}
		*ptr = 10;
		printf("Value : %d\n",*ptr);
		free(ptr);
		return 0;
}


```

## `realloc.c`

```c
#include<stdio.h>
#include<stdlib.h>
int main()
{
	int *arr = malloc(2 * sizeof(int));
	arr[0] = 1; arr[1] = 2;
	arr = realloc(arr, 4 * sizeof(int));
	arr[2] = 3; arr[3] = 4;
	for ( int i = 0; i < 4; i++)
	printf("%d\n",arr[i]);
	free(arr);
	return 0;
}	

```

