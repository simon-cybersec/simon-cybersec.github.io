---
layout: post
title: "Security in embedded systems"
subtitle: "Part 1: Attack scenarios"
background: '/img/posts/security-embedded-sys/head_image.jpg'
---

## Security in embedded systems
Embedded systems are present everywhere in our society. Smart coffee machines in our private life as well as smart production processes in Industry 4.0: So called "smart systems" get connected by the Internet of Things (IoT) and bring cool features we don't want to miss anymore. Of course this also generates possible attack vectors we have to know and to discuss about. Security in embedded systems is a combined matter of hardware-security and software-security. It has to be considered from the very first beginning of designing a system. This is going to be a two part article. While part one is about attack scenarios on embedded systems part two will cover possible countermeasures against them.  

## Part 1: Attacks on embedded systems
In the first post we discussed the [three main goals of cybersecurity](https://www.simon-cybersec.com/2022/06/02/cybersecurity-goals.html):
Confidentiality, integrity and availability - easy to remember using the "CIA" abbreviation. Attack scenarios to compromise these can be categorized as shown in the following graphic:  

![picture-attack-scenarios](/img/posts/security-embedded-sys/attackscenarios.png)


## Invasive attacks

With invasive attacks one gets hands on with the hardware and tries to modify it in order to change its behavior or to gather information. Of course therefore one has to have access to the hardware. As mentioned above invasive attacks are devided into logical and physical attacks.

#### >> Logical invasive attacks

Logical invasive attacks are targeting the integrity and confidentiality of a system. Mostly known as code injection attacks an attacker firstly inserts own code in memory and secondly triggers its execution. If succeeded one is able to control the system and therefore is able to read out data as well as changing data and behavior. But it is important to note that code injection is not always necessary. It has been prooved that by using return oriented programming it is possible to craft malicious routines without the injection of code.  

#### >> Physical invasive attacks

Physical invasive attacks are targeting all of the three CIA-goals. Availability is compromised if one simply damages a device . But more interesting, using special equipment one is able to read and to manipulate data as well as hardware circuits which compromises confidentiality and integrity.  
The dimensions of recent technologies are very small and the needed equipment can be expensive. This can make physical invasive attacks difficult to conduct. However, if money is not the problem the first step of such an attack is the depacking where one opens the device or chip in order to get access to its inner electronics or physical layers.  
If one wants to attack a chip the next step is to reconstruct its layout. Therefore one can use an optical microscope by analyzing layer by layer. By decoding the connections of the diffusion layers one can read out ROM content. Using manual micro-probing also signals can be observed, however very small probes in dimensions of micrometers are needed. and most of the time the top layer is protected by a passivation layer which has to be removed first.
If the layout has been reconstructed a netlist can be simulated and its functionality then be analyzed. An attacker could for example now clone and sell this device.  

However, if the dimensions are smaller than the wavelength of visible light a optical microscope doesn't work anymore. The solutions are beam technologies. Three types are known:
- *Focused Ion Beam (FIB)*  
        Precisely shooting Gallium ions on the chips surface in a vacuum chamber peels of secondary particles (positive, negative ions and electrons). These can be detected and the chip structure then be modeled. Using ion beam technology structures down to 5nm can be scanned.  
        
- *Electron Beam Tester (EBT)*  
        EBTs are so called Scanning Electron Microscopes (SEM) combined with a voltage-contrast function. With this technology signals can be observed too. Therefor the clock frequency has to be reduced below 100 kHz. This is not always possible and can be used as a countermeasure to this attack.  

- *Infrared Laser*  
        Because of the silicon substrate being transparent when observed with infrared laser a chip can be scanned from the rear using this technology. Also the photon current corresponds to the internal states of transistors so signals can be observed and memory cells can be read out.  


## Non-invasive attacks

Non-invasive attacks mostly don't modify the hard- and software but rather try to gather information and to get system access.  

#### >> Logical non-invasive attacks

Logical invasive attacks can be categorized in:
- *Authenticity forging*  
        The authenticity of someone can be forged using attacks like phishing or DNS spoofing.  

- *Exploit of cryptographic weaknesses*  
        I.e. brute force attacks or attacks using information leakage of bad cryptographic designs like WEP which has been used in WiFi networks.  

- *Copying*  
        Copying of programs and intelectual property ("IP cores").  



#### >> Physical non-invasive attacks

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
