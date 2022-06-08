<div id="top"></div>

# LIBFT 
Creat a static libery from useful function in c.   
this just a short note how each functions work.

---
## PART 1 - Libc FUNCTION
all of this function can be found in c libery   
### FT_IS
`int ft_isalpha(int c)` - check input is A-Z or a-z if not return 0.   
`int ft_isdigit(int c)` - check input is 0 - 9 oh i mean charactor.   
`int ft_isalnum(int c)` - combination of isalpha and isdigit.   
`int ft_isprint(int c)` - From 32 to 126 check table you will konw why.   
`int ft_isascii(int c)` - check input is ascii charactor.   
   
<strong>NOT</strong> FT_IS But ... I don't know where to catagorize it.   
`int ft_toupper(int c)` - recieve <strong>LOWERCASE</strong> charactor and change it to <strong>UPPERCASE</strong>   
`int ft_tolowwer(int c)` - recieve <strong>UPPERCASE</strong> charactor and change it to <strong>LOWWERCASE</strong>

### FT_MEM
basic memory access.   
`void *ft_memset(void *des, int c, size_t len)` - recieve **address** then assigned **value** to the address (have length).   
`void ft_bzero(void *des, size_t len)` - memset but value = 0.   
`void ft_memcpy(void *dst, const void *src, size_t len)` - copy value from src address to the destination address. restrict in c99 if you want more rigor     
`void ft_memmove(void *dst, const void *src, size_t len)` - also copy but handle case overlap memory.   
``` plaintext
c[] = "123456"
memcpy(c[1],c[0],3) -->c = "111156"
memmove(c[1],c[0],3) --> c = "112356"
```
`ft_memchr ` - return address of the first founded value.   
`ft_memcmp` - compare each element in array return diff of differant element. 0 if equal.    

<strong>****Note the different between mem function and string function is mem dont stop at string terminate beware segfualt during use</strong>

### FT_STR BASIC ...
really?   
ft_strlen - find lengnth of the string. ***MOST USE***   
ft_strlcpy - copy form src to des return length of the result (des length)   
ft_strlcat - concatinate destination string from source string return final length of destination length;   
ft_strchr - find first value in array return address of the founded value. else return NULL(address 0 )   
ft_strrchr - same above but find last   
ft_strncmp - compare each element in string return diff of value that difference.   
ft_strnstr - find substring in string if found return the first of found address.  
ft_strdup - make new string from old sting. new string was allocate at heap. **(malloc(colloc) strlen + 1 then cpy)**   

ft_colloc - malloc then bzero. **Useful for create string with \0 it decrese one line of code**   

### FT_ATOI and FT_ITOA   
ft_atoi - recieve str then return int if that string are correct pattern.   
ft_itoa - recieve integer then return array of charactor that made from int(NOT libc)   

---
## PART 2 
this function are not in lib c or have some part was change

### FT_STR
ft_substr - create string from main string by choose index and length.   
ft_strjoin - creat new string from 2 string concatinated  
ft_strtrim - creat new string from trim old string by charactor set.   
ft_split - creat two dim arraty from string by split the string with charator.   

ft_striteri - how explain uhh.. oh  take array and function then apply function to all element in an array   
ft_strmapi - same striteri but create new array that collect return of the function   

### FT_PUT
write value to file descriptor directly use fd = 1 for std_out   
ft_putchar_fd - just char  
ft_putstr_fd - jsut char array  
ft_putendl_fd - just char array + \n   
ft_putnbr_fd - it take int. recursive put.   
<strong>man 2 write</strong>

---
## BONUS PART don't miss this part
This part, It about Linked list.   
Linked what ?   
It is a one of many type of data structure.   
Basic. Linked list was create by a struct at least 2 element   
The first is data that we need to collect   
The secound is pointer to the next node of linked list   
   
let see  
```c
typedef struct s_list
{
    void    *data;
    t_list  *next;
}               t_list;
```
We have to creat fuction that handle this data structure.   

#### FUNTION LIST
##### ft_lstnew
`ft_lstnew(t_list *new)` - create new node

---

<p align="right">(<a href="#top">back to top</a>)</p>

