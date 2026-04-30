# All challenges are from [pwn.college](https://pwn.college/intro-to-cybersecurity/reverse-engineering/)

- Saw a c suid file in `\challenge` which was the source code of the executable `cimg`, which read a file and checked if the file extension was `.cimg` and if the magic numbers were `(Nmg` and asserted version to be 116 and occupying 8 bytes

- Using the python script below, the file was passed and the flag was found.

***
```
from struct import *

magic_number = b'\x28\x4e\x6d\x67'
version = pack("<Q", version)

with open("file.cimg", "wb") as f:
	f.write(magic_number)
	f.write(version)
```
***
