# Token Per Second Comparison

## Objective

We want to compare different solutions available on the market in June 2025 to get a better idea of what to buy for local LLM inference.

Alex published a [video on june 2025](https://www.youtube.com/watch?v=B7GDr-VFuEo) about the Gmktec Evo X2. Let's compare his results with an old NVIDIA P40 and with some 3 V100 Intel computer.

---

## Hardware Description

### NVIDIA P40

This is a second-hand NVIDIA P40 card bought for €250–300 (we bought 3).  
- [Datasheet](https://www.nvidia.com/content/dam/en-zz/Solutions/design-visualization/documents/nvidia-p40-datasheet.pdf)  
- Connected via Oculink or Oculink adapter (~€10): [list on Amazon](https://www.amazon.com/s?k=nvme+to+oculink&i=industrial)  
- Host PC: [GMKTec NucBox K8 Plus](https://www.gmktec.com/products/amd-ryzen-7-8845hs-mini-pc-nucbox-k8-plus?spm=..product_ba613c14-a120-431b-af10-c5c5ca575d55.header_1.1&spm_prev=..index.header_1.1&variant=e031c061-8f2a-45f4-9de2-e1eda86fc00e)

```
renaud@GMK8p:~$ neofetch
             /////////////                renaud@GMK8p 
         /////////////////////            ------------ 
      ///////*767////////////////         OS: Pop!_OS 22.04 LTS x86_64 
    //////7676767676*//////////////       Host: NucBox K8 Plus 
   /////76767//7676767//////////////      Kernel: 6.12.10-76061203-generic 
  /////767676///*76767///////////////     Uptime: 1 day, 2 hours, 19 mins 
 ///////767676///76767.///7676*///////    Packages: 1941 (dpkg) 
/////////767676//76767///767676////////   Shell: bash 5.1.16 
//////////76767676767////76767/////////   Terminal: /dev/pts/0 
///////////76767676//////7676//////////   CPU: AMD Ryzen 7 8845HS w/ Radeon 780M Graphics (16) @ 5.137GHz 
////////////,7676,///////767///////////   GPU: AMD ATI c7:00.0 Device 1900 
/////////////*7676///////76////////////   GPU: NVIDIA Tesla P40 
///////////////7676////////////////////   Memory: 3237MiB / 61099MiB 
 ///////////////7676///767////////////
  //////////////////////'////////////                             
   //////.7676767676767676767,//////                              
    /////767676767676767676767/////
      ///////////////////////////
         /////////////////////
             /////////////
```

---

### NVidia V100 on Xeon E5-2697 v4

```
neofetch
       _,met$$$$$gg.          renaud@nice_company 
    ,g$$$$$$$$$$$$$$$P.       ------------ 
  ,g$$P"     """Y$$.".        OS: Debian GNU/Linux 12 (bookworm) x86_64 
 ,$$P'              `$$$.     Host: PIO-628U-TR4T+-ST031 0123456789 
