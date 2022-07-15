 ***
 # system call   
 user 借助 os 去使用 device
 return 1 when error occurs
 return 0 on success 
 # library routine   
 不需要os  not usually use os  
 e.g. sin function
 ## in Standard I/O
 EOF or NULL when error occurs
 ## other library
 1 or 0  
 ?errno defined in errno..h; printed out usign perror library;  
 
***
# stdio
* buffer  
* character representation  
* format
## file pointers
### predefined fp
* stdin (keyboard)
* stdout(terminal screen)
* stderr (standard error output)

## file open and close
* fopen(filename,r/w/a)  r(require already exist) w(if not existed, create;if existed, destroy) a(if not existed, create;if existed, append)
   'r+''w+''a+' both read and write
 * fclose(stream) 0 on seccuss and EOF on error
## main  
argv[0] is the './a.out' itself, so argc can be 1 at least.
## read and write
getc(EOF is returned in the end) putc process one character at a time.
fgets(pointer to a character buffer, integer specifying the size of the buffer,fp referring to a stream open for reading) returns a pointer to the filled buffer or NULL
fputs
# difference between initialization and assignment  
LHS: left hand side
array type cant be assigned
__restrict  
？优化等级

