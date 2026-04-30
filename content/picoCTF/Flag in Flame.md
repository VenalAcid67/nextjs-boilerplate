## Download logs.txt from [picoCTF](https://challenge-files.picoctf.net/c_amiable_citadel/5d0fa1b1244c39428b2d5ca4f966fce8772038c43b9bd56f1c9890cb733c807f/logs.txt)

***
- `file logs.txt`
Verified filetype.

Saw Base64 upon opening.

- `base64 -d logs.txt > results | cat results`
Decoded the file into a new file

- `file results`
  Checked the filetype and saw PNG.

Opened and saw hex in the image,

- `echo "706...47D" | xxd -p -r`
Found the flag after decoding the hex.

***