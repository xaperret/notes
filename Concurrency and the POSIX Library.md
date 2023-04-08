---
date created: Saturday, January 22nd 2022, 6:18:05 pm
date modified: Sunday, January 23rd 2022, 3:49:08 pm
---

- Topic:
- Tags: #review #pn_2_1
- Links:
- Date Created: 22-01-22

---

# Concurrency and the POSIX Library

## Concurrency and the POSIX Library in Few Words

### Create a Thread

To create a [[Thread]], we use

```c
int pthread_create(pthread_t *thread, const pthread_attr_t *attr, void *(*start_routine) (void *), void *arg);
```

- `thread` is the **identifier** for the [[Thread]]
- `attr` allows us to define the [[Thread]] attributes, we can use those by *default* by specifying `null`
- `start_routine` is the [[Method]] ran by the newly created [[Thread]], it **MUST** have the following **prototype** `void *function(void *data)` since we are using void [[Pointers in C]] it gives us more flexibility
- `arg` is the argument passed to the function
- **Returns**: 0 for success

```ad-warning

Always test the result !

```

```c
#include <pthread.h>
#include <stdio.h>
#include <stdlib.h>

void *my_func(void __attribute__((unused)) *arg) {
	printf("\nThis is my awesome function that just print this text\n");
	return NULL;
}

int main(int argc, char **argv) {
	pthread_t thread; // we are going to keep inside this var the id
	if(pthread_create(&thread, NULL, func, NULL) != 0) {
		perror("thread creation error");
		return EXIT_FAILURE;
	}
	return EXIT_SUCCESS;
}
```

Now it is important to note that if we don't join [[Thread]] the program might close before the [[Thread]] is finished.

### Join

![[Pasted image 20220122183034.png]]

The join will wait that the [[Thread]] given in argument is finished. The place from where the [[Thread]] is called will be blocked until the [[Thread]] given in argument is finished.

```c
int pthread_join(pthread_t thread, void **value_ptr);
```

- `value_ptr` contains the return value
- **Returns** 0 on success

```c
#include <pthread.h>
#include <stdio.h>
#include <stdlib.h>
void *func(void *arg) {
  char *msg = (char *)arg;
  printf("Message = %s\n", msg);
  return NULL;
}
int main(int argc, char *argv[]) {
  pthread_t t;
  void **res;
  char *msg = "Threads are awesome!";
  if (pthread_create(&t, NULL, func, msg) != 0) {
    perror("thread creation error");
    return EXIT_FAILURE;
  } else {
	 ... // what should we add here so that func is ran correctly
  }
  return EXIT_SUCCESS;
}

```

### Interesting Stuff About Join

It's interesting to note that we cannot know the result of the program below, well we know that the output will contain something like *Thread 1, Thread 2, Status1: 0, Status 2: 4* but we don't know if the first two sentences will be in this order or not since we are using [[Thread]]

```c
void *func1(void *arg) {
  static int exit_code = 0;
  printf("Thread 1\n");
  return &exit_code;
}
void *func2(void *arg) {
  static int exit_code = 4;
  printf("Thread 2\n");
  pthread_exit((void *)&exit_code);
}
int main(int argc, char *argv[]) {
  pthread_t thread1, thread2;
  pthread_create(&thread1, NULL, func1, NULL);
  pthread_create(&thread2, NULL, func2, NULL);
  int *status1, *status2;
  pthread_join(thread1, (void **)&status1);
  pthread_join(thread2, (void **)&status2);
  printf("Status1: %d\n", *status1);
  printf("Status2: %d\n", *status2);
  return EXIT_SUCCESS;
}

```

### Ending a Thread

There are two ways a [[Thread]] finishes its job:

- It finishes by itself, meaning the instruction `return` is used or the [[Method]] `pthread_exit`
- Another [[Thread]] ends it by the [[Method]] `pthread_cancel`
- `exit` which terminates every [[Thread]] of the [[Process]], the place where it was called doesn't matter

```c
void pthread_exit(void *value);
```

This method ends the [[Thread]] and returns `value` to the [[Thread]] doing the [[Join]]. But if it was called in **main** it will **wait** until every [[Thread]] have finished before closing the [[Process]].

### Thread's Attributes

```c
int pthread_attr_init(pthread_attr_t *attr);
int pthread_attr_destroy(pthread_attr_t *attr);
```

The method `pthread_attr_init` initialize a thread's attribute, so it can be used during the [[Thread]] creation. It returns 0 on success.

The method `pthread_attr_destroy` kills the previously defined thread's attribute.

Once the **thread is created**, the **attribute** can be **killed**.

```ad-note

`man pthread_attr_init` gives us the list of possible attributes.

```

### Give Back Control

It's possible to ask the [[Scheduler]] that the [[Thread]] wants to give back control

```c
#include <sched.h>
int sched_yield();
```

**Unfortunately**, there are no **guarantees** that the [[Thread]] will be put in *wait-mode* and that the next one will be run.

Returns 0 for success.

### Auto Identification

A [[Thread]] can obtain its *identifier* with the method.

```c
pthread_t pthread_self();
```

```c
int pthread_create(pthread_t *thread, const pthread_attr_t *attr, void *(*start_routine) (void *), void *arg);
```

Here the *identifier* is `thread` and the argument returned by `pthread_self()`.

Now something that is very import that comes from the man documentation is the following

> Thread identifiers should be considered opaque: any attempt to use a thread ID other than in pthreads calls is non-portable and can lead to unspecified results.

This means `pthread` are meaningful in some area and not in others.

> Thread IDs are guaranteed to be unique only within a process. A thread ID may be reused after a terminated thread has been joined, or a detached thread has terminated.

This means that if a [[Thread]] is done then its **unique thread ID** can be **reused**, meaning we could see the same [[Thread]] id over and over again while these might be different in reality.

> **The thread ID returned by `pthread_self()` is not the same thing as the kernel thread ID returned by a call to `gettid(2)`**

### Comparing Two Identifiers

```c
int pthread_equal(pthread_t t1, pthread_t t2);
```

- Return 0 on success
- Since we cannot guarantee how is implemented `pthread_t` this is the only way to compare identifiers.

## Concurrency and the POSIX Library in Details

## References
