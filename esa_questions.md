# ESA 4 markers and above possible questions:

## Unit 1:

## Unit 2:

### Conceptual Questions:

1) Explain the concept of virtualization and its significance in cloud computing.

Ans:

- Vistualization is the process of abstracting the hardware layer such as physical resources into a logical view.
- It enables applications to operate independently of the hardware
- It is a fundamental technology in cloud computing as it facilitates resource sharing acrosss multiple servers.
- It enables VMs which allow efficient management of compute resources.
- The logical representation of resources allows for better resource allocation and management.

2) Differentiate between Type 1 and Type 2 hypervisors with examples.

Ans:

**Type 1 - Bare Metal**

- Type 1 hypervisors run directly on the physical hardware.
- It has better performance and efficiency.
- Manage hardware resources directly.
- Do not require a host operating system.
- Less overhead
- Strong isolation and security
- Example: Xen, Microsoft Hyper-V

**Type 2 - Hosted**

- Type 2 run on top of a host OS.
- Less performance and less efficient
- Do not manage resources directly, instead indirectly
- Requires a host OS
- More overhead
- less secure due to their reliance on the host OS
- Easy to use
- Example: VMware Workstation, Virtualbox

3) What are the requirements of a Virtual Machine Monitor (VMM)?

Ans:

- VMMs ensure that the virtual environment closely resembles the physical machine to maintain performance.
- Must not allow the VM to directly access the physical resources.
- Must virtualise and allocate memory and virtual memory efficiently
- Trap and translate sensitive instructions given by the VM
- Ensure that a performance close to the native resources is being achieved.

### Diagram/Architecture:

1) Draw and explain the architecture of a Type 1 and Type 2 hypervisor.

Ans:

2) Describe the components of VMware ESX Server using a diagram.

Ans:

### Scenario-Based:

1) Suppose you are deploying VMs for different OSs on the same physical hardware. Which virtualization technique will you use and why?

### Analytical:

1) Compare full virtualization and paravirtualization with pros and cons.

2) Explain how paravirtualization handles memory management with reference to Xen.

## Unit 3:

## Unit 4: