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
`void *ft_memset(void *des, int value, size_t len)` - recieve **address** then assigned **value** to the address (have length).   
`void ft_bzero(void *des, size_t len)` - memset but value = 0 and no return.   
`void ft_memcpy(void *dst, const void *src, size_t len)` - copy value from src address to the destination address. restrict in c99 if you want more rigor return dst     
`void *ft_memmove(void *dst, const void *src, size_t len)` - also copy but handle case overlap memory.   
``` plaintext
c[] = "123456"
memcpy(c[1],c[0],3) -->c = "111156"
memmove(c[1],c[0],3) --> c = "112356"
```
`void *ft_memchr(void *mem, int value); ` - return address of the first founded value.   
`int ft_memcmp(void *mem1, void *mem2);` - compare each element in array return diff of differant element. 0 if equal.    

<strong>****Note the different between mem function and string function is mem dont stop at string terminate beware segfualt during use</strong>

### FT_STR BASIC ...
really?   
`size_t ft_strlen(char *str)` - find lengnth of the string. ***MOST USE***   
`size_t ft_strlcpy(char *dst,char const *src, size_t f_len)` - copy form src to des return length of the result (des length)   
`size_t ft_strlcat(char *dst, char const *src, size_t f_len)` - concatinate destination string from source string return final length of destination length, f_len = final length   
`char *ft_strchr(const char *str, int value);` - find first value in array return address of the founded value. else return NULL(address 0 )   
`char *ft_strrchr(const char *str, int value); ` - same above but find last   
`int ft_strncmp(const char *s1, const char *s2, size_t len);` - compare each element in string return diff of value that difference.   
`char *ft_strnstr(const char *haystack, const char needle, size_t len);` - find substring in string if found return the first of found address.  
`char *ft_strdup(const char *str)` - make new string from old sting. new string was allocate at heap. **(malloc(colloc) strlen + 1 then cpy)**   

`void *ft_colloc(size_t a, size_t b)` - malloc then bzero. **Useful for create string with \0 it decrese one line of code**   

### FT_ATOI and FT_ITOA   
`int *ft_atoi(char *str)` - recieve str then return int if that string are correct pattern.   

`char *ft_itoa(int a)` - recieve integer then return array of charactor that made from int(NOT libc)   

---
## PART 2 
this function are not in lib c or have some part was change

### FT_STR
`cahr *ft_substr(const char *s, unsigned int start, size_t len)` - create string from main string by choose index and length.   

`char *ft_strjoin(const char *s1, const char *s2)` - creat new string from 2 string concatinated  

`char ft_strtrim(char const *s1, char const *set)` - creat new string from trim old string by charactor set.   

`char **ft_split(char const *s, char s)` - creat two dim arraty from string by split the string with charator.   


`void ft_striteri(char *s, void (*f)(unsigned int, char *))` - how explain uhh.. oh  take array and function then apply function to all element in an array   

`char *ft_strmapi(char const *s, char (*f)(unsigned int, char))` - same striteri but create new array that collect return of the function   


### FT_PUT
write value to file descriptor directly use fd = 1 for std_out   
`void ft_putchar_fd(chhar c, int fd)` - just char  

`void ft_putstr_fd(char *s,int fd)` - jsut char array  

`void ft_putendl_fd(char *s, int fd)` - just char array + \n   

`void ft_putnbr_fd(int n, int fd)` - it take int.
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
`t_list ft_lstnew(t_list *new)` - create new node  

`void ft_lstadd_front(t_list **lst, t_list *mew)` - add new node to the start of linked list.
``` plain text
newnode -> old_linked list
```   
`t_list ft_lstsize(t_list *lst)` - check list size    

`t_list *ft_lstlast(t_list *lst)` - return address of last lst  

`t_list *ft_lstadd_back(t_list *lst, t_list *new)` - add new node to the end of list
```plaintext
old_list -> new_node
```
`void ft_lstdelone(t_list *lst, void (*del)(void *)) ` - remove one node   

`void ft_lstclear(t_list **lst, void (*del)(void*))` - remove whole list    

`t_list ft_lstiter(t_list *lst, void (*f)void(void *));` - apply function to data in lst every node     

`t_list *ft_lstmap(t_list *lst, void *(*f)(void *), void (*del)(void *))` - same iterbut return result linked list  


---

<p align="right">(<a href="#top">back to top</a>)</p>

