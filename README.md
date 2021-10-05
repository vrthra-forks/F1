# F1 Fuzzer

This is the F1 Fuzzer described in the paper [Building Fast Fuzzers](https://arxiv.org/abs/1911.07707).

If you use F1 in a production setting, if you found bugs with it (yay!), or if
you have any suggestions to share, please let us know – your experience is very
valuable for us.  Thanks!


### List of changes made to the sourcecode to make it run on Linux systems - ###
- "stdint.h" header included in main.c
- fuzz\_src is written to fuzz.S instead of fuzz.s
- "clang -g -Ofast -mcmodel=medium  -o fuzzer main.c fuzz.S" in place of "cc -g -Ofast -o fuzzer main.c fuzz.S" in MacOS
- stackp's array size is INT\_MAX/100 in Linux (INT\_MAX in MacOS)
- out\_region\_initp's arraysize is UINT\_MAX/100 (UINT\_MAX in MacOS)
- all contents of ".section  __DATA,__data" is moved to ".text" section in vm\_ops.s
