# AkariDoc
This project aim to port and optimize Intel x86-64 Intrinsic function to OpenPOWER,ARM,and RISC-V. 

# Problem
Intel x86-64 is CISC,this has long history and carryes a lot of heritage.CISC like Intel x86-64 is converting CISC instruction to micro op of RISC inside microprosessor.So we need circuit for it and it makes die size large and has a lot of enegy and time overhead.On the other hand,RISC is relatively new so it carries less heritage and we can use relatively new technology.But we have many source code run only on Intel x86-64.So we need to port Intel x86-64 intrinsic code to RISC like architecture like OpenPOWER,ARM and RISC-V.

# Solution strategy

