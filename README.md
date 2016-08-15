# cgc_wahoo_challenges
Simple challenges written and used during the course of preparing for 2014-2016 DARPA Cyber Grand Challenge

### SIMPLE_* are programs primarily based on the UVA Dumbledore Grading program used in the class Defense Against the Dark Arts

SIMPLE_00001:  super-simplified dumbledore (smaller buffer, no input parameters to readString function). stack-based buffer overflow in readString.  sample type 1 exploit controls eip and ebp

SIMPLE_00002:  super-simplified dumbledore. stack-based buffer overflow in readString.  User input passed through toUpper() prior to use.  Sample type 1 exploit controls eip and ebp with caveat that if competition framework sends a value with any bytes that correspond to lowercase alpha characters, the POV will fail.

SIMPLE_00003:  super-simplified dumbledore as above. stack-based buffer overflow in readString.  strrev() called on user input.  Sample type 1 POV controls eip and ebp.

SIMPLE_00004: super-simplified dumbledore as above, but heap-based buffer overflow vulnerability (function pointer can be overwritten).  Sample type 1 exploit demonstrates control of eip and edx

SIMPLE_00005: super-simplified dumbledore as above, but global buffer overflow vulnerability (function pointer can be overwritten).  Sample type 1 exploit demonstrates control of eip and esi.

SIMPLE_00006: Modified version of CTF 2016 qualifier CB (thousand cuts base CB).  Stack-based buffer overflow with char buf canary.  Three Sample type 1 POVs provided to demonstrate control  of eip and (esi, edi, ebp)

SIMPLE_00007:  Modified version of CTF 2016 qualifier CB (thousand cuts base CB).  Stack-based buffer overflow with integer canary.  Sample type 1 POV demonstrates control of eip and ebp.

SIMPLE_00008:  Modified dumbledore.  Stack-based buffer overflow vulnerability.  Stack buffer is next to a pointer.  The pointer is dereferenced and transmitted via transmit_all() to stdout sometime after the buffer is filled/overflowed.   Sample type 2 POV demonstrates leaking secret value from secret page.

SIMPLE_00009: Modified dumbledore. Stack-based buffer overflow vulnerability. character rotated -13 upon read, rotated +13 before return.  Working type 1 POV example.

SIMPLE_00010: Modified dumbledore. Stack-based buffer overflow vulnerability. characters xor'd with constant 1-byte key upon read, xor'd with same constant 1-byte keybefore return.  Working type 1 POV example.

SIMPLE_00011: Modified dumbledore. Stack-based buffer overflow vulnerability. character rotated -13 upon read (using a rotate function), rotated +13 before return. Two example type 1 POVs that demonstrate 32-bit control of eip+ebp and eip+ebx respectively.

SIMPLE_00012: Modified dumbledore. Stack-based buffer overflow vulnerability. characters xor'd with constant 1-byte key upon read using rotate_xor() function, xor'd with same constant 1-byte key before return (using rotate_xor() function).  Two example type 1 POVs that demonstrate 32-bit control of eip+ebp and eip+ebx respectively.

SIMPLE_00013: Modified dumbledore. Stack-based buffer overflow vulnerability. characters xor'd with constant 4-byte key upon read using rotate_xor() function, xor'd with same constant 4-byte key before return (using rotate_xor() function).  Sample type 1 POV.
SIMPLE_00014: super-simplified dumbledore as above, but stackbuffer overflow vulnerability (function pointer on stack can be overwritten).  Sample type 1 exploit demonstrates control of eip and esi.

### SIMPLE2_*: layout: stack buffer next to pointer variable, vulnerability:  stack-based buffer overflow. Uses variations on format string specifiers
#### NOTE:  no pollers provided for SIMPLE2 only sample type 2 POV for each.

SIMPLE2_00001: printf("hello: %x\n", *ptr);
SIMPLE2_00002: printf("hello: %d\n", *ptr);
SIMPLE2_00003: printf("hello: %p\n" *ptr);
SIMPLE2_00004: printf("hello: 0x%08x\n", *ptr);
SIMPLE2_00005: write-what-where vulnerability.  stack-based buffer next to an unsigned int ptr allows an attacker to overwrite the address in a pointer variable. The memory location pointed to by the pointer variable is later assigned a user-specified value (via value given to receive).  That attacker can then control the pointer and the data written to it.
SIMPLE2_00006: write-what-where vulnerability. stack-based buffer next to unsigned int pointer like SIMPLE2_00005, but user-specified value is parsed as a string then converted to unsigned int.
