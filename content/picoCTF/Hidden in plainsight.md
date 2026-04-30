## Download img.jpg from [picoCTF](https://challenge-files.picoctf.net/c_amiable_citadel/5123e48e549ac5d8abb421627478aaf17d88b8e57b72ae5163183c55a693cc57/img.jpg)

***
- `file img.jpg`
  Verified the file-type and saw base64.

- `echo c3R..VE9 | base64 -d`  
  Decoded to obtain passphrase for steghide.
  
**Note: Steghide is a steganography program that is able to embed data and files in various kinds of image- and audio-files. The color- respectivly sample-frequencies are not changed thus making the embedding resistant against first-order statistical tests. It used RIjndael-128 algorithm for embedding.**

  
- `steghide info img.jpg`  
  Entered passphrase when  prompted and saw flag.txt was embedded in img.jpg
    
- `steghide --extract -sf img.jpg`
  Entered passphrase and extracted the flag
***