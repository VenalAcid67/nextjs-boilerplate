# All challenges are from [pwn.college](https://pwn.college/intro-to-cybersecurity/reverse-engineering/)

- Saw a python suid script in `\challenge` which read a file.
  It checked if the file extension was `.cimg` and asserted if the magic numbers were liitle endian and was  `0x474d215b`

- Using the python script below, the file was passed and the flag was found.

***
```
magic_number = b'\x5b\x21\x4d\x47'

with open("file.cimg", "wb") as f:
	f.write(magic_number)
```
***