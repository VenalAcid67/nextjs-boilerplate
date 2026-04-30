# All challenges are from [pwn.college](https://pwn.college/intro-to-cybersecurity/reverse-engineering/)

- Saw a python suid script in `\challenge` which read a file.
  It checked if the file extension was `.cimg` and asserted if the magic numbers were `[nnR` and that the version was 170 and asserted if the header length was 6 bytes

- Using the python script below, the file was passed and the flag was found.

***
```
version = b'\xaa\x00'
magic_number = b'\x5b\x6e\x6e\x52'

with open("file.cimg", "wb") as f:
	f.write(magic_number)
```
***