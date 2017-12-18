# get_next_line
A function that return a line read from a file descriptor.

### About this project
* This is an individual project at 42.
* The objective is to create a function that return a line read from a file descriptor.
* The libc functions allowed on this project are read, malloc and free.
* Static variables are allowed.

### About the function
The prototype of the function is as follow:
```
int get_next_line(const int fd, char **line);
```
* The first parameter is the file descriptor that will be used to read.
* The second parameter is the address of a pointer to a character that will be used to save the line read from the file descriptor.
* The return value can be 1, 0 or -1 depending on whether a line has been read, when the reading has been completed, or if an error has happened respectively.
* The function will return without '\n'.
* The function can manage multiple file descriptor.

### How to use the function
I recommend you to use my [libft](https://github.com/terngkub/libft) instead because I've integrated this function into libft libary.

If you just want to try this one, go to the libft directory. Then run make to create the library (libft.a).
```
make
```

Add the function prototype in your header file.
```
int get_next_line(const int fd, char **line);
```

You can use the function like the example below:
```
int main(void)
{
    int   fd;
    char  *line;
    
    fd = open("File name", O_RDONLY);
    while (get_next_line(fd, line) > 0)
    {
        printf("%s\n", line);
        free(line);
    }
    close(fd);
    return (0);
}
```
