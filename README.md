# AkariDoc
This is TeX documentation of testing framework of porting Intel intrinsic function to RISC.This is one of solution of Intel architecutre dependency problem. 

# Problem
Intel x86-64 is CISC,this has long history and carryes a lot of heritage.CISC like Intel x86-64 is converting CISC instruction to micro op of RISC inside microprosessor.So we need circuit for it and it makes die size large and has a lot of overhead.On the other hand,RISC is relatively new so it carries less heritage and we can use relatively new technology.But we have many source code run only on Intel x86-64.So we need to port Intel x86-64 intrinsic code to RISC.

#Solution
Connect Intel x86-64 and RISC by network. At first local area network.And input Intel intrinsic function and corespondance of that of ported to RISC same value. And make sure it is same.
