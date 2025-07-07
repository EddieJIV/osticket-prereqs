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

<h2>Step 1: Create a new resource group in Microsoft Azure </h2>
<img src="https://github.com/user-attachments/assets/2167d261-c2fd-4211-96ae-76be7f8c904b" height="100%" width="80%" alt="RG Create 1a"/>

 - Type, "Resource Group" in the Search bar, or navigate to the "Resource Group" section of Azure.
 - Click "Create" once you have navigated to the Resourse Group Home Page.
   
<img src="https://github.com/user-attachments/assets/b8828d30-a118-4a5e-ad33-bb64bbff2ef6" height="auto" width="auto" alt="RG Create 1b"/>

  
You will then be prompted to name the Resource Group, and Select the region of that Resource group. 
  
- We will name the resource group, "osTicket"
- Make the region that it is in local to you. I am selecting <strong>(US) East US 2</strong> but choose the region local to you.
- Click "Review & Create"
  
Following this, you will be prompted to review your new Resource Group. 
  - Make sure that it is named properly and in the correct region.
  - Click "Create" once more, confirming the process.

Congratulations!  
 You have sucessfully set up the Resource Group necessary for installing osTicket on a Virtual Machine in Azure.  
 To proceed to the next step, navigate back to the home page.


<h2>Step 2: Creating your Virtual Machine</h2>

  <img src="https://github.com/user-attachments/assets/cb002a5d-5533-4af2-ab18-ec50e63577dd" height="auto" width="auto" alt="VM Create 1"/>
  
  - Type, "Virtual Machine" in the Search bar, or navigate to the "Virtual Machine" section of Azure.
  - Click "Create"
  - Select the top option "Virtual Machine".

<p>
<img src="https://github.com/user-attachments/assets/86b772bf-dced-470d-9ce4-dc1f68fb0013" height="auto" width="auto" alt="VM Create 2"/>
</p>

You will be prompted to select your Resource Group, name your Virtual Machine, and select the region of the machine. 

 - Select the Resource Group "osTicket" you just created.
  
 - For the sake of this lab, we will name our Virtual Machine "osTicket-VM"

 - Make sure that the zone you select is the same zone as your resource group. For me that is (US) East US 2

 - Keep the Availability, Zone, and Security Options the pre-selected default options.

<p> Moving down along: 
  <p>
<img src="https://github.com/user-attachments/assets/af275a44-b058-43ee-af50-0d4a6068d984" height="auto" width="auto" alt="VM Create 3"/>
</p>

 - Select the image the VM will use.
     - For this lab we are looking to use a <Strong>Windows 10 pro, version 22H2 - x64 Gen2 </Strong>
 
 - For size, locate the <strong>Standard_D2s_v3 - 2vCPU, 8 Gib  </strong>
 
 - Do not worry about the VM Architecture, or checking the other two boxes (as seen above)

<p> Continuing down: <p/>
<p></p><img src="https://github.com/user-attachments/assets/e4f02ad8-9258-490f-900a-e113cf07741a" height="auto" width="auto" alt="VM Create 4"/><p/>

- Create your Administrator username and password for this VM.
   - For this lab, I have picked a username of "labuser" with a password of "Cyberlab123!" 
- Leave the Inbound Port Rule Section alone.
- Check the licensing box
- You do **not** have to click Next: Disks, simply click Review + create!

<p>
<img src="https://github.com/user-attachments/assets/8df602eb-553e-4076-abed-f844aea16c5d" height="auto" width="auto" alt="VM Create Final"/>
</p>

- Once you see that your VM is validated, review your VM, make sure everything looks correct in the Subscription, Resource Group, VM-Name, and Region section.
- Following your double check of information on the VM you can click create one more time to initialize the deployment of your VM!

Congratulations!  
At this point, we have completed the first two major steps of this lab by creating and deploying a Resource Group and Virtual Machine within Azure that we will subsequently install, configure, and deploy osTicket inside of!


<h2>Step 3: Access VM using Remote Desktop Connection: </h2>


<img src="https://github.com/user-attachments/assets/fd114353-8573-4c68-857e-d853d156b0ea" height="auto" width="auto" alt="Obtain IP"/>

- Obtain the Public IP Address of your VM from its home page within Azure.
- Copy the IP Address to your clipboard

<img src="https://github.com/user-attachments/assets/73f3f209-a75f-4ed4-a9a0-04175d1ae723" height="auto" width="auto" alt="RDP"/>

- Where it says, "Computer" paste the public IP address of your VM and click, "Connect".

<img src="https://github.com/user-attachments/assets/a6b90641-cf35-4329-9a71-cba66416997a" height="auto" width="auto" alt="login"/>

- Enter the Administrator Account login information you created earlier while setting up your VM and hit OK!

 <img src="https://github.com/user-attachments/assets/0fb5c892-4c05-43db-bf6e-054e6c0bf8d6" height="auto" width="auto" alt="Cert Warning"/>

- If you are subsequently prompted with a certificate warning, it is OK to bypass it and say "Yes" to connect!
- While your VM is spinning up for the first time, give yourself a pat on the back, and get some coffee or water, because now the fun really begins!

