# Network Security Strategies and Applications
This docs is created as a homework for the lecture: Network Security with Open Source Tools.

Github Repository link: [gunaykrgl/siberguvenlik]: https://github.com/gunaykrgl/siber_guvenlik/
Github Pages link: (siber_guvenlik_ghPages)[https://gunaykrgl.github.io/siber_guvenlik/]

**Note**: [n:Number] is a reference to the n-th entry in References

Below are specific topics that are mentioned throughout the document

**The Topics**:

1. Network Security Strategies

    a) Importance of physical, software-based and network security strategies
    b) Strategic approaches for maintaining data safety

2. Importance of Network Security Applications and Tools

    a) Importance of basic security applications like Firewalls, IDS/IPS, anti-virus software

    b) Importance of cryptography and encrypton tools

3. Current network security problems and solutions

    a) DDos attacks and data breaches

## Definition of Network Security
Network security refers to the set of measures, policies and practices designed to protect the integrity, confidentiality and availability of computer networks and the data they transmit and store. [Source](https://study.com/academy/lesson/what-is-network-security-definition-fundamentals.html)
## Importance of Network Security
In the definition above, network security was outlined as a framework designed to protect the integrity, confidentiality and the availability[1] of computer networks. Let's delve into the significance of each of these elements:

1. **Integrity**: Integrity refers to preserving the unaltered state of data free from unauthorized disruptions. 
To illustrate the importance of data integrity, consider an algorithmic trading bot that relies on data fetched by a third-party provider. Imagine a scenario where a malicious user intercepts and modifies the price data transmitted via the API. Such an attack could compromise the data's integrity, leading to the algorithmic trading bot to execute an incorrect market order, potentially resulting in significant financial losses. 
As a second example, consider operating a bank where ensuring the integrity of data exchanged between ATM machines and the mainframe server is crucial. Now, consider a scenario that, a malicious agent could alter the ***amount*** data in the withdrawal request to the mainframe server. Such an act could result in malicious agent withdrawing more money than what was available in their account leading to a fraud. These examples emphasizes the significance of data integrity in various contexts.

2. **Confidentiality**: Confidentiality is characterized by preserving secrets and preventing unauthorized read access to sensitive data. To underscore its significance, envision a scenario where a prominent game studio is developing the next game in their popular franchise. With potentially thousands of employees collabarating on the project, crucial game files are likely exchanged via the local network. Additionally, if remote working opportunities are provided, the game data will also be needed to be exchanged through global internet. The lack of confidentiality in the network could result in leakage of game data before its intended release date undermining the effect of the planned trailer. In that case, the importance of confidentiality can clearly be seen. 

3. **Availability**: Availability is characterized by the continuous accessibility of data and services at all times. To underscore its significance, envision a scenario where a bank offers payment services connecting customers with local merchants or stores. These payment services are expected to operate 24/7. To ensure their continuous operation, they must establish a connection to the mainframe server or a node (in distributed systems). The absence of availability could result in transactions being unable to process, potentially driving customers towards alternative payment service providers. The importance of availability, therefore, lies in maintaining uninterrupted and reliable access to services, particularly in sectors where uninterrupted operation is essential for meeting customer expectations and sustaining competitiveness.

## Possible Attacks and Counter-Strategies
**Note**: Given that networks depend on communication among numerous computers, securing individual computers is an important part within network security. Consequently, some of the attacks and counter-strategies mentioned below might appear more closely associated with computer security rather than network security.
**Note**:  restricting permissions to only necessary interactions between nodes in the network contributes to a more distributed system, minimizing the impact of successful attacks on a single node. Since, this is related to the overall software architecture, this information is provided independently of specific attack. 

### Physical Attacks
Physical attacks are the type of attacks that require the attacker to have physical access to a device in the network or a transfer medium used for the network (e.g Cables). They are based on exploiting the vulnerabilities on the first layer of the OSI model.

1. **Cable Interception (Wire Tapping)**: 
This attack is also known as "Man in the middle Attack" [2]
The attacker may sever a cable at a specific location and deploy a device, such as a Raspberry Pi, under their control. This device could be configured to intercept and duplicate incoming packets, sending an identical copy both to the intended destination and the attacker's device. Through this method, the attacker gains the ability to divert the network traffic through their own device, allowing for unauthorized access and potential interception of sensitive information (Compromising CONFIDENTIALITY).

    **Counter-Strategy**

    - Utilizing TLS encryption can impede an attacker's capacity to gather sensitive information from intercepted data packets. While the attacker can still have access to the encrypted packet, the formidable nature of TLS encryption, with a 2048-bit key, renders decryption challenging and significantly strengthens the protection of the data.
    
2. **Inserting a malicious USB**:
If an attacker gains physical access to a computer, they can employ various tactics, such as booting from a USB drive and injecting malicious code into low-level software like the BIOS. Since most antivirus software operates at the operating system level, it becomes challenging to detect malicious code running below this layer. This type of code can establish a backdoor, granting the attacker remote access to the compromised computer. Additionally, if the disk is not encrypted, the attacker can freely read all the data stored on the computer.
Consider a real-life scenario where an attacker adopts the guise of a cleaning worker. Seizing an opportunity when an executive is away from their computer, the attacker inserts a USB drive to execute a script. This script, operating within a live-USB Linux distribution, clandestinely copies all the data from the computer's disk onto the USB drive. (Compromising CONFIDENTIALITY)

    **Counter-Strategies**
        
    - Disabling un-used usb ports

    - Encrypting the disks

    - Putting surveillance (Cameras) to make sure unauthorized people do not come and insert a USB to the computer.

### Social Engineering based Attacks
Social engineering based attacks encapsulate attacks that exploit the psychology of the target person. These kinds of attacks are one of **the most** prevalent attacks as manipulating human psychology and emotions tends to be easier than finding and exploting a software or hardware vulnerability. Some of the common counter-measurements against this type of attack involves educating the staff to always be cautious and informed. 

1. **Phishing**:
There are two common methods of phishing, and their initial stages are similar. Initially, the attacker sends an email to the target from an address that closely resembles the actual email address of a known individual (e.g., the imitating email could be emily_1awson@gmail.com, while the original is emily_lawson@gmail.com). The subsequent methods diverge from this point:

    **a)** The attacker may replicate a familiar website, creating a fraudulent user interface identical to the original. When an authorized staff member, with access to sensitive information, enters data into a form on the fake website, the attacker gains access to the sensitive data, using the staff member's password.
    **b)** Alternatively, the attacker could set the website to automatically download malicious software onto the target's computer. That's a significant risk if the target's browser permits the automatic download and execution of JavaScript.

    (Compromising CONFIDENTIALITY)
    **Counter-Strategies**
    
    - Training staff to exercise caution with incoming emails, avoiding clicking on links and always verifying the sender's email address.
    
    - Configuring staff browsers to prompt users before executing JavaScript or downloading files automatically.
    
    - Implementing firewalls to detect and block packets from and to suspicious websites.
    
    - Employing anti-malware software to identify and remove malware proactively. Such software can cross-reference downloaded files with a known malware database before permitting execution, adding an extra layer of security.
