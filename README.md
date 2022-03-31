# Virtual Machine

## 参考书

*Virtual machines versatile platforms for systems and processes* by Smith J.E., Nair R.

*Advanced Design and Implementation of Virtual Machines* by Xiao-Feng Li 

*Virtualization Essentials* by Matthew Portnoy

## Warmup

[Virtual Machines - red key concepts: virtualization, hypervisors (uwaterloo.ca)](https://student.cs.uwaterloo.ca/~cs350/F19/notes/wrapup-1up.pdf)

> Can the VM disable interrupts on the physical CPU? Should it be able to?

[Masum Z Hasan, PhD - Hypervisor-based Virtualization (google.com)](https://sites.google.com/site/masumzh/articles/hypervisor-based-virtualization?authuser=0)

[Masum Z Hasan, PhD - X86 Architecture Basics (google.com)](https://sites.google.com/site/masumzh/articles/x86-architecture-basics-1?authuser=0)

### Hypervisor

[Virtualization Explained - YouTube](https://www.youtube.com/watch?v=FZR0rG3HKIk&t=208s)

[Cloud Computing and Virtualization | Mainstream Computer Virtualization - YouTube](https://www.youtube.com/watch?v=MaOHNG8MlEo)

[Computing virtualization | CPU Virtualization | Memory Virtualization | I/O Virtualization - YouTube](https://www.youtube.com/watch?v=A3qvxIgrhgY)

- Type 1 (“bare-metal” hypervisor)
  - Xen, KVM, acrn, Hyper-V 
  - (这类虚拟机都有一个特点, 在 `/arch/x86/kernel/cpu/` 搜索 `irq_hv_callback_count` 的 usage 都能找到， 而这个中断次数跟一个叫 hypervisor callback function 的函数有关) 
  - 由于 Hyper-V 是闭源的，要研究只能从 Xen 入手 ( KVM 由于没有 IO 的虚拟化)
- Type 2 : 
  - Oracle Virtual Box

---

## 源码分析

### Xen

[paper.dvi (cam.ac.uk)](https://www.cl.cam.ac.uk/research/srg/netos/papers/2003-xensosp.pdf)

[HowDoesXenWork.pdf (xenproject.org)](http://www-archive.xenproject.org/files/Marketing/HowDoesXenWork.pdf)

[xen_interface.pdf (xenproject.org)](http://www-archive.xenproject.org/files/xen_interface.pdf)

[Xen - Gentoo Wiki](https://wiki.gentoo.org/wiki/Xen)

### Hyper-V 

[vmbus 分析 一 – 夕月阁 (tecyle.com)](http://www.tecyle.com/2019/06/01/vmbus-分析/)

[vmbus 分析二 – 夕月阁 (tecyle.com)](http://www.tecyle.com/2019/06/01/vmbus-分析二/)

[Hyper-V - Gentoo Wiki](https://wiki.gentoo.org/wiki/Hyper-V)

