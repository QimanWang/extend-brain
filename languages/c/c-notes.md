#

### components
```
#include <stdio.h>  
//# preprocessor directive, include the file

```

### data types
```c
/* data types

char 255 
short 65535
int 4 bytes 
long 4 bytes 2^(8*4)
long long 8 bytes ,(2^64) - 1

can use 1 byte to use signed or unsigned

//guarantted byte usage
int8_t
uint64_t

// really small or really large num
floar
double
percisions

// grouped data
struct person {
    char name[50];
    int age;
    int height;
}

struct person me;
me.age = 39;

// array
int v[5] = {1,2,3,4,5}; //compiler will allocate memory
printf("v0 = %i", v[0]);

// pointer
int y = 7;
int *p = &y;

printf("%p\n", p); //print pointer
printf("%p\n", *p); //print value

point <=> array
int *p = v;
v[2] <=> *(v+2) <=> *(p+2) 
*/

```

### loop

```c
// while loop
while(){

}

// do while, checks condition after first do
do {

} while


// for loop
for (int i = 0; i < 5; i ++){

}

// break
exit loop

// continute
skip this iteration
```

### operators

```c

// modulus operator
% 

// increment decrement operator
++ 
--

y= x++ 
//y gets value before inc

y= ++x
// y gets value after inc

//assignment
= 

//equal?
==

&& //and
|| //or

// bit operation
&, |, ^, ~, <<, >>
```



### string
ascii 128

unicode ?

```c
// string
"Q", "I","M","A","N"

%d %lu, strlen()， 

char buffer[10];
strcpy(buffer, something);

// strncpy, pass in buffersize

// buffer will overflow, is fomething is too big

// strcmp() match return 0 if ==



### constant

```c
# define Array_Length 240 // pre processor, replace val with 240

const int arr_len = 240;
```

### file

```c

fopen() - use buffer, higher level

open() - lower level sys call, more control, file descriptors

```


### environment varibale
```c
get_env(), envp(), environ[],
```

### checking return value

```c
// if file failed to open
int fd = -1;
if (fd == -1){
    printf("failed to open file");
    exit(1);
}

while (bytes_read() > 0){

}

```

## build system

make

```Makefile

```


## Socket programming

connection between two program that aren't on the same machine.
```c



// create a new socket
if((sockfd = socket(AF_INET,SOCK_STREAM,0) < 0)){
    printf("bad");
}

// address faimly - internet,  stream socket, 0 == TCP
bzero(&servaddr, sizeof(servaddr));

servaddr.sin_faimly = AF_INET;
servaddr.sin_port = htons(SERVER_PORT);

if (inet_pton(AF))
```

## thread
pthread

```c
pthread_t t;
int *pclient = malloc(sizeof(int));
*pclient = client_socket;
pthread_create(&t, NULL, handle_connectin, pclient);
// thread function need to take, return pointer

```

too much threads can be bad. so let's use a thread pool

```c
THREAD_POOL size 20


pthread_t threadpool[size]

for {
    pthread_create(&threadpool[i], NULL, handle_connectin, pclient);
}

// save connection info somewhere



```

