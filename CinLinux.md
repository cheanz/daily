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
