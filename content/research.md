+++
title = "Research"
+++

## Research Interests
<!-- {{< figure class="avatar2" src="/neelu-photo-paris.jpeg" alt="avatar">}} -->
<div align="justified">
My research interests broadly include confidential computing, computer systems and computer architecture. Recently, during my PhD, my interests revolve around building trustworthy systems (confidential computing environments, isolation monitors, root of trust, trusted runtimes) and RISC-V. During my masters, I worked on the microarchitectural side of things such as optimising the performance of micro-op caches (at Intel Labs) and optimising energy and performance of hardware cache prefetchers.   
<hr style="height:2px;border-width:0;color:gray;background-color:gray">
<!-- <b><u>PhD Thesis</u>:</b> My PhD thesis has so far revolved around building trustworthy systems. -->

### Building Trustworthy Systems 

Traditionally, cloud service providers (CSP) have been bestowed with immense control over their customer's data. The purpose of confidential cloud computing is to take this control from the CSP and grant it to customers instead. Though the design space in this field has been widely explored in the last decade, there are obstacles in the form of prioprietary and specialised designs which can keep confidential cloud computing from reach its potential. With my advisor (Prof. Edouard Bugnion), colleagues at EPFL and collaborators at Microsoft Research Cambridge, we are trying to rethink the solution by keeping the entire systems stack in perspective. To this end, we are building a versatile isolation monitor which provides a new system abstraction of trust domains. Trust domains are isolated orthogonally to existing system abstractions and privilege hierarchies. The isolation monitor, called Tyche (the Greek goddess of fate, some say Tyche lets "good things happen"), leverages existing hardware security primitives to isolate trust domains. For instance, Intel VT-x on x86 and PMPs on RISC-V. I am personally responsible for the development of Tyche on RISC-V for QEMU and StarFive VisionFive2. If you find this interesting, check out our [HotOS 2023 paper](https://dl.acm.org/doi/abs/10.1145/3593856.3595900).  

A root of trust (RoT) is needed to establish trust in a privileged isolation monitor like Tyche. A dynamic RoT can help exclude the platform firmware, that runs in the same privileged mode as the monitor, from the trusted compute base (TCB). Unfortunately, existing solutions still include such firmware in the static root of trust chain, because there is no way to isolate the software executing in privileged modes like EL3/M-mode/SMM/etc. Instead of falling down the same rabbit hole of introducing a new privilege mode, we are designing ISA extensions to isolate M-mode software which can enable DRoT in RISC-V with a minimal TCB. If root of trust also interests you, I summarize the existing work and discuss the future trends in this field in my [SOSP 2023 doctoral workshop paper](https://drive.google.com/file/d/1sH3dWik4bU6BGEwlTeFY4uQ2dEFqH5jI/view?usp=sharing). 

Trusted runtimes are often overprivileged which can lead to Iago attacks. We worked on minimizing their privileges to harden the security guarantees towards the security sensitive applications, essentially enforcing the least privilege principle. To do this, we proposed an extension to RISC-V PMP; and evaluated it using the Keystone TEE framework. Check out our paper at [SysTEX 2023](https://dl.acm.org/doi/10.1145/3578359.359304) for more details.  

<hr style="height:2px;border-width:0;color:gray;background-color:gray">

### Internship at IBM Research, Zurich 

During my internship at IBM Research, Zurich, I worked on improving the security of context switch code in privileged software by gathering ISA-level insights from the formal specification of the ISA written in machine-readable Sail. The Sail model is officially adopted as the ground-truth ISA specification by the RISC-V foundation. We leverage Sail to automatically extract which ISA-level state is security-sensitive and must be cleared appropriately during the context switch implementation. If you are interested to learn more, check out our Usenix Security '25 paper <a href="https://arxiv.org/abs/2502.06609">here</a>.

### Internship at Intel Labs, Bangalore

During my internship at Intel Labs, Bangalore, with my manager Dr. Niranjan Soundararajan, I worked on optimising different parts of the processor pipeline. We improved front-end throughput with enhancements to the micro-op cache. Check out our [patent](https://patents.google.com/patent/US20230103206A1/en) for more details. We also worked on optimising the performance of loads and stores in the processor pipeline. Check out our patent [here](https://patents.google.com/patent/US20230418757A1/en).   

<hr style="height:2px;border-width:0;color:gray;background-color:gray">

### Hardware Cache Prefetching

My master's thesis, supervised by Dr. Biswabandan Panda, revolved around hardware cache prefetching. It was funded by the semiconductor research corporation (SRC) and liaisoned by Intel Labs, Bangalore. We proposed a novel mechanism to identify critical instructions using ROB occupancy and prefetch only for those to reduce energy consumption in the memory subsystem while retaining performance. Check out our [IEEE CAL paper](https://research.ece.ncsu.edu/wp-content/uploads/sites/19/2020/05/JIP.pdf) for more details. 

We also participated in the instruction prefetching championship colocated with ISCA 2020 and [our paper](https://research.ece.ncsu.edu/wp-content/uploads/sites/19/2020/05/JIP.pdf) had the 5th best performing instruction prefetcher. 
</div>
