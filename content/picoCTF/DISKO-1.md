## Download disko-1.dd.gz form [picoCTF](https://artifacts.picoctf.net/c/536/disko-1.dd.gz).

* * *

- `file disko-1.dd.gz`  
    Verifiying filetype.
    
- `gzip -d disko-1.dd.gz`  
    Decompressing the file.

  **Note: `-d` is used to decompress.**
    
- `file disko-1.dd`  
  Verifying the returned file after decompression.
  
#### Hint &rarr; check for embedded ASCII characters.

- `strings disko-1.dd`
  Checking for embedded ASCII characters.

**Note: `strings` extract and display printable characters in a binary file. Useful for analyzing non-text files by revealing human readable text embedded within them. string show text longer than 4 characters.**

- `strings disko-1.dd | grep pico`
    Found flag amongst ASCII characters after matching with flag format.
* * *