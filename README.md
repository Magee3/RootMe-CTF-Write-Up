# RootMe-CTF-Write-Up

### Objective

Gain access to the machine and become root!

Scope 10.10.129.139

### Reconnaissance

First step of our reconnaissance will be to simply test if we can connect with the machine. We test this by sending test packets or pings.

Run:

ping 10.10.129.139

![1](https://github.com/Magee3/RootMe-CTF-Write-Up/assets/134301259/2f245c23-6319-4278-98a5-0bd8fd0c4b73)

SUCCESS!

We can talk with the machine. The next step is to find information about the machine. We will run a port scan to see what services are running and hopefully find out what operating system.

Run: sudo nmap -v -sC -sV

![2](https://github.com/Magee3/RootMe-CTF-Write-Up/assets/134301259/4f1c7de8-c828-4134-add9-f66e4831aca2)

![2 2](https://github.com/Magee3/RootMe-CTF-Write-Up/assets/134301259/0ebe45a4-3f08-48e8-96f0-110af09c81c5)

With a simple port scan we find out that there are 2 services running, SSH and HTTP. This machine is also running on apache, the machine is most likely a webserver. We can test to see if we have access to it
by copying the targets ip into our local browser.

Run: http://10.10.129.139/

![4](https://github.com/Magee3/RootMe-CTF-Write-Up/assets/134301259/6c350730-2796-4a42-bc7d-d5fef1b1d382)

When we enter the webpage we get a RootMe tittle and thats pretty much it. No other information on the page but lets view the souce code just in case.


![5](https://github.com/Magee3/RootMe-CTF-Write-Up/assets/134301259/873446ef-81c9-4b37-a430-3f5769e142b6)

Even in the source code there is no other information. We can see if the website is hosting other webpages by running directory buster.

Run: dirb http://10.10.129.139/

![6](https://github.com/Magee3/RootMe-CTF-Write-Up/assets/134301259/bdef271d-a40f-4d49-9223-ca7070405bb5)

