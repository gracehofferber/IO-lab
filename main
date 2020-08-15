//Created by Grace Hofferber

#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/wait.h>


int main(){
	FILE *file;
	FILE *file1;
	int status;
	char temp[1024];
	file = fopen("lab2.txt", "r");
	file1 =fopen("lab2.txt","r");

	//didn't open correctly.
	if(file ==NULL){
		printf("Error reading in file!\n");
		exit(0);
	}

	int pid = fork();

	if(pid == 0){
	//child process
		printf("Child Process: %d\n", getppid());
		while(fgets(temp,sizeof(temp),file)!= NULL){
			printf("%s",temp);
			fflush(stdout);
		}

	
	}
	else if(pid < 0){
		printf("Forking failed!\n");
	}
	else{
	//parent process
		wait(&status);
		printf("Parent process: %d\n", getpid());
		while(fgets(temp,sizeof(temp),file1)!= NULL){
			printf("%s",temp);
			fflush(stdout);
		
		}

	}
	

	fclose(file);
	return 0;
}
