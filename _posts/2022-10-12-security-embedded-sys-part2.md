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

![picture-attackscenarios](/img/posts/security-embedded-sys/attackscenarios.png)


## Invasive attacks

If the attacker has access to the hardware of an embedded system and tries to modify its behavior or to gather information this is called an invasive attack. Invasive attacks are splitted into logical and physical attacks.

#### >> Countermeasures against logical invasive attacks

In order to protect a system against execution of injected code we know at least three different approaches:  
- Canary words
- Control flow checking
- Masking the stack non-executable

So called *canary words* are often placed between the local variables and the return address in the stack. If an attacker tries to manipulate the return address (i.e. by buffer overflow) in order to jump to injected code he or she also overwrites the canary word. Before the jump to the return address is executed the canary can be checked. If its value is different compared to its original value we know someone tries to attack the system. But canaries can also be placed in front of registers, the stack pointer or heap segment headers.

Another countermeasure is *control flow checking*. By previous analysis of the code the operating system can monitor its execution. Therefor the code is splitted into nodes which can either be commands or so called basic blocks. If injected code is executed it does not fit in one of the previously as possible noted control flows. The attack is detected.  



#### >> Countermeasures against physical invasive attacks

Physical invasive attacks can be prevented with at least following methods:
- Low frequency sensor
- Restricted program counter
- Destruction of test circuitry
- Top-layer sensor mesh
- IP watermarking

 

However, if the dimensions are smaller than the wavelength of visible light a optical microscope doesn't work anymore. The solutions are beam technologies. Three types are known:
- *Focused Ion Beam (FIB)*  
        Precisely shooting Gallium ions on the chips surface in a vacuum chamber peels of secondary particles (positive, negative ions and electrons). These can be detected and the chip structure then be modeled. Using ion beam technology structures down to 5nm can be scanned.  
        
- *Electron Beam Tester (EBT)*  
        EBTs are so called Scanning Electron Microscopes (SEM) combined with a voltage-contrast function. With this technology signals can be observed too. Therefor the clock frequency has to be reduced below 100 kHz. This is not always possible and can be used as a countermeasure to this attack.  

- *Infrared Laser*  
        Because of the silicon substrate being transparent when observed with infrared laser a chip can be scanned from the rear using this technology. Also the photon current corresponds to the internal states of transistors so signals can be observed and memory cells can be read out.  


## Non-invasive attacks

Non-invasive attacks mostly don't modify the hard- and software but rather try to gather information and to get system access.  

#### >> logical non-invasive attacks

Logical invasive attacks can be categorized in:
- *Authenticity forging*  
        The authenticity of someone can be forged using attacks like phishing or DNS spoofing.  

- *Exploit of cryptographic weaknesses*  
        I.e. brute force attacks or attacks using information leakage of bad cryptographic designs like WEP which has been used in WiFi networks.  

- *Copying*  
        Copying of programs and intelectual property ("IP cores").  



#### >> physical non-invasive attacks

As mentioned above non-invasive attacks do not modify hard- or software. Physical non-invasive attacks are for example:

- *Side-channel attacks*  
        During data processing information can be leaked unintentionally. Side channels are i.e. the power consumption, temperature, sound etc.  
        An example for a side channel attack is the "Correlation Power Analysis" (CPA) attacking an AES implementation. By sampling traces of the power consuption
        during AES encryption (or decryption) one is able to retrieve the used key. 

- *Eavesdropping*  
        For example listening on an unenrypted communication and waiting for a password beeing exchanged.  

## Coming next...
Part two of "Security in embedded systems" will cover countermeasures against the attack scenarios described above.


## Further information
- [Ultimate Guide to Embedded Systems Security](https://blackberry.qnx.com/en/ultimate-guides/embedded-system-security)
