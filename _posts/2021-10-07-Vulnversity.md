---
title: "Try Hack Me - Vulnversity"
categories:
  - CTF
---

Walkthrough of the room Vulnversity on TryHackMe. Let's go!

![](https://blogfelipe.com/assets/images/vulnversity-01.png)

## Task 1: Deploy the machine

In this task, you just need to deploy the machine. If you don’t know how to do it, please check my other article about OpenVPN to continue. If you know, deploy the machine and answer the task. Let’s continue!

### Task 2: Reconnaissance

In task 2, you will see a table containing some great functionalities of Nmap. Nmap is a tool used by a lot of professionals and students to scan and discover hosts or services on a computer network. You should get a notebook or write somewhere some flags. Now, let’s answer the questions.
1-There are many nmap “cheatsheets” online that you can use too.
No Answer is needed (just copy the flags somewhere as I said earlier).
2-Scan the box, how many ports are open?
To know HOW MANY ports are open, we can run: nmap -sV< IP ADDRESS> to see the services running.

![](https://blogfelipe.com/assets/images/vulnversity-02.png)

If you pay attention, you will see that 994 ports are closed. But, we have 6 ports OPEN.

Answer = 6

3-What version of the squid proxy is running on the machine?

Remember that if we use -sV flag we can determine the version of the services running? So let’s check it. We have 6 ports open and one of them is the http proxy service (3128). As you can see in the last column, nmap shows the version of the service and if you look, you will see the version of squid http proxy: 3.5.12

Answer: 3.5.12

![](https://blogfelipe.com/assets/images/vulnversity-03.png)

4-How many ports will nmap scan if the flag -p-400 was used?

Well, let’s see!

Run:

```bash
nmap -p-400<ip address>
```

![](https://blogfelipe.com/assets/images/vulnversity-04.png)

We can see 397 ports closed and 3 still open. So, the answer is 400.

5-Using the nmap flag -n what will it not resolve?

![](https://blogfelipe.com/assets/images/vulnversity-05.png)

Answer: DNS.

6-What is the most likely operating system this machine is running?

![](https://blogfelipe.com/assets/images/vulnversity-06.png)

Run: 

```bash
nmap -sV <ip>
```

You will see that Ubuntu is running on the machine.

Answer: Ubuntu

7-What port is the web server running on?

You could run a nmap command more sophisticatedly, but we already have our answer just using -sV flag. As you can see on the image, Apache is running on port 3333.

![](https://blogfelipe.com/assets/images/vulnversity-07.png)

Answer: 3333

## Task 3: Locating directiories using GoBuster

GoBuster is another useful tool for professionals and students. GoBuster is used to brute-force URIs, DNS subdomains, and also virtual host names. VulnUniversity will focus on using it to brute-force directories.
First, let’s install it.

Run: 

```bash
sudo apt-get install gobuster
```

![](https://blogfelipe.com/assets/images/vulnversity-08.png)

Now, we will run GoBuster with a wordlist.

Run: 

```bash
gobuster dir -u http://10.10.86.194:3333 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt | tee gobuster.log
```

You will find /uploads (forms) at /internal/

![](https://blogfelipe.com/assets/images/vulnversity-09.png)

Answer: 

```bash
/internal/
```

### Task 4: Compromise the webserver

1-Try upload a few file types to the server, what common extension seems to be blocked?

You need to test it, but you will find out that .php files are not allowed to upload.

Answer: .php

2-Run this attack, what extension is allowed?

Run nano phptest.txt to make a file with extensions.

![](https://blogfelipe.com/assets/images/vulnversity-10.png)

Put in the extensions inside our file and save it.

![](https://blogfelipe.com/assets/images/vulnversity-11.png)

Now, let’s use FoxyProxy for burpsuite. You will need to intercept and send it to intruder. Change this position to navigate to the payload and go to payload tab to import our file.

![](https://blogfelipe.com/assets/images/vulnversity-12.png)

Turn off URL encode and press attack button. Now, you are able to see the length of .phtml(723) is allowed. Remember to turn off the proxy.

Answer: .phtml	

3-No answer needed.

4-What is the name of the user who manages the webserver?
As a root, run ls -la /home and you will see the name bill.

Answer: Bill

5-What is the user flag?

Run:

```bash
cat /home/bill/user.txt
```

Now, you are able to see the flag!

Answer: 8bd7992fbe8a6ad22a63361004cfcedb

### Task 5: Privilege Escalation

1-On the system, search for all SUID files. What file stands out?

Run: 

```bash
find / -perm -u=s -type f 2>/dev/null
```

Answer: /bin/systemctl

2-Its challenge time! We have guided you through this far, are you able to exploit this system further to escalate your privileges and get the final answer? Become root and get the last flag (/root/root.txt)
Now, you will have a big challenge and I will let you try by yourself. I will give you only the steps you might need to get the last flag.

1-Create root.service

2-Enable root.service using systemctl

3-Create reverse connection to go to root directory

4-cat /root/root.txt

Answer: a58ff8579f0a9270368d33a9966c7fd5

I hope you liked it, thank you!