2. **Guessing the password**
This is generally **not considered** a type of attack as it is based more on passively trying possible passwords. However, it is still considered one of the most common method of stealing sensitive data.
Most people use easy-to-guess passwords like "12345678" and "password". Additionally, it is common for people to incorporate their personal information like name, birtplace or birthdate in their passwords. Furthermore, using the same password in multiple places is also commonplace. Using the same password across multiple places poses a security risk if one of the websites that the user was using the same password gets compromised.
(Compromising CONFIDENTIALITY)
    **Counter-Strategies**
    - Using 2 or 3-factor authentication 
    - Providing a limited number of (like 3) wrong password entries
    - Instructing the staff about using certain password managers, so that they can just memorise a single password to decrypt multiple passwords 
    - Instructing the staff to always check the authenticity of the website before entering their passwords.

### Software-based Attacks
1. **Malwares**
Malware is a broad term used to describe any type of malicious software. Such software can be utilized to either pilfer data, compromising the confidentiality of the network, or disrupt network operations, thereby undermining its availability. Ransomware, a specific type of malware, can further exacerbate the availability issue by restricting access to specific files.
(Could be used to compromise INTEGRITY, CONFIDENTIALITY OR AVAILABILITY)
    **Counter-Strategies [5]**

    - Anti-malware software can be used to check whether newly downloaded packages contain files that were previously identified as viruses. Centralized malware database are used in anti-malware softwares to list the knwon malwares.

    - Firewalls could be installed to selecctively block traffic from websites that are not in the trusted list.

    - Software could be kept up-to-date as new updates tend to patch existing security vulnerabilities.

    - Intrusion Detection Systems (IDSs) could be used to analyze the contents of incoming and outgoing packages and block suspicious packages from passing.

    - A distributed and well-defined authority structure in the network could prevents attackers from getting full control over the network by just infecting a small percentage of network participants.