## Step 4: Downloading osTicket Dependencies 

<img src="https://github.com/user-attachments/assets/dc11857c-95b1-4c4c-ae11-f5ae6942dfd8" height="auto" width="auto" alt="Install ZIP"/>

- Once you've gotten into your VM, copy the osTicket Installation Files link below, and paste it into the Microsoft Edge browser. This will take you to the zip file containing what we need to install osTicket to the VM.
  - [osTicket Installation Files](https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0)
  - Click "Download anyway"

<img src= "https://github.com/user-attachments/assets/032397b7-52ac-427b-a4c5-6f2aa8fc9853" height="auto" width="auto" alt="ZIP"/>

- Navigate to the "Downloads" section of your file explorer and locate the osTicket-Installation-Files zip file.
- Left Click the file and drag it to your desktop.
 
<img src="https://github.com/user-attachments/assets/fc2a9720-dbed-4487-8a5a-88aa4e6f65b6" height="auto" width="auto" alt="Extract All"/>

- Right click on the osTicket-Installation-Files ZIP file that is now on your desktop and click on "Extract All".

<img src="https://github.com/user-attachments/assets/f3ae48a9-14b3-4d54-88b5-e34aaf824df7" height="auto" width="auto" alt="Extract ZIP"/>

- Simply click extract from here. Your unzipped files will then appear on your desktop.

<img src="https://github.com/user-attachments/assets/37db4dbb-131e-4e64-8561-97946735a1e2" height="auto" width="auto" alt="Unzipped install file"/>

- Note that these are the files we are going to be working with and in. NOT the zip file.
  - Feel free to move the folder anywhere on the desktop that best suits you.

## Step 5: Enable IIS (Internet Information Services)

<img src="https://github.com/user-attachments/assets/fb806ab6-5659-487b-8287-4bc82193253e" height="auto" width="auto" alt="Control Panel 1"/>

- Open up Control Panel and Click on "Programs"
- Then, click on, "Programs and Features"
- Once you've navigated to Control Panel > Programs > Programs and Features, Click on "Turn Windows features on or off"

<img src="https://github.com/user-attachments/assets/e03dfba5-8887-4e65-a2b7-67f276cbda60" height="auto" width="auto" alt="IIS Enabled"/>

- Once you've clicked on "Turn Windows features on or off" within Programs and Features, find Internet Information Services
  - Check the box so it is black, as seen above, and click the box to the left of that to expand it.  

<img src="https://github.com/user-attachments/assets/ed3fae94-4606-4bdc-ad0b-fdee0ee6e459" height="auto" width="auto" alt="CGI"/>

 - We need to install CGI, a dependency that OSticket needs for part of the web server, within World Wide Web Services
 - Click "OK" once you've navigated to World Wide Web Services > Application Development Features > CGI and Check-marked the file folder named, "CGI"
   - It will now install the web server. Give it a moment to do so.

 ## Step 6: Install PHP Manager

<img src="https://github.com/user-attachments/assets/e47f81b1-6f38-4ca6-91ac-dc7b4b10ef28" height="auto" width="auto" alt="PHP Install Location"/>

- From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
  - Agree to the licensing terms and install the program.
 
<img src="https://github.com/user-attachments/assets/eb707506-fcea-4497-9663-588a1371d998" height="auto" width="auto" alt="PHP Installed"/>

- Once the installation is complete, you will see this screen. Simply hit close.
- Be advised: the next step is going to take place from within out osTicket installation folder as well.
 
## Step 7: Install Rewrite Module

<img src="https://github.com/user-attachments/assets/f0166aa0-73eb-4a5a-a48d-073846943de9" height="auto" width="auto" alt="Rewrite Module Location"/>

- Next, we are going to install the Rewrite Module.
- Double click the file to be brought to the install wizard

<img src="https://github.com/user-attachments/assets/5ee12ebc-32af-460f-99f8-b2b67e8091a4" height="auto" width="auto" alt="Rewrite install wizard"/>

- Accept the terms in the License Agreement
- Click Install
- Hit Finish upon completion of the same.

## Step 8: Create PHP Directory

<img src="https://github.com/user-attachments/assets/40c775f7-e1f9-49c8-8c55-b59a6bea0f25" height="auto" width="auto" alt="PHP Directory set-up"/>

- Right click on the file explorer on your taskbar and open a new file explorer page for this step.
  - Navigate to This PC > Windows C: in your new file explorer page

<img src="https://github.com/user-attachments/assets/216a32ac-10d3-4666-b8a5-db23b7cb31c2" height="auto" width="auto" alt="New Folder in C: drive"/>

- From within the C: drive create a new folder
- The easiest way to do so would be to simply right click from within the C: drive, locate the "New" tab and click on "Folder".

<img src="https://github.com/user-attachments/assets/8cce1614-9f7d-425b-ace4-83c019d5d032" height="auto" width="auto" alt="PHP"/>

- Name the new file "PHP". It should look like this in your C: Drive.

