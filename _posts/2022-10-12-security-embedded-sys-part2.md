---
layout: post
title: "Security in embedded systems"
subtitle: "Part 2: Countermeasures"
background: '/img/posts/security-embedded-sys/head_image.jpg'
---

## Security in embedded systems
Embedded systems are present everywhere in our society. Smart coffee machines in our private life as well as smart production processes in Industry 4.0: So called "smart systems" get connected by the Internet of Things (IoT) and bring cool features we don't want to miss anymore. Of course this also generates possible attack vectors we have to know and to discuss about. Security in embedded systems is a combined matter of hardware-security and software-security. It has to be considered from the very first beginning of designing a system. This is part two of this series. While part one was all about attack scenarios on embedded systems part two covers possible countermeasures against them.  

## Part 2: Countermeasures
In [part one](https://www.simon-cybersec.com/2022/07/06/security-embedded-sys-part1.html) we learned about the different scenarios attacks can be categorized in. This image is a great visualization we can utilize to discuss the different countermeasures.  

![picture-attack-scenarios](/img/posts/security-embedded-sys/attackscenarios.png)


## Invasive attacks

If the attacker has access to the hardware of an embedded system and tries to modify its behavior or to gather information this is called an invasive attack. Invasive attacks are devided into logical and physical attacks.

#### >> Countermeasures against logical invasive attacks

In order to protect a system against execution of injected code we know at least three different approaches:  
- Canary words
- Control flow checking
- Masking the stack non-executable

So called *canary words* are often placed between the local variables and the return address in the stack. If an attacker tries to manipulate the return address (i.e. by buffer overflow) in order to jump to injected code he or she also overwrites the canary word. Before the jump to the return address is executed the canary can be checked. If its value is different compared to its original value we know someone tries to attack the system. But canaries can also be placed in front of registers, the stack pointer or heap segment headers.

Another countermeasure is *control flow checking*. By previous analysis of the code the operating system can monitor its execution. Therefor the code is devided into nodes which can either be commands or so called basic blocks. If injected code is executed it does not fit in one of the previously as possible noted control flows. The attack is detected.  



#### >> Countermeasures against physical invasive attacks

Physical invasive attacks can be defended using following methods:
- Low frequency sensor
- Restricted program counter
- Destruction of test circuitry
- Top-layer sensor mesh
- IP watermarking

A *low frequency sensor* is a possible countermeasure against an Electron Beam Tester ("EBT") trying to observe signals. EBTs can observe signals below 100 kHz. The sensor can detect if the frequency is below a certain threshold and if so for example a reset can be triggered.

A *restricted program counter* consists of an segment address and an offset. The segment is not allowed to change. If the offset increases and an overflow happens the offset gets reset. This can protect the systems memory content from being completely read by manipulation of the program counter.

After a PCB has been produced in factory it also has to be tested. Often circuitry is included on the board for automated testing. The *destruction of this test circuitry* can prevent from attackers using it later. 

A *top-layer sensor mesh* can detect if an attacker tries to get access to underlying layers in a chip.

*IP watermarking* is the attempt to identify your own IP core in a different FPGA design of someone who illegaly copied it. It is done by hiding a unique singature in your IP core, i.e. utilizing unused memory space of LUTs. However, it is still part of research.  


## Non-invasive attacks

Non-invasive attacks mostly don't modify the hard- and software but rather try to gather information and to get system access.  

#### >> Countermeasures against non-invasive attacks

Possible countermeasures against non-invasive attacks are:
- Encryption
- Watermarking
- Unique identification of the execution site
- Social protection

The first two points are probably clear. Watermarking has been described above. In order to uniquely identify the execution site different approaches exist:
- MAC address
- USB dongle
- TPM module board
- Embedded unique key
- Physical unclonable function

While the MAC address can easily be changed a USB dongle or trusted platform module (TPM) are more secure. In FPGAs unique keys can be added which then are checked before code execution. Similar to that physical unclonable functions (PUF) are executed on a board before the actual code. If the return value is not the expected one the code does not get executed.

A challenge in cybersecurity is social engineering. Attackers try to forge authenticity using for example phishing emails deceiving people. Companies must teach their employees regularly. Besides that multi-factor authentication often prevents attacks from beeing successful.  


## Further information
- [Security in embedded systems: Attack scenarios](https://www.simon-cybersec.com/2022/07/06/security-embedded-sys-part1.html)
