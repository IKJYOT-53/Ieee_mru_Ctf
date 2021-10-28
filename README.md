# IEEE MRU CTF 2021
Solved 2 challenges in 2 hours :cry: :skull:

## OSINT 
##### welcometotheinternet
The challenge welcometotheinternet was a general osint challenge with the prompt 

> Our social media manager said "Like,follow and comment on our photo to give use feedback!"

So checked the instagram comments.
Found the [post](https://www.instagram.com/p/CUb60REPb9p/) with this random text
> bXJ1ezVoM2xsXzFzXzRtNHoxbmd9

Base64 decoded it and voila

> mru{5h3ll_1s_4m4z1ng}

## FORENSICS
##### testfunc
This challenge was a bit difficult,but figured it out with a little bruteforce and luck.
The prompt said 

> One of our analysts found this file inside our compromised system.I wonrder what is does...
>Maybe it's got a password?
>Just can't get to print it..

And was provided with a file   **testfunc.py**

Ran strings on it
```sh
strings testfunc.py
```
The output was hilariously large
But it contained a long list of strings encoded in base64
something along the line of this :
> bXJ1e2U0QUJVS2RvZnBmc3z9
> .
> .
> .

Upon Decoding found a lot of flags (about 100)
A few made sense in l33t code:
> mru{CHkra7IUpperKk}
>mru{i7_w45_m3du54}

the last one worked

---

##### There was also another challenge that i worked on but wasn't able to complete from the cryptography section named :
##### cryptum
The challenge prompt was this :

> They do not deserve the mantle responsibility! Encrypt!

And was provided with a zip file **Cryptum.zip**
The file was encrypted , so used [fcrackzip](https://github.com/hyc/fcrackzip) and [rockyou.txt](https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt)

```sh
fcrackzip -v -u -D -p rockyou.txt Cryptum.zip
```
found password = 'close'
so extracted text file **flag.txt**
Now the flag.txt file contained a lot of stuff , but found the some code written in a [forbidden language](https://en.wikipedia.org/wiki/Brainfuck)
Tried processing it but failed at that point and time was up.

The experience was pretty good.Learnt a lot.Had fun solving the challenges.
Thanks IEEE MRU.