---
title: "Try Hack Me - Introductory Research"
categories:
  - CTF
---

Walkthrough of the room Introductory Research on TryHackMe. Let's go!

![](https://blogfelipe.com/assets/images/introresearch-01.png)

## Task 1: Introduction


The first task is a simple introduction to tell you about the importance of research in Cybersecurity. You will always need to find something that you don’t know yet. So, it’s important to know how to search in order to get the answers you might need to solve your problem. Read the task and click on “Completed”. (No answer needed)

### Task 2: Example Research Question

In Task 2, you will learn how to search and found something on the internet to help you through a CTF or even at work. Let’s go!
Example of the Task: “JPEG image”. How can you find if there’s something hidden inside it? Well, if you never did it before, you will definitely need to search how you can do it. So, let’s google it!

How about: “How to look for hiding things inside JPEG images” in Google? Basically, you will probably find many options and hints to help you. And, if you are really looking for it, you will find something called: “Steganography”.

That’s how you search about a technique, find answers and keep learning in Cybersecurity. In that case, you will study Steganography and how we can hide things inside images. It’s amazing btw!

After you learn about it, we need to find something that we can extract something inside the file. So, let’s google it!
How about: “Extract file from jpeg image tool” You will find tools to help you!

As you go to your first or second option, you will probably dive iNTO some new knowledge. In that case, you will find 0xrick tool on Github and how to use it!

In Cybersecurity, we need to go step by step, search by search to get what we want. You should not rush or skip the process and the logic of your curiosity.

“This is a really good way to conduct research: Start with a question; get an initial understanding of the topic; then look into more advanced aspects as needed.”

Answer the questions below:

We can solve all of them, but we need to know how to search for them. You don’t need to know everything, you are not a machine.

1-In the Burp Suite Program that ships with Kali Linux, what mode would you use to manually send a request (often repeating a captured request numerous times)?

I have an idea. Let’s search something like “manually request burp”, you will get something called “Burp Repeater”. If you dive into it, you will see that Burp Repeater is used to send a request manually. So, the answer is Repeater. Please, learn about it!

[here](https://portswigger.net/burp/documentation/desktop/tools/repeater/using)

2-What hash format are modern Windows login passwords stored in?
Let’s search about it. We can google something like “hashing algorithm for windows”.You will probably find the answer(NTLM)

[here](https://www.sciencedirect.com/topics/computer-science/hashing-algorithm)

Don’t stop, try to understand how Microsoft does it and how hash algorithms works!

3-What are automated tasks called in Linux?

Let’s google: “automated tasks Linux”. You will find this website:

[here](https://www.linuxtechi.com/schedule-automate-tasks-linux-cron-jobs/)

There, you will see something called “cron jobs” (Crontab) used for the automation of tasks in Linux. Keep reading the website and answer:

cron jobs

4-What number base could you use as a shorthand for base 2 (binary)?

Let’s google: “number base shorthand for base 2”. You will find this website talking about Base 16 and how to use it (maybe is the answer):

[here](https://practicalee.com/binary/)

5-If a password hash starts with $6$, what format is it (Unix variant)?

You will still find the answer on the internet, so let’s google it: “$6$ unix variant”. You will find this website:

[here](https://www.open.com.au/radiator/ref/User-Password.html)

Then, you are able to answer the question by looking at Linux SHA crypt.

SHA512 crypt

## Task 3: Vulnerability Searching

“NVD keeps track of CVEs (Common Vulnerabilities and Exposures) — whether or not there is an exploit publicly available — so it’s a really good place to look if you’re researching vulnerabilities in a specific piece of software. CVEs take the form: CVE-YEAR-IDNUMBER

(Hint Hint: It’s going to be really useful in the questions!)

ExploitDB tends to be very useful for hackers, as it often actually contains exploits that can be downloaded and used straight out of the box. It tends to be one of the first stops when you encounter software in a CTF or pentest.

If you’re inclined towards the CLI on Linux, Kali comes pre-installed with a tool called “searchsploit” which allows you to search ExploitDB from your own machine. This is offline, and works using a downloaded version of the database, meaning that you already have all of the exploits already on your Kali Linux!”

Keep reading about how to search for exploits and how to find CVE numbers.

1-What is the CVE for the 2020 Cross-Site Scripting (XSS) vulnerability found in WPForms?

As explained, you can search about the XSS on ExploitDB website. So, try to search “cross site wp” and find the correct 2020 CVE vulnerability. Remember the format to answer:

CVE-YEAR-NUMBER.

![](https://blogfelipe.com/assets/images/introresearch-02.png)

CVE-2020–10385

2-There was a Local Privilege Escalation vulnerability found in the Debian version of Apache Tomcat, back in 2016. What’s the CVE for this vulnerability?

![](https://blogfelipe.com/assets/images/introresearch-03.png)

CVE-2016–1240

3-What is the very first CVE found in the VLC media player?

![](https://blogfelipe.com/assets/images/introresearch-04.png)

CVE-2007–0017

4-If you wanted to exploit a 2020 buffer overflow in the sudo program, which CVE would you use?

![](https://blogfelipe.com/assets/images/introresearch-05.png)

CVE-2019–18634

### Task 4: Manual Pages

Learn about the “man” command and let’s answer the questions.

1-SCP is a tool used to copy files from one computer to another. What switch would you use to copy an entire directory?

Search about some flags of SCP using “man” or search on the internet about it. I will give to you this website:

[here](https://stackabuse.com/copying-a-directory-with-scp/)

```bash
-r
```

2- fdisk is a command used to view and alter the partitioning scheme used on your hard drive.What switch would you use to list the current partitions?

Run “man fdisk”. You will find the answer. Also, you can google about fdisk flags.

```bash
-l
```

3-nano is an easy-to-use text editor for Linux. There are arguably better editors (Vim, being the obvious choice); however, nano is a great one to start with.What switch would you use to make a backup when opening a file with nano?

Run “man nano”. You will find all the options for nano and the answer.

```bash
-B
```

4- Netcat is a basic tool used to manually send and receive network requests. What command would you use to start netcat in listen mode, using port 12345?

Run “man netcat” and understand the format of netcat.

```bash
nc -l -p port [-options] [hostname] [port]
```

```bash
nc -l -p 12345
```

### Task 5: Final Thoughts

Read and finish the room!

Thank you!