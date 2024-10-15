# AkariDoc
This project aim to port and optimize Intel x86-64 Intrinsic function to OpenPOWER,ARM,and RISC-V. 

# Problem
 Intel x86-64 is CISC,this has long history and carryes a lot of heritage.CISC like Intel x86-64 is converting CISC instruction to micro op of RISC inside microprosessor.So we need circuit for it and it makes die size large and has a lot of enegy and time overhead.On the other hand,RISC is relatively new so it carries less heritage and we can use relatively new technology.But we have many source code run only on Intel x86-64.So we need to port Intel x86-64 intrinsic code to RISC like architecture like OpenPOWER,ARM and RISC-V.
 Currently, a lot of Intel x86-64 arcutecture is running in PC or cloud server or supercomputer.The reason why we use Intel x86-64 architecture is software compatibility.

# Solution strategy
 Out solution for software architecture dependency problem is not convert Inte x86 machine code to RISC architecture. Intel intrinsic function is Intel x86-64 dependent because it enable for C language to access SIMD capability of Intel x86-64.Our solution is to make enable to run Intel Intrinsic function on RISC arcutecture. It uses unique wrap structure. The age of ending Moors law,the next advancement of computer technology are RISC-V and other RISC like architecture and other related technology.

 one of example are shown below.
 
 ```c
extern __inline __m128d __attribute__((__gnu_inline__, __always_inline__,__artificial__))
_mm_add_pd (__m128d __A, __m128d __B)
{
   return (__m128d) ((__v2df)__A + (__v2df)__B);
}
```

The source code shown above is one of example of port Intel x8-64 Intrinsic function to OpenPOWER.`_mm_add_pd` is one of Intel Intrinsic function name.

One question arises when writing these port code. "These source code is really correct?" In many cases "no" and it leads to horrible result.Then we need open source testing framework for this.  
This testing framework functionality is written below.  

1, Generate random __m128d value and input `_mm_add_pd` of Intel x86-64 and that of ported to RISC like architecture by inputing __A and __B. Value of __m128d of Intel and RISC must be same  
2, Compare return value of Intrinsic funciton of Intel x86-64 and that of RISC. And make sure its same. If value are same,porting code may be correct.If these value are different,Error exist.  

I think these operation must be executed by file transfer, not network connection.If Intel computer and RISC computer are in same place. USB memory or portable HDD may be used to transfer data.  
The reason we do not use network is one is security reason.These operation may be vulnerable.  


Reference
"Linux on Power Porting Guide"  
https://openpowerfoundation.org/specifications/vectorintrinsicportingguide/


This picture is mascot of Testing framework Akari.
![Picture of Akari](AkariMascot.jpeg "Akari")
