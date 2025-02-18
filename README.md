# Network-Security-Groups-NSGs-and-Inspecting-Network-Protocols
<p align="center">
![1](https://github.com/user-attachments/assets/bf2b826d-d6d6-44e3-b1a8-49d50d2f0673"

</p>
<p align="center">
![2](https://github.com/user-attachments/assets/70c09387-d538-44f7-aca3-a66e9251e431"

</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDP, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- First create a Resource Group
- Create a Virtual Machine in Windows
- Create a Virtual Machine in Linux
- Remote Desktop Connection into both VM
- Download Wireshark in VM1
- Open Command prompt and perform a endless ping -t from VM1 to VM2
- Create a Network Security Group in Azure for denying the endless ping
- Open Wireshark and monitor protocols (SSH,DNS,RDP, and ICMP)
- Open Powershell and log into VM2 using SSH
- Run Powershell Commands in VM2
- Exit VM1
- Delete Resource Groups in Azure for both VM's


<h2>Actions and Observations</h2>

<p>
![3](https://github.com/user-attachments/assets/dee6b27c-1f5a-43a5-9be2-09fbe169fc06"

</p>
<p>
First go to Microsoft Azure and type Resource Groups in the search bar
</p>
<br />

<p>
![4](https://github.com/user-attachments/assets/59132714-37ad-46b0-b26e-e8c265048041"

</p>
<p>
Next for the Resource Group name type RG-LAB-02 and the region under US West US 3
</p>
<br />

<p>
![5](https://github.com/user-attachments/assets/da793cc5-7315-4f09-a9b9-50f1e3a0a8ab"

</p>
<p>
Then go to the Review and Create section and let the validation passed
</p>
<br />

<p>
![6](https://github.com/user-attachments/assets/c56a8d6c-eec8-4bf6-99ae-2e16752ebeaa"

</p>
<p>
Now go back to Resource Groups and you will see it was created
</p>
<br />

<p>
![7](https://github.com/user-attachments/assets/ba4cfd08-74f2-40ba-8498-c72312aa29e1"

</p>
<p>
Type Virtual Machines in the search bar
</p>
<br />


<p>
![8](https://github.com/user-attachments/assets/6e337c81-a48b-4387-972c-fd1068d5c9cc"

</p>
<p>
Now for the Resource Group click the one we created RG-LAB-02.
</p>
<br />

<p>
![9](https://github.com/user-attachments/assets/91a633b4-dba9-4291-86d6-99e665599dcd"

</p>
<p>
Next type the VM name VM1, and the region under US West US 3, the Image under Windows 10 Pro, and the size under Standard E2s
</p>
<br />

<p>
![10](https://github.com/user-attachments/assets/00089212-ee88-4587-850a-38c1a4e7ca29"

</p>
<p>
Next the username will be named labuser and the password can be your own unique password. The Licensing check the box
</p>
<br />

<p>
![11](https://github.com/user-attachments/assets/7489ce7c-8076-4717-9dbd-f63cad98b081"

</p>
<p>
Now go to the Networking tab and make sure the Virtual Network, Subnet, and Public IP all says (new)
</p>
<br />

<p>
![12](https://github.com/user-attachments/assets/c64456c2-4500-472b-a8cc-bd2815362f7b"

</p>
<p>
Now go to the Review and create tab and click the Create tab on the bottom left
</p>
<br />

<p>
![13](https://github.com/user-attachments/assets/01d8742a-d3b7-47bd-b904-23cc402c17a3"

</p>
<p>
![14](https://github.com/user-attachments/assets/4a5e08a9-1b92-4244-9e4c-c2f4373d974b"

</p>
<p>
Next let the deployment process load, once its done a green check will emerge near the deployment
</p>
<br />

<p>
![15](https://github.com/user-attachments/assets/838a526a-51b2-49ff-a14a-5fa0802161b3"

</p>
<p>
Next go type Virtual Machine and click VM1
</p>
<br />

<p>
![16](https://github.com/user-attachments/assets/6d0314ef-597f-4a7a-8391-c063c45f57a3"

</p>
<p>
Now click create Azure Virtual Machine 
</p>
<br />

<p>
![17](https://github.com/user-attachments/assets/400df7dd-9854-4c97-9669-3c51ae23b8f1"

</p>
<p>
Next click the Resource group name under RG-LAB-02, the Vritual Machine Name under VM2 and the region US WEST US 3
</p>
<br />

<p>
![18](https://github.com/user-attachments/assets/44a7ac41-cd59-4262-8162-9138666faa34"

</p>
<p>
Now for the Image put Ubuntu Sever Gen2 and the size under Standard E2
</p>
<br />

<p>
![19](https://github.com/user-attachments/assets/bace22a6-5c15-48b1-aa55-4d858d9fd974"

</p>
<p>
Next for the authentication type click password, under Username type labuser and the password tpye the password
</p>
<br />

<p>
![20](https://github.com/user-attachments/assets/4dfce9b4-cc86-4cf1-8ff2-e02f11720ccd"

</p>
<p>
Now go to the networking tab and make sure virtual network, subent, and public IP all says (new)
</p>
<br />

<p>
![21](https://github.com/user-attachments/assets/c3d167fa-3dc2-4840-8e47-0c246b102b14"

</p>
<p>
Next go to the Review and create tab and click create at the bottom left
</p>
<br />

<p>
![22](https://github.com/user-attachments/assets/7e8e31e0-053a-4e8a-9719-f8b0ada92d82"

</p>
<p>
![23](https://github.com/user-attachments/assets/91e24bf8-54ab-44c0-83f5-00ebed7a501c"

</p>
<p>
Now the deployment process will begin. Then once it's done a green check will appear
</p>
<br />


<p>
![24](https://github.com/user-attachments/assets/b058a836-7b6b-4a70-9468-dbdee567efb7"

</p>
<p>
Next you can upload all the info in a notepad file
</p>
<br />

<p>
![25](https://github.com/user-attachments/assets/71dabde5-d174-4ceb-8965-5766ecba69c4"

</p>
<p>
Next type Virtual Machine in the search bar
</p>
<br />

<p>
![26](https://github.com/user-attachments/assets/91b1a200-7b93-44f5-9989-5f2c68b1cbbe"

</p>
<p>
![27](https://github.com/user-attachments/assets/fe0d8740-64f4-40f6-a0fd-7b0d5764574a"

</p>
<p>
Next you will see the VM has been created click VM1 and copy the public IP address 
</p>
<br />

<p>
![28](https://github.com/user-attachments/assets/560b1644-be4d-42e2-ba8f-ed156c6ad8e2"

</p>
<p>
Next type Remote Desktop Connection in the search bar
</p>
<br />

<p>
![29](https://github.com/user-attachments/assets/770529e4-93ab-44e7-b963-0469fb78c585"

</p>
<p>
Next type the public IP of VM1 in the computer seciton and click the connect buttton
</p>
<br />


<p>
![30](https://github.com/user-attachments/assets/701cfd92-193d-44cb-adb9-c873d4b42dcd"

</p>
<p>
Next type the username as labsuer and the password as the password you created, then click the blue ok button
</p>
<br />

<p>
![31](https://github.com/user-attachments/assets/dfbc0668-a062-420f-be88-50e34f959591"

</p>
<p>
Then click the yes button 
</p>
<br />

<p>
![32](https://github.com/user-attachments/assets/0afe1c11-46db-497e-b290-6261d5cbdf5f"

</p>
<p>
Then click no for all of the following in the image above
</p>
<br />

<p>
![33](https://github.com/user-attachments/assets/9ac4696c-4880-42db-a1a3-38bb0917c219"

</p>
<p>
Then once the networking tab loads click the yes button 
</p>
<br />

<p>
![34](https://github.com/user-attachments/assets/d2d8b1fb-d7aa-4eb8-b12a-fe998e3febfd"

</p>
<p>
Next load Microsoft Excel and click start without yuor data 
</p>
<br />

<p>
![35](https://github.com/user-attachments/assets/010af768-b964-4ed9-ab95-b5e4466dd30c"

</p>
<p>
Next click continue without this data
</p>
<br />

<p>
![36](https://github.com/user-attachments/assets/29100910-4f8b-41e0-93a6-413df96521f0"

</p>
<p>
Now click confirm and continue 
</p>
<br />

<p>
![37](https://github.com/user-attachments/assets/0745d60c-3eb5-464a-b4ae-8914b3fbb4e7"

</p>
<p>
Next click confirm and start browsing
</p>
<br />

<p>
![38](https://github.com/user-attachments/assets/2dce70d4-b96c-400c-a70a-ebb530511b9d"

</p>
<p>
Now type download wireshark in the search bar 
</p>
<br />

<p>
![39](https://github.com/user-attachments/assets/b323ca9a-69e4-4637-8ca3-f21d6543a8be"

</p>
<p>
Now click go to download 
</p>
<br />

<p>
![40](https://github.com/user-attachments/assets/6a036e16-41f7-4fe5-8f61-fac966575cdd"

</p>
<p>
Now click windows x64 installer 
</p>
<br />

<p>
![41](https://github.com/user-attachments/assets/9df32be4-c4ff-46b1-b216-91b9ece796ee"

</p>
<p>
Once the process is done click the file to open in or go to file explorer and open the file in the downloads folder
</p>
<br />

<p>
![42](https://github.com/user-attachments/assets/84b5c73d-11d0-4bb5-9a37-9d3ede41a8af"

</p>
<p>
Next go to file explorer and double click Wireshark to load the software
</p>
<br />

<p>
![43](https://github.com/user-attachments/assets/b4f4700c-785d-4183-942c-b58fb6f395c8"

</p>
<p>
Now click next
</p>
<br />

<p>
![44](https://github.com/user-attachments/assets/14c8b5b3-b248-412d-9302-ab3e8b121323"

</p>
<p>
Now click next 
</p>
<br />

<p>
![45](https://github.com/user-attachments/assets/8d3fec36-4e0b-418e-bc8b-099d7f1be191"

</p>
<p>
Now finally click Install
</p>
<br />

<p>
![46](https://github.com/user-attachments/assets/a7dcae0a-e870-4082-9bcb-1bc62dd86e1c"

</p>
<p>
The installation progess will start
</p>
<br />

<p>
![47](https://github.com/user-attachments/assets/b9390a9b-f4e9-429e-8127-50c01024fedd"

</p>
<p>
Once the process is done click finish 
</p>
<br />

<p>
![48](https://github.com/user-attachments/assets/e7883eb0-f224-40f9-b2c3-1f5ea98e9476"

</p>
<p>
Next type Wireshark in the search bar on the VM, then double click to open the software
</p>
<br />

<p>
![49](https://github.com/user-attachments/assets/3e9a1676-57b8-4f02-93b9-f94f97674537"

</p>
<p>
Next click the Ethernet on Wireshark
</p>
<br />

<p>
![50](https://github.com/user-attachments/assets/acadf030-2c99-4a0f-baa5-44c9ce113b94"

</p>
<p>
Now go back to Miscrosoft Azure and click VM2, copy the  IP or the Private IP address 
</p>
<br />

<p>
![51](https://github.com/user-attachments/assets/da942156-a705-4290-aca6-a35cfb6cb411"

</p>
<p>
Now open Windows Powershell and type ping (then type the private IP address) Example >>[ping 10.0.0.4] 
</p>
<br />

<p>
![52](https://github.com/user-attachments/assets/a148f6fe-58cc-49ea-9318-94215442a52a"

</p>
<p>
You can see that 4 packets where sent and received
</p>
<br />

<p>
![53](https://github.com/user-attachments/assets/e1014465-0cd4-4014-b717-3052914bc2fd"

</p>
<p>
Now we can ping a website to see the same results, ping www.google.com
</p>
<br />

<p>
![54](https://github.com/user-attachments/assets/b02fbe51-4880-4f49-a83a-150345fe3253"

</p>
<p>
Next we can do a endless ping by typing ping (then type the private IP address) -t Example >>[ping 10.0.0.4 -t] 
</p>
<br />

<p>
![55](https://github.com/user-attachments/assets/caf0784c-424e-42fc-830a-5422a59c058c"

</p>
<p>
Now go to Microsoft Azure and type Network Security Groups 
</p>
<br />

<p>
![56](https://github.com/user-attachments/assets/50af4dcf-dfc8-41cc-8464-dc4e6047e2d0"

</p>
<p>
Next click VM2 and then click +Add 
</p>
<br />

<p>
![57](https://github.com/user-attachments/assets/452b24ce-5d32-4672-834b-71b39d3ecc0c"

</p>
<p>
Now source can be under any, Protocol you need to click ICMP and the action will be deny, because we are going to deny the endless ping to stop. The priority needs to be lower than all the others for this example I put 200 and the name will be DENYICMPPINGFROMANYWHERE
</p>
<br />

<p>
![58](https://github.com/user-attachments/assets/34767b9e-1b69-401f-bea9-44b07c696b48"

</p>
<p>
Now if we go back to VM1 we can see the ping stop when can now click Ctrl + C to go back to the home on commandline
</p>
<br />

<p>
![59](https://github.com/user-attachments/assets/b19cbff3-d236-4e82-be1f-0f41659ba9e4"

</p>
<p>
Next type ssh in the search bar in Wireshark to see ssh traffic (SSH Stands for Secure Shell)
</p>
<br />

<p>
![60](https://github.com/user-attachments/assets/f98cb174-301d-4ac1-ac60-d7cba143b64d"

</p>
<p>
Next type dns in the search bar in Wireshark to see dns traffic (DNS stands for Domain Name Systems)
</p>
<br />

<p>
![61](https://github.com/user-attachments/assets/36cbafc5-b963-463f-a7fb-5b65a8533e41"

</p>
<p>
Next type rdp in the search bar in Wireshark to see rdp traffic (RDP stands for Romote Desktop Protocol)
</p>
<br />

<p>
![62](https://github.com/user-attachments/assets/356f0a70-8fb8-4f19-beb2-245119c3e00a"

</p>
<p>
Next each of these protocols have port numbers type tcp.port==22 this port is for ssh Secure Shell
</p>
<br />

<p>
![63](https://github.com/user-attachments/assets/8fd00a30-4d4e-488a-97d1-88757ee04ae3"

</p>
<p>
Next type udp.port==53 this port is for dns Domain Name System
</p>
<br />

<p>
![64](https://github.com/user-attachments/assets/b3840aef-54f7-46ef-b542-489af77233c5"

</p>
<p>
Next type tcp.port==3389 this port is for rdp Romote Desktop Protocol
</p>
<br />

<p>
![65](https://github.com/user-attachments/assets/1764e6ae-dfcd-446b-8e84-1206945d79b8"

</p>
<p>
Now go back to Microsoft Azure and copy the Public IP address or the Private IP address of VM2 
</p>
<br />

<p>
![66](https://github.com/user-attachments/assets/9c2f05cb-250e-491f-8fa8-aa5ffbc6f7f9"

</p>
<p>
Now go back to VM1 and type ssh labuser@ Public IP Address or Private IP Address. So this is using ssh to take into VM2 through VM1. ssh then the name of the VM which was labuser, then type the private or public IP address. Next type yes to allow the connection. Then type in your password the password wont show on the screen just have faith you are typing it correctly then press ENTER
</p>
<br />

<p>
![67](https://github.com/user-attachments/assets/760cd055-5cc1-4f5a-93b1-5d9133552e3b"

</p>
<p>
You will know it worked if you see a green name under labuser@VM2. Next type pwd (Print Working Directory) to show the directory 
</p>
<br />

<p>
![68](https://github.com/user-attachments/assets/7d312443-e1ec-426b-9313-b96403d963ae"

</p>
<p>
Now type id to show all the identification in VM2
</p>
<br />

<p>
![69](https://github.com/user-attachments/assets/a188cb32-97c2-42e8-a259-4287a5d714b0"

</p>
<p>
Now type ip to see all the list of ip commands 
</p>
<br />

<p>
![70](https://github.com/user-attachments/assets/db2fd451-1250-41aa-a773-1aaa3a8f9262"

</p>
<p>
Now to create a txt file we can type touch hi.txt this will create a hi txt file 
</p>
<br />

<p>
![71](https://github.com/user-attachments/assets/a3798fd0-05c9-4360-88fd-60ddf5456f99"

</p>
<p>
Now to see the txt file we just created type ls -lasth
</p>
<br />

<p>
![72](https://github.com/user-attachments/assets/72c67c0e-8aad-4c50-b5ff-8f5f7199928a"

</p>
<p>
Now we can also create multiple files at once by typing touch hi my name is. Anything after touch will be its own file created. Then type ls -lasth to see the files
</p>
<br />

<p>
![73](https://github.com/user-attachments/assets/1bfe0de5-0dec-4612-ba8a-cd6d9094768f"

</p>
<p>
Now type uname -a this shows a string with all the os info running on it
</p>
<br />

<p>
![74](https://github.com/user-attachments/assets/36d500d8-bad0-41dc-84ff-0e95f7e2170e"

</p>
<p>
Now to exit out of VM2 type exit 
</p>
<br />

<p>
![75](https://github.com/user-attachments/assets/7f440874-4263-4c06-a9d3-f2d53f34f916"

</p>
<p>
Next out of VM2 in the command line type nslookup this shows the IP or the DNS
</p>
<br />

<p>
![76](https://github.com/user-attachments/assets/ece5574b-bad2-4d54-9799-28bd0744ac2f"

</p>
<p>
Next type ipconfig in the command line this shows the current TCP/ IP also machine IP
</p>
<br />

<p>
![77](https://github.com/user-attachments/assets/be2e1578-6763-4f70-9fed-97ce5ce5cd69"

</p>
<p>
Now go back to Microsoft Azure and go to the Resource Groups we created. Click RG-LAB-02 and retype it in the delete section, then click the red delete button
</p>
<br />

<p>
![78](https://github.com/user-attachments/assets/a38408db-a501-4dcf-98e4-c1fc8faae036"

</p>
<p>
Now go to the NetworkWatcherRG and delete that one as well
</p>
<br />
