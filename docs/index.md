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
A potential attacker may sever a cable at a specific location and deploy a device, such as a Raspberry Pi, under their control. This device could be configured to intercept and duplicate incoming packets, sending an identical copy both to the intended destination and the attacker's device. Through this method, the attacker gains the ability to divert the network traffic through their own device, allowing for unauthorized access and potential interception of sensitive information.
**Possible Counter-Strategy**:
Utilizing TLS encryption can impede an attacker's capacity to gather sensitive information from intercepted data packets. While the attacker may have access to the encrypted packet, the formidable nature of TLS encryption, with a 2048-bit key, renders decryption challenging and significantly strengthens the protection of the data.

## Strategies for Network Security
### Physical Security Strategies
### People-based Security Strategies
### Software-based Security Strategies
### Network-based Security Strategies
