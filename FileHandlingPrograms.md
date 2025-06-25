# FileHandlingPrograms Repository


## `FileHandlingPrograms/AbsCwd.c`

```c
#include<stdio.h>
#include<unistd.h>
int main()
{
	char cwd[1024];
	if (getcwd(cwd,sizeof(cwd)) != NULL)
	{
		printf("Current Directoy : %s \n",cwd);
	}
	else
	{
		perror("getcwd error");
	}
return 0:

}
```

- `FileHandlingPrograms/Backup` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/Backup.c`

```c
#include <stdio.h>
#include <unistd.h>
int main()
{
	if(mkdir("../Backup :" , 0777 ) ==0)
	{
		printf("Back up Directoty is created in parent Directory");
	}
	else
	{
		perror("Directory Creation Failed \n");
	}
}
```

- `FileHandlingPrograms/CreateDir` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/CreateDir.c`

```c
#include <sys/stat.h>
#include <sys/types.h>
#include<stdio.h>

int main()
{
	if(mkdir("Test" , 0777) == -1)
		perror("Test directory creation Failed \n");
	else
		printf("Test Directory Created Successfully \n");
return 0;

}
```

## `FileHandlingPrograms/Destination.txt`

```

```

- `FileHandlingPrograms/DirExist` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/DirExist.c`

```c
#include <stdio.h>
#include <sys/stat.h>
int main()
{
	struct stat st;
	if (stat("Test", &st) == 0 && S_ISDIR(st.st_mode))
	{
		printf("Direcory is exist :  \n");
	}
	else
	{
		printf("Directory is Not existing :\n");
	}

return 0;
}
```

- `FileHandlingPrograms/Images/WhatsApp Image 2025-06-17 at 2.38.36 PM.jpeg` *(binary or non-source file, not shown here)*
- `FileHandlingPrograms/Images/WhatsApp Image 2025-06-17 at 2.38.37 PM(1).jpeg` *(binary or non-source file, not shown here)*
- `FileHandlingPrograms/Images/WhatsApp Image 2025-06-17 at 2.38.37 PM.jpeg` *(binary or non-source file, not shown here)*
- `FileHandlingPrograms/Images/passportsize_photo.jpeg` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/Test/sample.txt`

```
Hi this a copying file from hello to to Sample txt file
I am only Created this file
I am very much Eited to Dump the 
Thank you somuch For Successful validation
```

- `FileHandlingPrograms/a.out` *(binary or non-source file, not shown here)*
- `FileHandlingPrograms/appendgoodbye` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/appendgoodbye.c`

```c
#include<stdio.h>
int main()
{
	FILE *fp = fopen("appendgoodbye.txt","a");
	if(!fp)
	{
		perror("Open Failed  \n");
		return 1;
	}
	fprintf(fp,"I am adding this text my Eistin DOCUMENT\n");
	fclose(fp);
	return 0;
}
```

## `FileHandlingPrograms/appendgoodbye.txt`

```
Hello this my New file the out we need add some tet at the end of the Program




I am adding this text my Eistin DOCUMENT
```

- `FileHandlingPrograms/chmod` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/chmod.c`

```c
#include<stdio.h>
#include<sys/stat.h>

int main()
{
	if(chmod("sample.txt", S_IRUSR ) ==0)
	{
		printf("Permissioin Changes to readmode only   \n");
	}
	else
	{
		perror("chmod failed");
	}

return 0;
 }
```

- `FileHandlingPrograms/copyfile` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/copyfile.c`

```c
#include<stdio.h>
int main()
{
	FILE *src = fopen("Source.txt", "r");
	FILE *dest = fopen("Destination.txt","rw");
	if(!src || dest)
	{
	perror("Files open failed");
	return 1;
	}
char ch;
while( (ch = fgetc(src) != EOF))
		{
		fputc(ch,dest);
		fclose(src);
		fclose(dest);
		}

return 0;
}
```

- `FileHandlingPrograms/copyfile1` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/copyfile1.c`

```c
#include<stdio.h>
int main()
{
	FILE *src = fopen("sample.txt", "r");
	FILE *dest = fopen("hello.txt","w");
	if(!src || !dest)
	{
	perror("Files does not Exist \n");
	return 1;
	}
char ch;
while( (ch = fgetc(src) != EOF))
		{
		fputc(ch,dest);
		fclose(src);
		fclose(dest);	
		}

return 0;
}
```

- `FileHandlingPrograms/copyfile1.o` *(binary or non-source file, not shown here)*
- `FileHandlingPrograms/countnumberlines` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/countnumberlines.c`

```c
#include<stdio.h>
int main()
{
	FILE *fp = fopen("sample.txt","r");
	if(!fp)
	{
		perror("Open Failed");
		return 1;
	}
	int lines = 0;
	char ch;
	while((ch = fgetc(fp)) != EOF)
		if(ch =='\n')
			lines++;
	fclose(fp);
	printf("Total Lines : %d\n ",lines);
	return 0;
}
```

- `FileHandlingPrograms/createfifo` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/createfifo.c`

