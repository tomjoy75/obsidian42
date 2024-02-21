A pipe is created by calling pipe function :
```C
#include <unistd.h>

int pipe(int fd[2])
```
![[Interprocess_communication.drawio.png]]
- if we read from a pipe whose write has been closed, `read` returns 0 to indicate EOF
- if we write to a pipe whose read end has been closed, the signal `SIGPIPE` is generated. `write` returns -1 with `errno` set to `EPIPE` 