# Práca so súbormi

## read(), write(), fd

#### Syntax:
```c
#include <unistd.h>
int read(int fd, char \*buf, size_t count);
int write(int fd, char \*buf, size_t count);
```
### read()
- načíta count bajtov z kanála fd do vyrovnávacej pamäte buf
- pri úspešnom zbehnutí vráti počet prečítaných bajtov, inak vráti -1

### write()
- zapíše count bajtov do kanála fd do vyrovnávacej pamäte buf
- pri úspešnom zbehnutí vráti počet zapísaných bajtov, inak vráti -1

## open(), close(), flags, inode

#### Syntax
```c
#include <sys/types.h>  
#include <sys/stat.h>  
#include <fcntl.h>  
#include <unistd.h>
int open(char \*pathname, int flags, mode_t mode)
int close(int fd)
```

### open()
- slúži na otvorenie súboru s cestou pathname
- **flags** určuje čítanie, zápis a špeciálne funkcie
	- O_RDONLY -> iba pre čítanie
	- O_WRONLY -> iba pre písanie
	- O_RDWR -> pre čítanie aj písanie
	- O_APPEND -> doplnenie pre každý zápis (podbne ako použite lseek)
	- O_CREAT -> vytvorí súbor ak neexistuje
	- O_EXCL -> vráti chybu ak súbor už existuje
	- O_TRUNC -> skráti súbor na 0 (zmaže obsah)
- **mode**  slúži na určenie práv:
	- základné makrá fungujú následovne:
		1. začiatok je stále S_I
		2. následuje druh práva (**R**ead,**W**rite,e**X**ecute) 
		3. a potom cieľ:
			- USR -> vlastník
			- GRP -> skupina
			- OTH -> ostatní
	