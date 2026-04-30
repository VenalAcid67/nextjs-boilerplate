# All challenges are from [pwn.college](https://pwn.college/intro-to-cybersecurity/reverse-engineering/)

- Saw a python suid script in `\challenge` which read a file.
  It checked if the file extension was `.cimg` and if the magic numbers were `{0nr`

- Using the python script below, the file was passed and the flag was found.

***
```
magic_number = b'\x7b\x30\x6e\x72'

with open("file.cimg", "wb") as f:
	f.write(magic_number)
```
***