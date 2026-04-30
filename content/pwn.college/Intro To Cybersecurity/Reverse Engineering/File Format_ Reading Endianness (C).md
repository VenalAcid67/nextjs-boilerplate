# All challenges are from [pwn.college](https://pwn.college/intro-to-cybersecurity/reverse-engineering/)

- Saw a c suid file in `\challenge` which was the source code of the executable `cimg`, which read a file and checked if the file extension was `.cimg` and if the magic numbers were `1919840040`

- 1919840040 was 726e6f28 in hex
  This is in little endian as hex of decimals are stored in little endian format

- Using the python script below, the file was passed and the flag was found.

***
```
magic_number = b'\x28\x6e\x6f\x72'

with open("file.cimg", "wb") as f:
	f.write(magic_number)
```
***
