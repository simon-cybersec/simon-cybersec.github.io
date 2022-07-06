---
layout: post
title: "Security in embedded systems"
subtitle: "Part 1: Attack scenarios"
background: '/img/posts/security-embedded-sys/head_image.jpg'
---

## Security in embedded systems
Embedded systems are present everywhere in our society. From the intelligent coffee machine as an example in our private life to a smart production process in Industry 4.0. So called "smart systems" get connected by the Internet of Things (IoT) and bring cool features we don't want to miss anymore. Of course this also generates possible attack vectors we have to know and discuss about. Security in embedded Systems is a combined matter of security in hardware and security in software. It has to be considered from the first beginning of designing a system.  

## Attacks on embedded systems
Do you remember the [three main goals of cybersecurity](https://www.simon-cybersec.com/2022/06/02/cybersecurity-goals.html)?
Confidentiality, integrity and availability - easy to remember using the "CIA" abbreviation. In embedded systems attack scenarios to compromise these goals can be categorized as follows:  

- invasive attacks  
        - logical  
        - physical  
- non-invasive attacks  
        - logical  
        - physical  



## Invasive attacks

With invasive attacks one gets hands on with the hardware and try to modify it in order to change its behaviour or to gather information. Of course therefore one has to have access to the hardware. As mentioned above invasive attacks are splitted into logical and physical attacks.

#### >> logical invasive attacks

These are targeting the integrity and confidentialty of a system. For example, using code injection an attacker is able to control an embedded system and therefore is able to read out data and to change its data and behaviour.  

#### >> physical invasive attacks

Physical invasive attacks are targeting all of the three CIA-goals. One could simply damage a device which compromises its availability. But more interesting, using special equipment one is able to read and to manipulate data and hardware circuits targeting confidentiality and integrity.

## Non-invasive attacks

Non-invasive attacks don't modify the hardware but rather try to gather information or to get access using other channels.



## Further information
- [Ultimate Guide to Embedded Systems Security](https://blackberry.qnx.com/en/ultimate-guides/embedded-system-security)
