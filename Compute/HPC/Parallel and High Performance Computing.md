
## Chapter 2 Exercises
You have a wave height simulation application. It is a serial application and does not have any software engineering techniques. Now to turn it into an available tool with 3 other developers, what do you include in your project plan?
- You would need to include version control, test suites and code portability at minimum. Version control offers a way of allowing multiple developers to collaborate as well as having a way of storing the code and the history. Test suites help the code to become more robust as features are tested to ensure they work. Code portability allows for the code to work on multiple systems easier.

Fix the memory leak in:
```c
#include <stdlib.h>


int main(int argc, char *argv[]) {
	int ipos, ival;
	int *iarray = (int *) malloc(10 * sizeof(int));
	
	if (argc==2) ival = atoi(argv[1]);
	
	for (int i = 0; i<=10; i++) {iarray[i] = ipos;}
	
	for (int i = 0; i<=10; i++) {
		if (ival == iarray[1]) ipos=i;
	}

}
```

```c
#include <stdlib.h>

#include <stdio.h>

  

int main(int argc, char *argv[]) {

	int ipos, ival;
	ipos = 0;
	ival = 0;
	int *iarray = (int *) malloc(10 * sizeof(int));
	
	if (argc==2) ival = atoi(argv[1]);
	
	for (int i = 0; i<=10; i++) {iarray[i] = ipos;}
	
	for (int i = 0; i<=10; i++) {
		if (ival == iarray[1]) ipos=i;
	}
	
	printf("%s", (char *) iarray);

}
```

#### Answer:
```c
#include <stdlib.h>

int main(int argc, char *argv[]) {
	int ipos=0, ival;
	int *iarray = (int *) malloc(10 * sizeof(int));
	
	if (argc==2) ival = atoi(argv[1]);
	
	for (int i = 0; i<10; i++) {iarray[i] = ipos;}
	
	for (int i = 0; i<10; i++) {
		if (ival == iarray[1]) ipos=i;
	}
	free(iarray);

}
```
#### What did I miss?
- `ival` doesn't need to be initialised
- There's only 10 values in the array so it should be `i<10` and not `i<=10`
- Free memory at the end.

## Chapter 3

Write a 2D contiguous memory allocator for a lower-left triangular matrix
