# All challenges are from [pwn.college](https://pwn.college/intro-to-cybersecurity/reverse-engineering/)

- Saw the executable `cimg` in `\challenge`

- used `gdb /challenge/cimg` in shell to spawn gdb
- `set disassembly-flavor intel` to make the display of assembly code cleaner
- `info functions` to display all functions loaded from the executable
- `disas main` to dissasmble the main function
  It was seen that the magic numbers were 36, 6d, 7e and 28

- Exited out of gdb and passed a file generated using the python script below to `cimg` to get the flag

***
```
magic_number = b'\x28\x7e\x6d\x36'

with open("file.cimg", "wb") as f:
	f.write(magic_number)
```
***
