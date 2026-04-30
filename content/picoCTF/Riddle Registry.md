## Download confidential.pdf from [picoCTF](https://challenge-files.picoctf.net/c_amiable_citadel/85ff7059d0bc98abe4aa040e2dd70a342f9f9aaa8edd70ccba166efeb6249afa/confidential.pdf).

***
- `file confidential.pdf`
Verified file-type.

- `strings confidential.pdf | grep pico`
Searching for the flag embedded in binary.

#### Hint 1 &rarr; The pdf file is a decoy

Opened the file and saw random gibberish  like "lorem ipsum" everywhere.

**Note: `hexdump` displays the contents of binary files in a human-readable format. It shows data in hexadecimal, decimal, octal, or ASCII, and is used to analyze file formats.**

#### HInt 2 &rarr; Look deeper in the surface.


**Note: `exiftool` is used for reading, writing, and manipulating image, audio, video, and PDF metadata.**


- `exiftool confidential.pdf`
  Viewed metadata using exiftool.
  
**Note: `base64` is used for encoding normal human-readable text to base64 and `-d` can be passed to it for decoding. It typically dosen't take input by itself, and so, it need to provided input using `|` from another text file or `echo`, which is used to return to the stream itself.**

- `echo "cGl...ZH0" | base64 -d`
Found Base64 in one of the fields, and found the flag after decoding it.  
  