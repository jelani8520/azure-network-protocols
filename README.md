# azure-network-protocols
<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- create a resource group and virtual machines setting up subnet
- view virtual machines in in remote desktop 
- using command-line tools such as  nslookup , cd,ls.cat.ipconfig ,-t,ume -a 
- install wireshark
- view various network protocols

<h2>Actions and Observations</h2>

<p>

><img width="1680" alt="Screen Shot 2025-02-13 at 6 50 14 PM" src="https://github.com/user-attachments/assets/40fac726-cf6c-45b2-8b5b-f1c2a8979f81" />

<p>
in Microsoft Azure i created a reasource group
A Resource Group in Azure is a logical container for managing and organizing Azure resources (e.g., virtual machines, storage accounts, databases, etc.). You can create a resource group using different methods i used the azure portal 

</p>
<br /><img width="1680" alt="Screen Shot 2025-02-13 at 6 52 12 PM" src="https://github.com/user-attachments/assets/03d9bf23-7ffd-4342-96c0-8dfa36fbcbbf" />

after creating the resource group i observed it
<p>

<img width="1680" alt="Screen Shot 2025-02-13 at 6 52 52 PM" src="https://github.com/user-attachments/assets/b1f4b9f2-d98a-4d6a-8622-16fc599ed2bf" />
after its creation i then navaigated to virtual macines

<img width="1680" alt="Screen Shot 2025-02-13 at 6 54 20 PM" src="https://github.com/user-attachments/assets/4733b555-c467-4fdd-bd97-ebf46f5bc9d7" />
i filled out all the steps such as setting the correct resource group ( rg - network activites )  and the correct image  windows 10 x64 gen  for the right display  

<img width="1680" alt="Screen Shot 2025-02-13 at 6 55 20 PM" src="https://github.com/user-attachments/assets/64327984-2596-42ad-988d-e7bee6e8d530" />
while creating i setup the subnet mask so that the two systems could reach each other 

<img width="1680" alt="Screen Shot 2025-02-13 at 6 56 30 PM" src="https://github.com/user-attachments/assets/1af85eb6-c095-46e9-a523-9d481ad7cd73" />


< ><img width="1680" alt="Screen Shot 2025-02-13 at 6 58 24 PM" src="https://github.com/user-attachments/assets/3f5a4280-1a18-4993-8dbf-f3c8f7ba360c" />
in the resource group i observe it being made 

<img width="1680" alt="Screen Shot 2025-02-13 at 7 01 22 PM" src="https://github.com/user-attachments/assets/99a824a7-c038-46aa-a63c-6d331b14ab56" />
i then created the linux  vm with Ubuntu Server 20.04 and set a user and password 
<img width="1680" alt="Screen Shot 2025-02-13 at 7 05 50 PM" src="https://github.com/user-attachments/assets/0f4b7820-e882-429b-91ec-d399ff8ddf67" />
i then put the linux vm under the same resource group 

<img width="1680" alt="Screen Shot 2025-02-13 at 7 08 14 PM" src="https://github.com/user-attachments/assets/c5fee2f8-100b-4a6f-8e1f-d384cb3b0afd" />
i then  observed the two vms under the same subnet

<img width="1680" alt="Screen Shot 2025-02-13 at 7 08 27 PM" src="https://github.com/user-attachments/assets/0022a572-0fdf-40dd-98db-44471f4b84ef" />

i had to get a little creative with with viewing the vm's because i have a older system so i downloaded and configrued it to work and view 
<img width="1680" alt="Screen Shot 2025-02-13 at 7 24 01 PM" src="https://github.com/user-attachments/assets/8d5442ca-4849-4d86-8183-930e03622f1f" />


<img width="1680" alt="Screen Shot 2025-02-13 at 8 59 09 PM" src="https://github.com/user-attachments/assets/79d157f8-67aa-4b22-8270-ab8b6e057eba" />
after i copied the public ip address i then login in as a labuser 

<img width="1680" alt="Screen Shot 2025-02-13 at 9 04 20 PM" src="https://github.com/user-attachments/assets/1f5a8ebe-05a2-4048-b057-5a5d79f5f5ab" />
i use the web browser to then download wireshark Protocol Analyzer

<img width="1680" alt="Screen Shot 2025-02-13 at 9 09 47 PM" src="https://github.com/user-attachments/assets/a054f3db-d51a-4ea0-9eaa-de6b34c79b83" />
within wireshark i clicked on ethernet to start the capture then i fillerd for icmp traffic by opening powershell and sending a ping observing the traffic between the public and private ip address
<img width="1680" alt="Screen Shot 2025-02-13 at 9 17 25 PM" src="https://github.com/user-attachments/assets/5d1596d6-e62a-480c-82f2-e931a41a8940" />
in powershell i ran a non-stop ping  using command -t 
<img width="1680" alt="Screen Shot 2025-02-13 at 9 17 25 PM" src="https://github.com/user-attachments/assets/e7ed8e6d-b761-4848-a90b-05f7df2922e6" />
within the network setting i created a fire wall from setting any icmp traffic and observed the change before deleting the rule

<img width="1680" alt="Screen Shot 2025-02-13 at 9 20 11 PM" src="https://github.com/user-attachments/assets/ce41c921-f3bf-4d78-8c07-b17f2cf74292" />
<img width="1680" alt="Screen Shot 2025-02-13 at 9 22 00 PM" src="https://github.com/user-attachments/assets/ea047434-6d62-4505-883a-70527c67d7b4" />
in wireshark i fillterd for ssh and run ssh in powershell  

<img width="1680" alt="Screen Shot 2025-02-13 at 9 29 21 PM" src="https://github.com/user-attachments/assets/f7f1f055-a46a-4fc9-a94d-164075813b40" />

dhcp traffic that was captured

<img width="1680" alt="Screen Shot 2025-02-13 at 9 46 13 PM" src="https://github.com/user-attachments/assets/50e6fb9b-9fea-4124-914c-b2610462de78" />
 i fillerd for rdp traffic by by using udp.port 3389 
<img width="1680" alt="Screen Shot 2025-02-13 at 9 52 49 PM" src="https://github.com/user-attachments/assets/e0f5af7b-c02a-4d17-a65f-b9cc49c2a42c" />
 i used wireshark to observe dns traffic using udp.port 53 

<img width="1680" alt="Screen Shot 2025-02-13 at 9 47 34 PM" src="https://github.com/user-attachments/assets/1811b38f-bf3f-42b3-811f-8b9e89d04721" />











