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
***  
# difference between initialization and assignment  
LHS: left hand side
array type cant be assigned
__restrict  
？优化等级
# Escape sequences
In C, all escape sequences consist of two or more characters, the first of which is the backslash, \ (called the "Escape character"); the remaining characters determine the interpretation of the escape sequence. For example, \n is an escape sequence that denotes a newline character.
# in Unix and linux \n is the code for end-of-line
***  
#bugs
![Screenshot from 2022-07-18 14-34-22](https://user-images.githubusercontent.com/59786755/179456280-45262c2c-6c57-47c6-b819-8796d4736032.png)

![Screenshot from 2022-07-18 14-36-06](https://user-images.githubusercontent.com/59786755/179456400-e929ecc1-1787-4c72-a90d-b93cef086a88.png)
When compile escape.c, there is no main funciton though I wrote it in escape.c, whcih can be confirmed in escape.i. The reason is, in this folder, there are other files containing main functions.