```c
/*WAP to create a FIFO named "myfifo" */

#include<stdio.h>
# include<sys/stat.h>
int main()
{
	if(mkfifo("myfifo",0666) == -1)
		perror("FIFO Creation Failed");
	else
		printf("FIFO created successfull \n");
	return 0;
}
```

- `FileHandlingPrograms/createfile` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/createfile.c`

```c
#include <stdio.h>
int main()
{ 
FILE *fp = fopen("hello1.txt","w");
if(fp == NULL)
{
	perror("File creation Failed");
	return 1;
}
fprintf(fp,"Hello, world we are writing programs for file handling !\n");
fclose(fp);
return 0;
}
```

- `FileHandlingPrograms/createtempfile` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/createtempfile.c`

```c
#include <stdio.h>
int main()
{
	FILE *fp = tmpfile();
	if(!fp)
	{
		perror("Fail Creation Failed \n");
		return 1;
	}
	fprintf(fp,"Temporary data \n");
	rewind(fp);
	char ch;
	while((ch = fgetc(fp)) != EOF)
		putchar(ch);
	fclose(fp);
	return 0;
}
```

- `FileHandlingPrograms/delete` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/delete.c`

```c

```

## `FileHandlingPrograms/deletefile.c`

```c
#include<stdio.h>
int main()
{
	if (remove("rename")==0)
	{
		printf("File deleted successfully \n");
	}
	else
	{
	
		perror("File deletion is failed \n");
	}
	
	return 0;
}
```

- `FileHandlingPrograms/display` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/empty.txt`

```
I am create an Empty File !
```

- `FileHandlingPrograms/emptyfile` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/emptyfile.c`

```c
#include <stdio.h>
int main()
{ 
FILE *fp = fopen("empty.txt","w");
if(fp == NULL)
{
	perror("File creation Failed");
	return 1;
}
fprintf(fp,"I am create an Empty File !\n");
fclose(fp);
return 0;
}
```

- `FileHandlingPrograms/filesize` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/filesize.c`

```c
#include <stdio.h>
int main()
{
	FILE *fp = fopen("sample.txt","r");
	if (!fp)
	{
		perror("File does not Exist:  \n");
		return 1;
	}
	fseek(fp , 0 , SEEK_END);
	long size = ftell(fp);
	printf("File Size  : %ld  bytes \n", size);
	fclose(fp);
	return 0;
}
```

- `FileHandlingPrograms/filetype` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/filetype.c`

```c
/* File ;Type */
#include <stdio.h>
#include <sys/stat.h>

int main()
{
	struct stat st;
	stat("path/ to/ check \n", &st);

	if(S_ISREG(st.st_mode))
	{
		printf("Regular File \n");
	}
	else if(S_ISDIR(st.st_mode))
	{
		printf("Dirctory \n");
	}
	else if(S_ISLNK(st.st_mode))
	{
		printf("Symbolic Link \n");
	}
	else
	{	
		printf("Other Type ");
	}

	return 0;
}
```

- `FileHandlingPrograms/getfilepermission` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/getfilepermission.c`

```c
/* Get File Permissions of "file.txt"*/

#include<stdio.h>
#include<sys/stat.h>
int main()
{
struct stat st;
stat("Destination.txt", &st);
printf("Permission %o :", st.st_mode & 0777);
return 0;
}
```

## `FileHandlingPrograms/hello.txt`

```

```

## `FileHandlingPrograms/hello1.txt`

```
Hello, world we are writing programs for file handling !
```

- `FileHandlingPrograms/images` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/images.c`

```c
#include<stdio.h>
#include<dirent.h>
int main()
{
	DIR *dir = opendir("Images");
	struct dirent *entry;
	int count = 0;
	while((entry = readdir(dir)))
	{
		if ((entry->d_type == DT_REG))
		count++;
	}

	closedir(dir);
	{
	printf("Total files : %d \n", count);
	}

return 0;
}
```

- `FileHandlingPrograms/inputoutput` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/inputoutput.c`

```c
#include <stdio.h>

int main() {
    FILE *fp = fopen("hello.txt", "r");
    fseek(fp, 0, SEEK_END);
    long size = ftell(fp);
    FILE *out = fopen("Destination.txt", "w");

    for (long i = size - 1; i >= 0; i--) {
        fseek(fp, i, SEEK_SET);
        fputc(fgetc(fp), out);
    }

    fclose(fp);
    fclose(out);
    return 0;
}
```

- `FileHandlingPrograms/movefile` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/movefile.c`

```c
#include<stdio.h>

