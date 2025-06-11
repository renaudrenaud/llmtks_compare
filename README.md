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
- Docker + Ollama + WebUI


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

- 600$ / Month rent
- Docker + Ollama + WebUI
- NVIDIA V100x3
```
neofetch
       _,met$$$$$gg.          renaud@nice_company 
    ,g$$$$$$$$$$$$$$$P.       ------------ 
  ,g$$P"     """Y$$.".        OS: Debian GNU/Linux 12 (bookworm) x86_64 
 ,$$P'              `$$$.     Host: PIO-628U-TR4T+-ST031 0123456789 
',$$P       ,ggs.     `$$b:   Kernel: 6.1.0-28-amd64 
`d$$'     ,$P"'   .    $$$    Uptime: 1 day, 17 hours, 24 mins 
 $$P      d$'     ,    $$P    Packages: 737 (dpkg) 
 $$:      $$.   -    ,d$$'    Shell: bash 5.2.15 
 $$;      Y$b._   _,d$P'      Resolution: 1024x768 
 Y$$.    `.`"Y$$$$P"'         Terminal: /dev/pts/0 
 `$$b      "-.__              CPU: Intel Xeon E5-2697 v4 (72) @ 3.600GHz 
  `Y$$                        GPU: NVIDIA Tesla V100 PCIe 16GB 
   `Y$$.                      GPU: NVIDIA Tesla V100 PCIe 16GB 
     `$$b.                    GPU: NVIDIA Tesla V100 PCIe 16GB 
       `Y$$b.                 Memory: 4873MiB / 257804MiB 
          `"Y$b._
              `"""                                    
```

---

### GMKTec EVO2

- A "high-end" ~€2000 [mini-PC](https://www.gmktec.com/products/amd-ryzen%E2%84%A2-ai-max-395-evo-x2-ai-mini-pc)
- Reviewed here: [YouTube](https://www.youtube.com/watch?v=B7GDr-VFuEo)
- Using [AMD-395](https://www.amd.com/en/products/processors/laptop/ryzen/ai-300-series/amd-ryzen-ai-max-plus-395.html)
- Alex is testing with Windows (yes, I know) using Vulkan drivers
---


## Results

## Results (Color Emoji Bars – Scaled per Table)

### [Gemma 3:4B](https://ollama.com/library/gemma3:4b)

| Hardware        | Tokens/sec | Visual Comparison                    |
|----------------|-------------|--------------------------------------|
| NVIDIA P40     | 63          | 🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨⬜         |
| GMKTec EVO2    | 66          | 🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨⬜         |
| NVIDIA N100    | 80          | 🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩         |

---

### [Deepseek-R1:7b](https://ollama.com/library/deepseek-r1:7b)

| Hardware        | Tokens/sec | Visual Comparison                    |
|----------------|-------------|--------------------------------------|
| NVIDIA P40     | 49          | 🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨⬜⬜         |
| GMKTec EVO2    | 44          | 🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨⬜⬜⬜⬜         |
| NVIDIA N100    | 70          | 🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩         |

---

### [Gemma 3:12b](https://ollama.com/library/gemma3:12b)

| Hardware        | Tokens/sec | Visual Comparison                    |
|----------------|-------------|--------------------------------------|
| NVIDIA P40     | 26          | 🟨🟨🟨🟨🟨🟨🟨🟨🟨⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜         |
| GMKTec EVO2    | 24          | 🟨🟨🟨🟨🟨🟨🟨🟨⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜         |
| NVIDIA N100    | 47          | 🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩         |

---

### [Qwen3:32B](https://ollama.com/library/qwen3:32b)

| Hardware        | Tokens/sec | Visual Comparison                    |
|----------------|-------------|--------------------------------------|
| NVIDIA P40     | 11.14       | 🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩🟩         |
| GMKTec EVO2    | 10.80       | 🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨🟨⬜         |
| NVIDIA N100    | 3.12        | 🟥🟥🟥⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜⬜         |



### Legend

🟩 = high performance
🟨 = average
🟥 = low

Each line 20 blocs max, relative to the best measurement.

---

## Comments

### V100x3 is a fail !

There is only one reason the Qwen3:32B is ultra slow when the model is bigger than one card VRAM: the cards are not interconnected with NVLINK.

Let's prove it:

```
nvidia-smi topo -m
```

|        | GPU0 | GPU1 | GPU2 | CPU Affinity     | NUMA Affinity | GPU NUMA ID |
|--------|------|------|------|------------------|----------------|-------------|
| **GPU0** |  X   | SYS  | SYS  | 0-17,36-53        | 0              | N/A         |
| **GPU1** | SYS  |  X   | PHB  | 18-35,54-71       | 1              | N/A         |
| **GPU2** | SYS  | PHB  |  X   | 18-35,54-71       | 1              | N/A         |

```
Legend:

  X    = Self
  SYS  = Connection traversing PCIe as well as the SMP interconnect between NUMA nodes (e.g., QPI/UPI)
  NODE = Connection traversing PCIe as well as the interconnect between PCIe Host Bridges within a NUMA node
  PHB  = Connection traversing PCIe as well as a PCIe Host Bridge (typically the CPU)
  PXB  = Connection traversing multiple PCIe bridges (without traversing the PCIe Host Bridge)
  PIX  = Connection traversing at most a single PCIe bridge
  NV#  = Connection traversing a bonded set of # NVLinks
```

It means:
GPU	to GPU
* GPU0 <-> GPU1	SYS (slow)
* GPU0 <-> GPU2	SYS (slow)
* GPU1 <-> GPU2	PHB (horrible)

There is no NV0, NV1... interconnect, results are:
* massive swapping via PCIe
* catastrophic lantencies
* zero gain with multi GPU

Solution: contact the company who rents the computer and ask for NVIDIA link or stop this contract


### AMD395+ vs P40

* Performances are in par with the P40
  + one box solution
  + power efficient
  + less noise
  + bigger models (but really big models are really slow)
  - more expansive (x2)
* P40 cost (second hand) is around 300€ + Oculink box 200€ = 500€, but you need a computer (500€) = 1000€
  + less expansive
  - more electric consumption +/- 250W only for the card
  - noise (you need to cool the card)
  - two boxes and more cables solution
