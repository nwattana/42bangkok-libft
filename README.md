<div id="top"></div>

# LIBFT 
Creat a static libery from useful function in c.   
this just a short note how each functions work.

## FT_IS
ft_isalpha - check input is A-Z or a-z if not return 0.   
ft_isdigit - check input is 0 - 9 oh i mean charactor.   
ft_isalnum - combination of isalpha and isdigit.   
ft_isprint - From 32 to 126 check table you will konw why.   
ft_isascii - check input is ascii charactor.   

## FT_MEM
basic memory access.   
ft_memset - recieve **address** then assigned **value** to the address (have length).   
ft_bzero - memset but value = 0.   
ft_memcpy - copy value!! from src address to the destination address.   
ft_memmove - also copy but handle case overlap memory.   
ft_memchr - return address of the first founded value.   
ft_memcmp - compare each element in array return diff of differant element. 0 if equal.    

<strong>Note the different between mem function and string function is mem dont stop at string terminate beware segfualt during use</strong>





<p align="right">(<a href="#top">back to top</a>)</p>

