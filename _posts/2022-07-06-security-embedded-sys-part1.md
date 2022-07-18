---
layout: post
title: "Security in embedded systems"
subtitle: "Part 1: Attack scenarios"
background: '/img/posts/security-embedded-sys/head_image.jpg'
---

## Security in embedded systems
Embedded systems are present everywhere in our society. From the intelligent coffee machine as an example in our private life to a smart production process in Industry 4.0. So called "smart systems" get connected by the Internet of Things (IoT) and bring cool features we don't want to miss anymore. Of course this also generates possible attack vectors we have to know and discuss about. Security in embedded Systems is a combined matter of security in hardware and security in software. It has to be considered from the first beginning of designing a system.  

## Attacks on embedded systems
In the first post we discussed the [three main goals of cybersecurity](https://www.simon-cybersec.com/2022/06/02/cybersecurity-goals.html):
Confidentiality, integrity and availability - easy to remember using the "CIA" abbreviation. In embedded systems attack scenarios to compromise these goals can be categorized as shown in the following graphic:  

![picture-attackscenarios](/img/posts/security-embedded-sys/attackscenarios.png)


## Invasive attacks

With invasive attacks one gets hands on with the hardware and try to modify it in order to change its behaviour or to gather information. Of course therefore one has to have access to the hardware. As mentioned above invasive attacks are splitted into logical and physical attacks.

#### >> logical invasive attacks

These are targeting the integrity and confidentialty of a system. An example of an logical invasive attack is a code injection attack. An attacker firstly inserts own code in memory and secondly triggers its execution. When succeeded one is able to control the embedded system and therefore is able to read out data as well as changing data and behaviour.  

#### >> physical invasive attacks

Physical invasive attacks are targeting all of the three CIA-goals. One could simply damage a device which compromises its availability. But more interesting, using special equipment one is able to read and to manipulate data as well as hardware circuits which compromises confidentiality and integrity.  
The dimensions of recent technologies are very small and the needed equipment can be expensive. This can make physical invasive attacks difficult to conduct. However, if money is not the problem the first step of such an attack is the depacking where one opens the chip in order to get access to its electronics layers.  
The next step is to reconstruct the layout of the chip. Therefore one can use an optical microscope analyzing layer by layer. When standardized architectures and ASIC cells are used this helps to identify modules. Also one can read out the content of the ROM by decoding the connections of the diffusion layers.  
Using manual micro-probing the signals can be observed. The shaft thickness of a probe has to be around 10 um and its tip around 0.1 um. Most of the time the top layer is protected by a passivation layer which has to be removed before.
If the layout has been reconstructed a netlist can be simulated and its functionality be analyzed. An attacker could for example clone and sell this device.  

However, if the dimensions are smaller than the wavelength of visible light a optical microscope doesn't work anymore. The solutions are beam technologies. Three types are known:
- *Focused Ion Beam (FIB)*  
        Precisely shooting Gallium ions onto chip surface in a vacuum chamber peels of secondary particles (positive, negative ions and electrons). These can be detected and with them the chip structure remodelled. Using ion beam technology structures down to 5nm can be scanned.  
        
- *Electron Beam Tester (EBT)*  
        EBTs are so called Scanning Electron Microscopes (SEM) together with a voltage-contrast function. The energy of the secondary particles correspond to the electrick field. Also with this technology signals can be observed. But therefor the clock frequency has to be reduced below 100 kHz. This is not allways possible and can be used as a countermeasure to this attack.  

- *Infrared Laser*  
        Because of silicon substrate being transparent in the infrared wavelength range a chip can be scanned from the rear using an infrared laser. Also the photon current corresponds to the intenal states of transistors so signals can be observed and memory cells can be read out.  


## Non-invasive attacks

Non-invasive attacks don't modify the hardware but rather try to gather information or to get access using other channels.


## Further information
- [Ultimate Guide to Embedded Systems Security](https://blackberry.qnx.com/en/ultimate-guides/embedded-system-security)
