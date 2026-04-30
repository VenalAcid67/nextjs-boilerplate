## Download log file from [picoCTF](https://challenge-files.picoctf.net/c_amiable_citadel/49cec6157142f24a599f4164d5b63322c2494f801390d6f22eb91b3aa592bc66/server.log).


* * *
Found multiple pieces of flag upon opening logs.txt

- `grep FLAGPART server.log | cut -d " " -f5 | sort -u | tee results`
  Extracted individual flagparts.

**Note: `cut` only works when the fed date is clearly formatted into multiple fields. Otherwise, it throw errors.**

Reassambled to obtain the flag.
* * *