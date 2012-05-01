---
layout: post
title: Future of Computers - Virtual Machines
---

<p>
	My CS professor Gustavo Rodriguez was talking about virtual machines (VM) in detail today in my OS class. What is a virtual machine ? It is a completely isolated OS within another host OS. You can find many instances of VMs running in a single host. One of the main advantages of using VMs is that you can take a 'snapshot' (i.e. a huge chunk of memory) of an OS <i>including</i> the applications it has installed. You can then save and duplicate the VM in another machine altogether!
</p>
<p>
	This has great implications, if a system-breaking virus has inflicted your VM, you can reload it from a snapshot that has been saved previously, effectively rolling back till you get back to a stable state to continue your work!
</p>
<p>
	This allows you to:
</p>
<ul>
	<li>Test programs in multiple OS versions without the need for multiple computers</li>
	<li>Simplify administration of programs since the administrator can install programs in one VM and duplicate that across many machines</li>
</ul>
<p>
	<a href="http://www.citrix.com/" target="_blank">Citrix</a> and <a href="http://www.vmware.com/" target="_blank">VMware</a> are companies that are leading in this virtualization technology.
</p>
<p>
	What hasn't really been mentioned though, is the effective business model of selling a bare-bone computer model for a really competitive price to the mass public, and letting the machine run a VM from a selection of VMs from the company's web servers. This would be kind of like Amazon's strategy of Kindle Fire - selling hardware for a really competitively cheap price, and gaining profits from the software sold. Currently Citrix has a product called <a href="http://www.citrix.com/xendesktop/overview" target="_blank">Xen Desktop</a> that does this on a corporate level, but it's not applicable to the mass public.
</p>
<p>
	This concept requires a combination of fast (much better than current 1 Gbps), stable and widely available (4G networks) internet connection that is not yet present currently. This scenario would change in the next few years though, and I believe we can expect a prominent IT company to come with this integrated product!
</p>