<img src="https://github.com/user-attachments/assets/9833d4fa-fc48-41fc-afe9-e0086616458f" height="auto" width="auto" alt="Extract to new folder"/>

- From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into your new “C:\PHP” folder.
- To do so, simply right click the ZIP file named php-7.3.8-nts-Win32-VC15-x86.zip, and Click "Extract All..."

<img src="https://github.com/user-attachments/assets/f7e98281-7bdf-4438-9e3a-1234812d6b50" height="auto" width="auto" alt="Browse to"/>

- Once you click "Extract All..." you will be prompted to browse to a folder or click extract.
- From here, we want to click browse, then navigate to Windows(C:) > PHP, and click, "Select Folder".

<img src="https://github.com/user-attachments/assets/c21340d8-2778-4d3c-a373-d221870bae4b" height="auto" width="auto" alt="Extract Location"/>

- This is what your extract Folder should look like PRIOR TO EXTRACTING.
- Once it looks like this, hit "Extract"

<img src="https://github.com/user-attachments/assets/a0dd20fd-c0ff-4e31-8db4-875cd6e99526" height="auto" width="auto" alt="NEW PHP"/>

- This is what your newly created PHP folder should now look like post extraction.

## Step 9: Install VC_redist.x86

<img src="https://github.com/user-attachments/assets/e3fb652b-63f0-4002-8306-ba7ac1e9cb05" height="auto" width="auto" alt="Step 9"/>

- Going back into your osTicket-Installation-Files folder, install VC_redist.x86.exe
- Once you double click, agree to the terms and click Install.

## Step 10: Install, "mysql-5.5.62-win32" database

<img src="https://github.com/user-attachments/assets/cbaee797-2eb9-4929-83d6-be3aa4f245d3" height="auto" width="auto" alt="Step 10"/> 

- Double click the file folder named, "mysql-5.5.62-win32"
- Hit "Next"

<img src="https://github.com/user-attachments/assets/15649a9c-9fe5-497b-987c-ef478b724947" height="auto" width="auto" alt="10.2"/>

- Accept the End-User License Agreement by checking the box and hit "Next"

<img src="https://github.com/user-attachments/assets/306361b5-186a-42fb-865e-c2efd15bee65" height="auto" width="auto" alt="10.3"/>

- For our installation, we want to do a "Typical Installation"
- So, make sure Typical is selected and click, "Next"
- Once you are brought to the next page, click on, "Install".

<img src="https://github.com/user-attachments/assets/e0c9bbd1-4874-4952-9865-de4ed309b323" height="auto" width="auto" alt="10.4"/>

- Make sure that the box to launch the MySQL Instance Configuration Wizard is checked.
- Click on Finish 

<img src="https://github.com/user-attachments/assets/1a7df3c5-c7bb-46fd-9164-bbe392f511cb" height="auto" width="auto" alt="10.5"/>

- From here, simply click "Next >"

<img src="https://github.com/user-attachments/assets/2cdce0f9-10a2-46d7-83e0-37ff0a2ec50a" height="auto" width="auto" alt="10.6"/>

- From here, we want to select "Standard Configuration" and click "Next >".

<img src="https://github.com/user-attachments/assets/8d206d2b-80ff-4904-83d7-234c56d332fe" height="auto" width="auto" alt="10.7"/>

- Leave this screen alone, and hit "Next >"

  
⚠️ Please be advised, the next step is very important ⚠️ 
---

Once you are prompted with the following screen:

<img src="https://github.com/user-attachments/assets/6e7f455c-f16c-427c-a32a-06c187a92888" height="auto" width="auto" alt="IMPORTANT 10.8"/>

 - Just type the word, "ROOT" in both the boxes.
 - It may sound simple, but MAKE SURE you type in ROOT in all capital letters in both boxes.
 - Later on, the username will be root but the password is ROOT.
    - This would be really bad in the real world but we're keeping simple for this project.
 - Click Next, Execute on the next screen, and then Finish.

## Step 11: Internet Information Services (IIS) Manager Configuration

<img src="https://github.com/user-attachments/assets/cbcf84ee-00de-4eb8-92bd-2c34d7401c3e" height="auto" width="auto" alt="IIS Location"/>

- Next, we are going to open up IIS as an Administrator
- It is important to be aware that we are running it is as an Admin and NOT just clicking open.
- To get to IIS manager we can just type "iis" into the search bar and it will appear.
- Again, remember to click, "Run as administrator".

<img src="https://i.imgur.com/DJmEXEB.png" height="auto" width="auto" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/DJmEXEB.png" height="auto" width="auto" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/DJmEXEB.png" height="auto" width="auto" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/DJmEXEB.png" height="auto" width="auto" alt="Disk Sanitization Steps"/> 

<img src="https://i.imgur.com/DJmEXEB.png" height="auto" width="auto" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/DJmEXEB.png" height="auto" width="auto" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/DJmEXEB.png" height="auto" width="auto" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/DJmEXEB.png" height="auto" width="auto" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/DJmEXEB.png" height="auto" width="auto" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/DJmEXEB.png" height="auto" width="auto" alt="Disk Sanitization Steps"/> 