### Network-based Attacks
1. **DDoS (Distributed Denial of Service) attacks**
A Distributed Denial of Service (DDoS) attack involves an initial stage where the attacker compromises a substantial number of independent small computers (called zombie computers). Then, the attacker uses the infected zombie computers to send a multitude of requests to a server, simultaneously. As a result of the sheer number of requests (from zombie computers), server may become unable to respond to legitimate requests. Consequently, this orchestrated flood of traffic can lead to network collapse, undermining the availability of services. For entities dependent on continuous and uninterrupted operation (like banking networks), DDoS attacks pose a significant and disruptive threat.
(Compromising AVAILABILITY)

    **Common types of DDoS attacks [4]**

    - Application layer attack: Different computers keep sending large number of simple http requests
    - Protocol attack: Protocol attacks exploit vulnerabilities in 3rd and 4th layers. An example of protocol attacks is SYN flood. In SYN flood, the attacker sends a large number of SYN packets to signify they want to make a TCP connection. Then, the server responds with SYN/ACK packets and starts waiting for an ACK packet. Attacker does not send the SYN/ACK package and causes server to keep an open port with each zombie computer. Once, there is not open ports left for the authentic requests, the server  becomes unable to function normally.
    **Counter-Strategies**

    - Load-balancing techniques can be used to distribute the traffic across multiple servers, so that the service can handle more requests.

    - IP addresses that any user haven't registered with but are actively used to make requests could be blocked.

    - The amount of request a single IP address makes can be limited, ignoring the over-the-limit requests.

    - If the majority of requests are coming from a certain region, the server could automatically reject requests from that region for some time. This could prevent the service from collapsing all around the world.

2. **DNS Spoofing Attack**
In a network, each computer is assigned an IP address for identification. Since directly remembering IP addresses can be challenging, DNS servers have been developed to translate textual addresses to corresponding IP addresses. These servers convert user-friendly textual addresses (e.g., http://www.google.com) into their corresponding IP addresses (e.g., 142.251.209.46 for Google).
A fake DNS attack commonly involves the attacker positioning themselves between the user and the DNS server, redirecting the user to a malicious website designed to mimic the appearance of the intended site. In this type of attack, a typical user may not readily discern that they have landed on a fraudulent website since the URL in the browser's top bar still displays the correct textual address. Consequently, users may unknowingly provide sensitive information to the attackers. (could be used to compromise INTEGRITY OR CONFIDENTIALITY)

    **Counter-Measure**
    
    - By using Domain Name System Security Extensions (DNSSEC)[3], the communication with DNSSEC is signed. Therefore, the user's computer can verify whether the DNS record sent by the server is from the registrar itself.

## Conclusion

Various attacks have been detailed in the preceding chapters, primarily focusing on attacks compromising confidentiality. As emphasized, adopting a proactive stance, educating staff about potential security vulnerabilities, maintaining constant vigilance regarding links in incoming emails, and preventing unauthorized physical access are among the most important pre-measures for ensuring security.

## References

**Repository link**: [siber_guvenlik, github](https://github.com/gunaykrgl/siber_guvenlik/)

1. [CIA Triad, unitrends](
https://www.unitrends.com/blog/cia-triad-confidentiality-integrity-availability#:~:text=Confidentiality%20measures%20are%20designed%20to,readily%20accessible%20for%20authorized%20parties)

2. [Wire-tapping attacks, infosectrain](https://www.infosectrain.com/blog/what-is-wiretapping-in-cybersecurity/)

3. [DNSSEC, imperva](https://www.imperva.com/learn/application-security/dnssec/)

4. [About DDoS ,Cloudflare](https://www.cloudflare.com/learning/ddos/what-is-a-ddos-attack/)

5. [IDS, firewall and Antivirus: What you need to have installed, welivesecurity by eset](https://www.welivesecurity.com/2015/04/30/ids-firewall-antivirus-need-installed/)
