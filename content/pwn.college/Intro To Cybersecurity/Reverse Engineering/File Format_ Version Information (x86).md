# All challenges are from [pwn.college](https://pwn.college/intro-to-cybersecurity/reverse-engineering/)

- Saw the executable `cimg` in `\challenge`

- used `gdb /challenge/cimg` in shell to spawn gdb
- `set disassembly-flavor intel` to make the display of assembly code cleaner
- `info functions` to display all functions loaded from the executable
- `disas main` to dissasmble the main function
  It was seen that the magic numbers were 43, 7e, 4e and 72 and version number 6d

- Exited out of gdb and passed a file generated using the python script below to `cimg` to get the flag

***
```
magic_number = b'\x43\x7e\x4e\x72'
version = b'\x6d'

with open("file.cimg", "wb") as f:
	f.write(magic_number)
	f.write(version)
```
***
