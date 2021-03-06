AES Crypter-1st Part of SoE RAT
=====================




###What is AES Crypter?
AES crypter is a tool that takes a Portable-Executable program and encrypts it
so that is unable to be analyzed in memory by AVs or reverse-engineers.
###How does AES Crypter work?
AES Crypter receives a user-designated program and outputs an encryption version of the program. Essentially, the encrypted program is essentially a **stub** attached to a **payload** in memory, which holds the obfuscated code of the original program. When the encrypted program is executed and loaded into memory, the stub decrypts the payload, recreates into memory from this decrypted code, and then executes the "useful" code at runtime.
![Visual Representation](http://raw.github.com/derekdakid/AES-Crypter-WIN32/master/IMAGES/crypter_example_012.png)

**The payload itself must further be encrypted in order to provide enhanced security, the stub may be rendered obsolete at any time by AVs.**

[] String Variables and Payload encrypted with AES Algorithm

[] Win32 API function calls are encrypted -> Go to kernel32.dll and look at its export address table -> Determine the memory addresses of your functions from the table

[] Length of elements in the "tail" are variable and unpredictable

![Program inMemory](http://raw.github.com/derekdakid/AES-Crypter-WIN32/master/IMAGES/crypter_structere_02.png)
### Credits:
**Project Lead/Lead Hacker: Derek Ta (dta858king@gmail.com)**


### References for Frameworks/Information used in project

[Windows Portable Executable Format: In-depth](http://msdn.microsoft.com/en-us/magazine/cc301805.aspx)

[Win32 API](http://msdn.microsoft.com/en-us/library/windows/desktop/ff818516(v=vs.85).aspx)

[C/C++ Reference] (http://en.cppreference.com/w/)
