---
layout: post
title: Future of Computers - Virtual Machines
---

My CS professor Gustavo Rodriguez was talking about virtual machines (VM) in detail today in my OS class. What is a virtual machine ? It is a completely isolated OS within another host OS. You can find many instances of VMs running in a single host. One of the main advantages of using VMs is that you can take a 'snapshot' (i.e. a huge chunk of memory) of an OS <i>including</i> the applications it has installed. You can then save and duplicate the VM in another machine altogether!

This has great implications, if a system-breaking virus has inflicted your VM, you can reload it from a snapshot that has been saved previously, effectively rolling back till you get back to a stable state to continue your work!