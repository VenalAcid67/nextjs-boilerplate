# All challenges are from [pwn.college](https://pwn.college/intro-to-cybersecurity/reverse-engineering/)

- Saw a python suid script in `\challenge` which read a file.
  It checked if the file extension was `.cimg` and asserted if the magic numbers were `CMag` and that the version was 1, asserted 4 byte length of 62 and 4 byte breadth of 23 and data as width times height 

- Using the python script below, the file was passed and the flag was found.

***
```
from struct import *

version = b'\x01'
magic_number = b'\x43\x4d\x61\x67'

width = 62
height = 23
data = bytes([255]*(width*height))
dimension = pack("<II", width, height)


with open("file.cimg", "wb") as f:
	f.write(magic_number)
	f.write(version)
	f.write(dimension)
	f.write(data)

```
***