## What is an operating system?
- An operating system (**OS**) is software that **manages computer hardware** and **provides a platform for running applications**
    
- It provides **an interface between the user and the hardware** in a computer system
    
- It **hides the complexities of the hardware** from the user, for example:
    
    - A user does not need to know 'where' on secondary storage data is kept, just that it is saved for when they want it again
        
- An operating systems **main functions** can be divided in to **eight** key areas
    
## File Management
### What is file management?
- File management is a process carried out by the operating system **creating, organising, manipulating and accessing files and folders on a computer system**
    
- The OS **manages where data is stored** in both **primary and secondary** **storage**
    
- File management gives the user the ability to:
    
    - **Create files/folders**
        
    - **Name files/folders**
        
    - **Rename files/folders**
        
    - **Copy files/folders**
        
    - **Move files/folders**
        
    - **Delete files/folders**
        
- The OS allows users to control who can access, modify and delete files/folders (**permissions**)
    
- The OS provides a **search facility** to find specific files based on various criteria
    
## Handling Interrupts
#### What is interrupt handling?
- Interrupt events **require the immediate attention** of the **central processing unit**
    
- In order to maintain the smooth running of the system, interrupts need to be **handled** and processed **in a timely manner**
    
- For example, if a user clicks cancel on a file conversion process, a signal is sent from the mouse, **interrupts the processor**, and the operating system will trigger the cancellation routine
![[截屏2025-02-16 17.57.33.png]]
## User Interface
### What is a user interface?
- A user interface is **how the user interacts with the operating system**
- Examples of user interfaces include:
    - **Command Line Interface (CLI)**
    - **Graphical User Interface (GUI)**
    - **Menu**
    - **Natural language (NLI)**
![Graphic showing visual differences between CLI and GUI](https://cdn.savemyexams.com/cdn-cgi/image/f=auto,width=3840/https://cdn.savemyexams.com/uploads/2024/03/purpose-and-functionality-of-the-os-.png)
#### What is a command line interface?
- A Command Line Interface (**CLI**) requires users to interact with the operating system using **text based commands**
    
- CLIs are more commonly used by **advanced users**
    
- Examples of CLIs are MSDOS (Microsoft Disk Operating System) and Raspbian (for Raspberry Pi)
    
#### What is a graphical user interface?
- A Graphical User Interface (**GUI**) requires users to interact with the operating system using **visual elements** such as windows, icons, menus & pointers (**WIMP**)
    
- GUIs are **optimised for mouse and touch gesture input**
    
- Examples of GUIs are Windows, Android and MAC OS
        
#### What is a natural language interface?
- A natural language interface (**NLI**) uses the spoken word to respond to spoken or textual inputs from a user
    
- Examples include
    
    - **Virtual assistants** - Amazon Alexa, Google Assistant, Siri
        
    - **Search engines**
        
    - **Smart home devices**

![[截屏2025-02-16 17.39.20.png]]
        
### Advantages and disadvantages of user interfaces
|**Interface**|**Advantages**|**Disadvantages**|
|---|---|---|
|Command line (**CLI**)|- Uses less system resources<br>    <br>- Useful for automation of tasks<br>    <br>- Commands are often faster to type than navigating menus|- Requires users to remember commands<br>    <br>- Typing errors are common<br>    <br>- Less intuitive than GUI|
|Graphical (**GUI**)|- Intuitive and user-friendly<br>    <br>- Requires no previous knowledge to use<br>    <br>- Information is visual, making it easier to understand|- Uses more system resources<br>    <br>- Can be slower to find and execute commands<br>    <br>- Can be frustrating when doing repetitive tasks|
|Menu|- Simplicity<br>    <br>- Efficiency|- Limited flexibility<br>    <br>- Accessibility issues|
|Natural language (**NLI**)|- Can be used by people with disabilities<br>    <br>- Intuitive|- Not always reliable<br>    <br>- Privacy concerns|
## Peripheral Management & Device Drivers
### What is peripheral management?
- Peripheral management is a process carried out by the operating system **managing the way** **peripherals** **(hardware) interact with software**
    
- The OS **allocates system resources** to peripherals to ensure **efficient operation**
    
- Peripheral management makes **plug-and-play** (PnP) functionality possible, **automatically detecting and configuring new peripherals** without the need for manually installing device drivers or power cycling the system
    
### What is a device driver?
- A device driver is **a piece of software used to control a piece of hardware**
    
- Peripherals **require device drivers** in order to be used by the operating system
    
- The OS has **generic device drivers built in** which makes **basic compatibilit**y possible and enables **plug-and-play** (PnP)
    
- In order for hardware to be used to its **maximum capacity**, often **a separate device driver must be downloaded** from the manufacturer
    
- Device drivers are **OS specific** and are **regularly updated**
    
## Memory Management & Multitasking
### What is memory management?
- Memory management is a process carried out by the operating system **allocating main memory (RAM) between different programs** that are **open at the same time**
    
- The OS is responsible for **copying programs and data from secondary to primary storage** as it is needed
    
- **Programs and data require different amounts of RAM** to operate efficiently and the OS manages this process
    
- **RAM is allocated** based on **priority and fairness**, for example, system applications (essential) may have a higher priority than user applications
    
- The OS **dynamically manages the memory**, adjusting allocation as needed to maintain optimal system performance
    
- Memory management makes **multitasking** possible
    
### What is multitasking?
- Multitasking is a process made possible by the OS **simultaneously managing system resources** (memory, CPU etc) to give a user the **perception of being able to use multiple programs at the same time**
    
- The OS **splits tasks and allocates system resources** based on a priority
    
- The CPU can only **execute one instruction at a time**, it can can execute billions of them in one second.
    
- This makes it **appear that multiple programs are running at the same time**
    
