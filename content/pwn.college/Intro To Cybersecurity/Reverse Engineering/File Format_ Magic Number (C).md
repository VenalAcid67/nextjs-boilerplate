# All challenges are from [pwn.college](https://pwn.college/intro-to-cybersecurity/reverse-engineering/)

- Saw a c suid file in `\challenge` which was the source code of the executable `cimg`, which read a file and checked if the file extension was `.cimg` and if the magic numbers were `{nm6`

- Using the python script below, the file was passed and the flag was found.

***
```
magic_number = b'\x7b\x6e\x6d\x36'

with open("file.cimg", "wb") as f:
	f.write(magic_number)
```
***