int main()
{
	if(rename("sample.txt","Test/sample.txt") == 0)
		printf("File moved Successful");
	else
		perror("Move Failed");
	return 0;
}
```

## `FileHandlingPrograms/opendisplay.c`

```c
#include<stdio.h>
int main()
{
	printf("Opening a File.............");
	FILE *fp = fopen("hello.txt","r");
	printf("writing and reading a file.............\n");
	if (fp  == NULL)
	{
		perror("File open Failed \n");
	}

	char ch;
	while((ch = fgetc(fp)) != EOF)
	{
		putchar(ch);
	}
	fclose(fp);
	return 0;
}
```

## `FileHandlingPrograms/ownertouser.c`

```c
#include<stdio.h>
#include<unistd.h>
#include<pwd.h>
#include<sys/types.h>
int main()
{
	struct passwd *pw = getpwnam("user1");;
	if(!pw)
	{
		perror("user not Found \n");
		return 1;
	}
	if(chown("sample.txt",pw->pw_uid, -1) == 0)
		printf("Owner ship Changed \n");
	else
	{
		perror("Chown failed \n");
	}
return 0;
}
```

- `FileHandlingPrograms/readCSVfile` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/readCSVfile.c`

```c
#include <stdio.h>

int main()
{
	FILE *fp = fopen("data.csv","r");
	if(!fp)
	{
		perror("File open Failed");
		return 1;
	}
	char buffer[1024];
	while(fgets(buffer,sizeof(buffer),fp))
	{
		printf("%s", buffer);
	}
	fclose(fp);
	return 0;
}
```

- `FileHandlingPrograms/readdatafromfifo` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/readdatafromfifo.c`

```c
/* REad Data From FIFO */

#include <stdio.h>
# include<fcntl.h>
#include<unistd.h>
int main()
{
	char buffer[128];
	int fd = open("myfifo",O_RDONLY);
	if(fd == -1)
	{
	perror("Open Failed");
	return 1;
	}
	read(fd,buffer,sizeof(buffer));
	printf("Received : : %s \n",buffer);
	close(fd);
	return 0;
}
```

- `FileHandlingPrograms/readdisplay` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/readdisplay.c`

```c
#include<stdio.h>
int main()
{
	printf("Opening a File.............");
	FILE *fp = fopen("hello.txt","r");
	printf("writing and reading a file.............\n");
	char line[1024];
	int count = 0;
	if (fp  == NULL)
	{
		perror("File open Failed \n");
	}

	while((fgets(line,sizeof(line),fp) && count << 10))
	{
		printf("%s", line);
		count++ ;
	}
	fclose(fp);
	return 0;
}
```

## `FileHandlingPrograms/rename.c`

```c
#include <stdio.h>
int main()
{
	if(rename("hello.txt:","sample.txt") == 0)
	{
		printf("File renamed successfully \n");
	}
	else
	{
		perror("Rename failed \n");
	}
	return 0;
}
```

- `FileHandlingPrograms/rename1` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/renamefile.c`

```c
#include <stdio.h>
int main()
{
	if(rename("oldname.txt","newname.txt") == 0)
	{
		printf("File renamed successfully \n");
	}
	else
	{
		perror("Rename failed \n");
	}
	return 0;
}
```

- `FileHandlingPrograms/rmcontent` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/rmcontent.c`

```c
/* Recursively Delete Directory "Temp" and Its Contents */

#include<stdio.h>
#include<stdlib.h>
int main()
{
	system("rm -rf Temp");
	printf("Remove Directory Temp in your system \n");
	return 0;
}
```

- `FileHandlingPrograms/sample` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/sample.c`

```c
#include<stdio.h>
int main()
{
	FILE *fp = fopen("sample.txt","r");
	if(fp )
	{
		printf("File Exist :\n");
		fclose(fp);
	}
	else
	{
		printf("File does not Exist:");
	}
return 0;
}
```

- `FileHandlingPrograms/searchstring` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/searchstring.c`

```c
#include<stdio.h>
int main()
{
	FILE *fp = fopen("sample.txt","r");
	if(!fp)
	{
		perror("Open Failed");
		return 1;
	}
	int lines = 0;
	char buffer[1024];
	while(fgets(buffer,sizeof(buffer),fp))
	{
		lines++;
		if(strstr(buffer,"target_string"))
			printf("Found at Line : %d \n",lines);
	}
	fclose(fp);
	return 0;
}
```

## `FileHandlingPrograms/tempdeletefiles.c`

```c
#include<stdio.h>
# include <unistd.h>
#include<string.h>
#include<dirent.h>
int main()
{
	DIR *dp = opendir("Temp");
	struct dirent *entry
		if(!dp)
		{
			perror("Open Failed");		
			return 1;
		}
	while((entry = readdir(
```

- `FileHandlingPrograms/truncatefile` *(binary or non-source file, not shown here)*
## `FileHandlingPrograms/truncatefile.c`

```c
/* Truncate File tt in 20 bytes */

#include <stdio.h>
#include <unistd.h>
int main()
{
	if(truncate("Destination.txt", 20) == -1)
		perror("Truncate Failed \n");
	else
		printf("File truncate to 20bytes \n");
	return 0;
}
```

