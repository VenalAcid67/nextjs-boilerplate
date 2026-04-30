## Challenge instance &rarr; https://play.picoctf.org/practice/challenge/520

* * *

#### Hint 1 &rarr; Check source code for hints
#### Hint 2 &rarr; Key is 13

- `echo "ABG...rf"" | tr 'N-ZA-Mn-za-m' 'A-Za-z'`
  Here, 'N-ZA-M' is the uppercase and 'n-za-m' is the lowercase shifted aphabets, while 'A-Za-z' is the ASCII alphabets.

Found a header to get dev access after decrypting, applied it and resend the request. Found the flag after logging in.