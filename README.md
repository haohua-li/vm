# Virtual Machine

## WSL2 
WSL2 已经用上了 HyperV , WSL2 的内核是开源的，可以对比一下与 Linux Kernel 的区别。

https://github.com/microsoft/WSL2-Linux-Kernel


## 参考书

*[Intel® 64 and IA-32 Architectures Software Developer’s Manual, Volume 3A: System Programming Guide, Part 1](https://www.intel.com/content/dam/www/public/us/en/documents/manuals/64-ia-32-architectures-software-developer-vol-3a-part-1-manual.pdf)*

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

[Release RELEASE-2.0.0: bitkeeper revision 1.1159.1.385 (418b582ajt_xRJBZ_QltlCQBhLkgkQ) · xen-project/xen (github.com)](https://github.com/xen-project/xen/releases/tag/RELEASE-2.0.0)

推荐从低版本开始看源码，因为最新的代码一般都看不懂。

[paper.dvi (cam.ac.uk)](https://www.cl.cam.ac.uk/research/srg/netos/papers/2003-xensosp.pdf)

[HowDoesXenWork.pdf (xenproject.org)](http://www-archive.xenproject.org/files/Marketing/HowDoesXenWork.pdf)

[xen_interface.pdf (xenproject.org)](http://www-archive.xenproject.org/files/xen_interface.pdf)

[Xen - Gentoo Wiki](https://wiki.gentoo.org/wiki/Xen)

### Hyper-V 

[vmbus 分析 一 – 夕月阁 (tecyle.com)](http://www.tecyle.com/2019/06/01/vmbus-分析/)

[vmbus 分析二 – 夕月阁 (tecyle.com)](http://www.tecyle.com/2019/06/01/vmbus-分析二/)

[Hyper-V - Gentoo Wiki](https://wiki.gentoo.org/wiki/Hyper-V)

