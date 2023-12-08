# Network Security Strategies and Applications
This docs is created as a homework for the lecture: Network Security with Open Source Tools
## Intoduction
### Definition of Network Security
Network security refers to the set of measures, policies and practices designed to protect the integrity, confidentiality and availability of computer networks and the data they transmit and store. [Source](https://study.com/academy/lesson/what-is-network-security-definition-fundamentals.html)
### Importance of Network Security
In the definition above, network security was outlined as a framework designed to protect the integrity, confidentiality and the availability of computer networks. Let's delve into the significance of each of these elements:

1. **Integrity**: Integrity refers to preserving the unaltered state of data free from unauthorized disruptions. 
To illustrate the importance of data integrity, consider an algorithmic trading bot that relies on data fetched by a third-party provider. Imagine a scenario where a malicious user intercepts and modifies the price data transmitted via the API. Such an attack could compromise the data's integrity, leading to the algorithmic trading bot to execute an incorrect market order, potentially resulting in significant financial losses. 
As a second example, consider operating a bank where ensuring the integrity of data exchanged between ATM machines and the mainframe server is crucial. Now, consider a scenario that, a malicious agent could alter the ***amount*** data in the withdrawal request to the mainframe server. Such an act could result in malicious agent withdrawing more money than what was available in their account leading to a fraud. These examples emphasizes the significance of data integrity in various contexts.

2. **Confidentiality**: Confidentiality is characterized by preserving secrets and preventing unauthorized read access to sensitive data. To underscore its significance, envision a scenario where a prominent game studio is developing the next game in their popular franchise. With potentially thousands of employees collabarating on the project, crucial game files are likely exchanged via the local network. Additionally, if remote working opportunities are provided, the game data will also be needed to be exchanged through global internet. The lack of confidentiality in the network could result in leakage of game data before its intended release date undermining the effect of the planned trailer. In that case, the importance of confidentiality can clearly be seen. 

3. Availability: Availability is characterized by the continuous accessibility of data and services at all times. To underscore its significance, envision a scenario where a bank offers payment services connecting customers with local merchants or stores. These payment services are expected to operate 24/7. To ensure their continuous operation, they must establish a connection to the mainframe server or a node (in distributed systems). The absence of availability could result in transactions being unable to process, potentially driving customers towards alternative payment service providers. The importance of availability, therefore, lies in maintaining uninterrupted and reliable access to services, particularly in sectors where round-the-clock operation is essential for meeting customer expectations and sustaining competitiveness.

## Possible Attacks and Counter-Strategies
### Physical Attacks
Physical attacks are the type of attacks that require the attacker to have physical access to a device in the network or a transfer medium used for the network (e.g Cables).
1. **Cable Interception (Wire Tapping)**: 
The attacker may sever a cable at a specific location and deploy a device, such as a Raspberry Pi, under their control. This device could be configured to intercept and duplicate incoming packets, sending an identical copy both to the intended destination and the attacker's device. Through this method, the attacker gains the ability to divert the network traffic through their own device, allowing for unauthorized access and potential interception of sensitive information.
**Counter-Strategy**:
Utilizing TLS encryption can impede an attacker's capacity to gather sensitive information from intercepted data packets. While the attacker can still have access to the encrypted packet, the formidable nature of TLS encryption, with a 2048-bit key, renders decryption challenging and significantly strengthens the protection of the data. 
2. **Inserting a malicious USB**:
If the attacker has physical access to a computer, they could boot from their own USB drive and insert malicious code in low-level software like bios. As most antivirus softwares work on operating system, they won't easily be able to detect software that is running below operating system layer. Such malicious code could be used to open a back-door and get remote access to the computer.

**Counter-Strategy**:
* Disabling un-used usb ports
* Putting surveillance (Cameras) to make sure unauthorized people do not come and insert a USB to the computer.

### Staff-based Attacks
**Phishing**:
There are two common methods of phishing, and their initial stages are similar. Initially, the attacker sends an email to the target from an address that closely resembles the actual email address of a known individual (e.g., the imitating email could be emily_1awson@gmail.com, while the original is emily_lawson@gmail.com). The subsequent methods diverge from this point:

**a)** The attacker may replicate a familiar website, creating a fraudulent user interface identical to the original. When an authorized staff member, with access to sensitive information, enters data into a form on the fake website, the attacker gains access to the sensitive data, using the staff member's password.
**b)** Alternatively, the attacker could set the website to automatically download malicious software onto the target's computer. That's a significant risk if the target's browser permits the automatic download and execution of JavaScript.
**Counter-Strategies**: 
a) Training staff to exercise caution with incoming emails, avoiding clicking on links and always verifying the sender's email address.
b) Configuring staff browsers to prompt users before executing JavaScript or downloading files automatically.
c) Implementing firewalls to detect and block packets from and to suspicious websites.
d) Employing anti-malware software to identify and remove malware proactively. Such software can cross-reference downloaded files with a known malware database before permitting execution, adding an extra layer of security.

## Strategies for Network Security
### Physical Security Strategies
### People-based Security Strategies
### Software-based Security Strategies
### Network-based Security Strategies
