<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)

<h2>Lab Prerequisites</h2>

- PC or Laptop
- Connection to the Internet
- Microsoft Azure Subscription

<h2>Installation Steps</h2>
<strong><em> Assuming you have a Microsoft Azure account & subscription, please log in and proceed with the following:</em> </strong>

<h2>Step 1: Create a new resource group in Microsoft Azure: </h2>
<img src="https://github.com/user-attachments/assets/2167d261-c2fd-4211-96ae-76be7f8c904b" height="60%" width="80%" alt="RG Create 1a"/>
<p>Type, "Resource Group" in the Search bar, or navigate to the "Resource Group" section of Azure and click "Create".
<img src="https://github.com/user-attachments/assets/b8828d30-a118-4a5e-ad33-bb64bbff2ef6" height="80%" width="80%" alt="RG Create 1b"/>
<p> You will then be prompted to name the Resource Group, and Select the region of that Resource group.<br /> We will name the resource group, "osTicket" and the region that it is in will be local to you.<br /> I am selecting <strong>(US) East US 2</strong> but you can choose the region local to you.</p>
<p>Following this, you will be prompted to review your new Resource Group prior to creating. Make sure that it is named properly, and in the correct region, and click "Create" once more, confirming the process.</p>
<p>Congratulations! You have sucessfully set up the Resource Group necessary for installing osTicket on a Virtual Machine in Azure. To proceed to the next step, navigate back to the home page. </p>


<h2>Step 2: Creating your Virtual Machine:</h2>
<p>Type, "Virtual Machine" in the Search bar, or navigate to the "Virtual Machine" section of Azure and click "Create".<br>Select the top option "Virtual Machine".<br/></p>
  <img src="https://github.com/user-attachments/assets/cb002a5d-5533-4af2-ab18-ec50e63577dd" height="80%" width="80%" alt="VM Create 1"/>
<p> You will be prompted to select your resource group, name your Virtual Machine, and select the region of the machine. <br> Select the Resource Group "osTicket" you just created.<br/> 
<br> For the sake of this lab, we will name our Virtual Machine "osTicket-VM"<br/>
<br> Keep the Availability, Zone, and Security Options the pre-selected default options.


<p>
<img src="https://github.com/user-attachments/assets/86b772bf-dced-470d-9ce4-dc1f68fb0013" height="80%" width="80%" alt="VM Create 2"/>
</p>
<p> Moving down along: <br>Select the image the VM will use. For this lab we are looking to use a <Strong>Windows 10 pro, version 22H2 - x64 Gen2 </Strong><br/><br>For size, locate the <strong>Standard_D2s_v3 - 2vCPU, 8 Gib  </strong> <br> Do not worry about the VM Architecture, or checking the other two boxes (as seen below)<br/>

<p>
<img src="https://github.com/user-attachments/assets/af275a44-b058-43ee-af50-0d4a6068d984" height="80%" width="80%" alt="VM Create 3"/>
</p>
<p> Continuing down, create your Administrator username and password for this VM.<br>For the sake of simplicity, I have picked a username of "labuser" with a password of "Cyberlab123!"<br/>
<p>You may pick a username and password that suits your choosing, as long as you keep note of the same!</p>
<p> Leave the Inbound Port Rule Section alone.</p>
<p> Make sure to check the licensing box, and click review + create!</p>

<p>
<img src="https://github.com/user-attachments/assets/e4f02ad8-9258-490f-900a-e113cf07741a" height="80%" width="80%" alt="VM Create 4"/>
</p>
<p>
Once you see that your VM is validated. Review your VM, make sure everything looks correct in the Subscription, Resource Group, VM-Name, and Region section.<br> Following your double check of information on the VM you can click create one more time to initialize the deployment of your VM!
</p>
<br />
<p>
<img src="https://github.com/user-attachments/assets/8df602eb-553e-4076-abed-f844aea16c5d" height="80%" width="80%" alt="VM Create Final"/>
</p>
<p>
Congratulations! At this point, we have completed the first two major steps of this lab by creating and deploying a Resource Group and Virtual Machine within Azure that we will subsequently install, configure, and deploy osTicket inside of!
<h2>Step 3: Access VM using Remote Desktop Connection: </h2>
</p>
<br /><p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br /><p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br /><p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br /><p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br /><p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br /><p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br /><p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br /><p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
