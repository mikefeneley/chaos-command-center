# chaos-command-system

Information security managament system

This is a placeholder repo. No significant work has been done here yet.

**Problem**

The problem in a nutshell: security is difficult. 

As computer and information systems increase in complexity, it becomes difficult to keep user data and systems secure.

To secure systems, tools and controls have to be put in place to deal with threats at multiple layers of technology abstraction. But it is impossible for the average computer user to have the technical domain knowledge to do this. Currently, even infosec professionals cannot stay up to date with all the developments in this field. At best, they can be a hyperspecialist and become proficient in one aspect of security. To have a reasonable chance of setting up a secure system, the implementation and configuration details need to be abstracted away from the user as much as possible. 

**Objective:**

We aim to provide a simple GUI wrapper for a comprehensive information security management system tool. The core functionality of the tool will be automated deployment and configuration of a variety of critical, open source infosec tools. These tools will either be existing implementations, or ones that we write ourselves.

The goal is to automate the security process as much as possible. Humans are usually the weakest link in the information security chain, so by minimizing human involvement we decrease the risk that the human element can be exploited to gain access to information systems.

To accomplish this goal, we aim to make an 'all in one' tool that addresses as many aspects of a strong security system as possible including configuration management, vulnerability scanning, system auditing, file integrity checks, IDS/IPS, firewalls, etc.

Tools already exist to address these individual security tasks, but they do not come installed and configured by default. Furthermore, they require a high level of expertise to use. Our goal is to write new tools and combine existing solutions into a single, cohesive tool that 'just works'. It should be easy to install and come pre configured to enforce security best practices. Due to the nature of security, this won't be a silver bullet that provides an impenetrable security shield for information system, but we aim to get as close to that as possible.

The main design objective is to have the ISMS be composed of tiny, modular tools which adress single infosec issues. These tools than can then be wrapped in a GUI to form a comprehensive system that provides an interface a security naive user can understand.

**Strategy**

We think the easiest way to move forward on this is to pick one of the features we want to support and build it as an independent command line tool. Once 2-3 tools have been developed or chosen from existing options for inclusion, we can can start to write a GUI interface that wraps these tools together while continuting to add or develop addtional tools to increaes the functionality.

The first tool we are adding is an integrity verification tool. The idea behind the tool is that you have files on your computer that you want to make sure have not been tampered with, such as libraries and configuration files. You can verify the integrity of the files by calculating the checksum and storing it in a database. At a future time, you can verify that the files are the same by calculating the checksum and comparing them to make sure they are the same.

The verification tool interface allows users to add folders and files to list. The program computes the checksum of these files and stores them in a remote database. The program runs a daemon in the background that periodically wakes up, recalculates the checksum of every file in the list, and compares it to what is stored. If any of the files don’t match up, then you know the file has been changed and you can respond appropriately. 

We have started working on this project and are hosting it on github here: https://github.com/mikefeneley/chaos-monitor

**Desired Tools and Candidates Brainstorm**

Below is a list of tools we would like to implement as part of the larger, information security management system. Most of these tools already have open source implementations and should be used instead of writing our own from scratch.

File Integrity Checker  -- Chaos Monitor

Configuration Management Tool -- SaltStack

Configuration Auditor  -- OpenScap

Automated Vulnerability Checker -- 

Access Control -- PacketFense

Cloud Storage --- 

Backup Management Tool - Encrypted file uploads to cloud storage

CCC Gui -- 

Full Disk Encryption -- TrueCrypt, VeraCrypt

**Tentative Schedule**

There are potentially 3 people working on the project. 

The project is modular enough that we think multiple, discrete teams working on different components is the most effective way to implement the system.

We are in the process of making a schedule. Dates will be selected based on community interest in the project.

**Misc**

If you are interested in helping with this project, email mfeneley@vt.edu.

We don't just need people who are interested in technology, we are also looking for people who are talented writers and artists.

I would also like to help and mentor new programmers, so if you are beginner who is a hard, disciplined worker and is eager to learn, let me know. 

**BrainStorm/Misc**

Information security goals: Confidentiality, Integrity, Availability

Individual solutions exist for of all of these, but individual programs have to be tailored to meet the exact requirements of the user and their system. This requires a high degree of technical competence and security awareness. Our goal is to make a system which automates the security process as much as possible. Upon deployment, the system installs and configures all the tools necessary to ensure, Confidentiality, Integrity, Availability. Programs are installed with best practices and requires a minimum of user interaction. Once deployed, the system should operate with as little user involvement as possible.

Likely solution, write individual tools or utilize existing tools that already solve one aspect of security, then combine them together with a user friendly interface that doesn’t require understanding of the underlying processes.

Chaos-Monitor: Tool to guarantee the integrity of a user's files. Important system files should be added to the list to verify that they have not changed by a malicious hacker. Users data in long term storage should be added to prevent bit rot.
