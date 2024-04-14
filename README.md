// C program to demonstrate working of tmpfile() 
#include <stdio.h> 
int main() 
{ 
	char str[] = "Hello GeeksforGeeks"; 
	int i = 0; 

	FILE* tmp = tmpfile(); 
	if (tmp == NULL) 
	{ 
		puts("Unable to create temp file"); 
		return 0; 
	} 

	puts("Temporary file is created\n"); 
	while (str[i] != '\0') 
	{ 
		fputc(str[i], tmp); 
		i++; 
	} 

	// rewind() function sets the file pointer 
	// at the beginning of the stream. 
	rewind(tmp); 

	while (!feof(tmp)) 
		putchar(fgetc(tmp)); 
} 
# create-a-temporary-file-in-c
