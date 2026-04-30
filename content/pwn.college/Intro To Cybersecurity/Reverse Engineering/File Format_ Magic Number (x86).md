# All challenges are from [pwn.college](https://pwn.college/intro-to-cybersecurity/reverse-engineering/)

- Saw the executable `cimg` in `\challenge`

- used `gdb /challenge/cimg` in shell to spawn gdb
- `set disassembly-flavor intel` to make the display of assembly code cleaner
- `info functions` to display all functions loaded from the executable
- `disas main` to dissasmble the main function
  It was seen that the magic numbers were 5b, 4f, 4e and 72

- `break * 0x_____` : setting a break at memory address of strcmp
- `run file.cimg` : running the executable inside gdb using a `.cimg` file created using the python script below
  	The execution stopped at strcmp

- `print (char*) $rdi` and `print (char*) $rsi` : checks the value stored in the source register (hardcoded in program) and the destination register (fetched from hexdump)
  Both were storing `.cimg`

- Exited out of gdb and passed a file generated using the python script below to `cimg` to get the flag

***
```
magic_number = b'\x5b\x4f\x4e\x72'

with open("file.cimg", "wb") as f:
	f.write(magic_number)
```
***
#### NOTE: all next x86 levels assume .cimg is the file extension and is checked in the executable