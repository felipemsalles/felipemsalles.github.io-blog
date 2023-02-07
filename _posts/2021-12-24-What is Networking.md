---
title: "Try Hack Me - What is Networking?"
categories:
  - CTF
---

Walkthrough of the room What is Networking on TryHackMe. Let's go!

## Task 1: What is Networking?

![](https://blogfelipe.com/assets/images/wnet-01.png)

What is the key term for devices that are connected together?

Well, if you want to send a message to a friend, connect to other people, what do you need? A network, something capable of connecting devices. So, our answer is Network.

### Task 2: What is the Internet?

Who invented the World Wide Web? 

You can read more about the history here: https://webfoundation.org/about/vision/history-of-the-web/

The Answer is: Tim Berners-Lee

## Task 3: Identifying Devices on a Network

What does the term "IP" stand for?
Answer: Internet Protocol

What is each section of an IP address called?
Answer: octet

How many sections (in digits) does an IP address have?
Answer: 4

What does the term "MAC" stand for?
Answer: Media Access Control

Deploy the interactive lab using the "View Site" button and spoof your MAC address to access the site.  What is the flag?

The first step is to click on “View website”. As you probably noticed, when you click on “request site” Bob’s blue ball goes to the bin, and not to Try Hack Me as Alice. How do we solve it? Well, if you look at Alice, she is communicating successfully, but Bob can’t do it with his MAC Address. So, you only need to switch to her MAC Address and “request site” to get the flag.

Answer: THM{YOU_GOT_ON_TRYHACKME}

### Task 4: Ping (ICMP)

What protocol does ping use? 	
Answer: ICMP

What is the syntax to ping 10.10.10.10?
Answer: ping 10.10.10.10

What flag do you get when you ping 8.8.8.8?
Click on “view site” and insert the IP Address to send the request “8.8.8.8”. You will get the flag!

Answer: THM{I_PINGED_THE_SERVER}

### Task 5: Continue your learning: Intro to Lan

Conclude the task and continue your journey to the next room!
Thank you!
