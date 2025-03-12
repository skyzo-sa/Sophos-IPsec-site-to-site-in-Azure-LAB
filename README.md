# Sophos XGS IPsec Site to Site in Azure LAB

## Objective

The main objective of this LAB is to establish a secure encrypted tunnel between an on-premises network (protected by Sophos XGS Firewall) and Azure Virtual Network (VNet). This ensures that resources in both environments can securely communicate as if they were on the same network.

### Job Skills Learned

- Cloud Networking & Security
- Real-world experience in hybrid cloud connectivity
-  Network Security & VPN Configuration
- Firewall & Security Rules
- Azure Networking & Security


### Tools Used

- Microsoft Azure Portal
- Sophos XGS Firewall v21.0 (virtual instance) 
- Access to the Sophos Central Management Portal
- SFOS 21.0 Web Interface (GUI)
- SFOS 21.0 Command Line Interface (CLI)
- Control Center Dashboard: Built-in monitoring tool for real-time traffic and event analysis.


*Ref 1: Network Diagram*
![image](https://github.com/user-attachments/assets/0c49bc23-9797-4dea-ab7a-3aebd8c0ad99)

 
## CONFIGURATION STEPS

This outlines the steps needed to enable IPsec tunnel site-to-site in Azure, ensuring proper network configuration and security policies.


-	Notes:

-	UDP 4500
-	UDP 500
-	IP 50
![image](https://github.com/user-attachments/assets/23f69ef3-f257-43ac-8093-c837ae1d5671)

 

-	1. Allow IPSec Protocols (Both Ends)
Azure Cloud
![image](https://github.com/user-attachments/assets/13b21ef2-4bc0-483b-ae4f-96a747bb95c5)
![image](https://github.com/user-attachments/assets/99b6b221-1805-4321-a65d-fcefa6d35aab)
![image](https://github.com/user-attachments/assets/8611be09-9113-4cab-9482-a16b7785ad8c)
 
 
 
On-prem router
DMZ traffic to WAN Public IP of Azure
![image](https://github.com/user-attachments/assets/74f28368-31f9-4dab-b39a-82353b738352)
![image](https://github.com/user-attachments/assets/591c2953-b5fb-4bf2-9e6b-89b565ef19d8)
 


-	2. Define the Objects (Both Ends) 


-	# On-Premise Network#

-	LAN: `192.168.2.0/24`
 ![image](https://github.com/user-attachments/assets/f0fd7fdb-717c-4496-8a4c-e0fade46a4a9)

-	Remote LAN: `10.0.2.0/24`
 ![image](https://github.com/user-attachments/assets/fa4ff5c8-1811-4a76-9890-48850e8b2458)



-	# Azure Cloud Network#
-	LAN: `10.0.2.0/24`
![image](https://github.com/user-attachments/assets/5047b995-ea6f-4ce5-8ba1-6faf0f50ecf9)
 
-	Remote LAN: `192.168.2.0/24`
 ![image](https://github.com/user-attachments/assets/f9c63f4a-fdfc-4deb-9492-49fa4ba87063)



-	3. Create IPSec connection On-prem 
 ![image](https://github.com/user-attachments/assets/941f8871-b57d-41ef-86f5-ea09e982c56f)
![image](https://github.com/user-attachments/assets/25d379a9-02c1-404d-b38a-344b8c87c5e6)
![image](https://github.com/user-attachments/assets/48284e68-8489-4792-9da3-a9ba1506abb1)
![image](https://github.com/user-attachments/assets/333744d8-62c8-446c-84ca-3493e67d8bfb)

-	4. Create IPsec connection Azure 
![image](https://github.com/user-attachments/assets/1f11488b-7634-48e3-98ef-0dda3191daa0)
![image](https://github.com/user-attachments/assets/d90179fb-9182-4360-a82b-c8f765a2117c)
![image](https://github.com/user-attachments/assets/faffe7e2-946c-474d-ba29-3eb1604ea034)
![image](https://github.com/user-attachments/assets/3af48892-a1d5-4d73-a5a9-15fc23f06978)
![image](https://github.com/user-attachments/assets/29bd9c79-3c13-4b00-b02b-46316afcb386)
![image](https://github.com/user-attachments/assets/d0828c35-a3e8-43a7-b86f-2e2801293f7a)




-	5. Create Firewall Rules (Both Ends) 
![image](https://github.com/user-attachments/assets/23db8dcc-48b2-4cb0-850c-e8ff3a3e6457)
 ![image](https://github.com/user-attachments/assets/bae14f8a-0f49-4d20-8307-a52ccb537479)
![image](https://github.com/user-attachments/assets/f47fe360-146c-42ed-bb94-c15f343fd03e)
 

Azure Side
![image](https://github.com/user-attachments/assets/cfd0ae3d-176e-4d4a-87bf-755b2347a633)
![image](https://github.com/user-attachments/assets/f8bb35b8-99c0-460b-9e57-aa0ed2a58a09)
![image](https://github.com/user-attachments/assets/99100992-46d4-40f1-b3d2-fda20f3b30ac)
![image](https://github.com/user-attachments/assets/12bfcb21-682d-4eac-b630-cd0487d0dc67)

Enable Ping and DNS under VPN zone for Device Access (Both Ends)
![image](https://github.com/user-attachments/assets/b80d243c-23ed-48e8-9ee9-363769eeec40)
 
-	6. Test the connection
![image](https://github.com/user-attachments/assets/4ccfd578-a1b5-40ea-b1a0-080bfa3cdb26)
![image](https://github.com/user-attachments/assets/a02478ac-16e9-4bc2-9689-8aee574e9df4)

 

 
