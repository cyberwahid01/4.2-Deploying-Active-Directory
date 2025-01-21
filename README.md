<p align="center">
<img src="https://i.imgur.com/9JmwJSF.png" alt="osTicket logo"/>
</p>

<h1>Active Directory: Configuring and Deploying Active Directory 🪟</h1>
In this section of the Active Directory lab, I run through the process of promoting the Server to a Domain Controller, Creating Organisational Units, Creating Users, Promoting Users as Admins, Remotely Connecting to the Client Domain from the Server and Keeping the Domain Properties Organised. 

(Link Back to Main Project Contents Page is at the Bottom of this Repo)
<h2>Environments and Technologies Used</h2>

- Lenovo Ideapad 5 Pro 16gb AMD Ryzen 7
- Microsoft Azure Resource Group
- Microsoft Azure Windows 10 Pro version 22H2 - x64 Gen2 Virtual Machine
- Microsoft Azure Windows Server 22 Datacenter: Azure Edition - x64 Gen2 Virtual Machine
- osTicket Software and File Dependencies

<h2>Operating Systems Used </h2>

- Local Windows 11 Home Version 21H2</b>
- Windows 10 Pro Version 22H2 Virtual Machine
- Windows Server 22 Datacenter: Azure Edition - x64 Gen2 Virtual Machine
  
<h2>List of Prerequisites</h2>

- Microsoft Azure Subscription
- Microsoft Azure Subscription Credit 

<h2>Installation, Setup, Resource Setup, Executing Functions</h2>
1. To start off we need to Install the Active Directory Domain Services role to our server. Once we have selected AD DS, we choose the necessary role features that will be installed with AD DS, including GPM (Group Policy Management) tools. 
</p>
<br />

<img src="https://i.imgur.com/E81TLti.png" alt="1"/>
</p>
<p>
2. Here we can see the final page before installing the Domain Services.
</p>
<br />

<p>
<img src="https://i.imgur.com/ruXgyrg.png" alt="2"/>
</p>
<p>
3. In order to utilise the installed Domain Services, we must promote the server to be a Domain Controller.
</p>
<br />

<p>
<img src="https://i.imgur.com/NkwGTLb.png" alt="3"/>
</p>
<p>
4. We add a new forest and configure the Root Domain Name for our domain.
</p>
<br />

<p>
<img src="https://i.imgur.com/jmyWcas.png" alt="4"/>
</p>
<p>
5. Once we have Configured all the necessary settings such as making sure the correct DNS Options have been chosen, we can install and deploy the Domain Controller.
</p>
<br />

<p>
<img src="https://i.imgur.com/Cj9OSbi.png" alt="5"/>
</p>
<p>
6. Here we can see confirmation that we have been automatically logged into our server as the domain we created during the deployment of the Domain Controller.
</p>
<br />

<img src="https://i.imgur.com/l7BlMtD.png" alt="6"/>
</p>
<p>
7. At this stage, we can now go into our Active Directory Users and Computers program and see "mydomain.com" successfully showing up as a domain that we can manage.
</p>
<br />

<p>
<img src="https://i.imgur.com/U7X5wUa.png" alt="7"/>
</p>
<p>
8. At this stage, we can go ahead and start executing some functions within our domain. In this instance we are creating some Organizational Units which are used to organise Users into certain categories. In our case we are organising them via "_EMPLOYEES" and "_ADMINS and later as "_CLIENTS". We do this by right-clicking the domain itself, hovering into the "New" menu and choosing "Organizational Unit"
</p>
<br />

<p>
<img src="https://i.imgur.com/PjC1E6f.png" alt="8"/>
</p>
<p>
9. In this slide we can now see, within our domain drop-down menu, two new folders corresponding to our Organisational Units. These folder will be where we place Users based on their categorization within our Organization. The next step will be to create a User whom we will then go on to categorise and assign as an Admin.
</p>
<br />

<p>
<img src="https://i.imgur.com/mfoZyCu.png" alt="9"/>
</p>
<p>
10. Here we can see we have created a user named Jane Doe and she has been placed in the Admin folder. Please note at this stage she has not been assigned the Administrator role or privileges, she has simply been organised into the correct designated category folder. We created "Jane Doe" by again right-clicking our domain and this time choosing the "User" option, creating her profile and assigning her to the Admin category.  
</p>
<br />

<img src="https://i.imgur.com/h7Ouh0j.png" alt="10"/>
</p>
<p>
11. At this stage we still need to assign Jane Doe the actual administrator role and make her an Admin User. We do this by right-clicking her user profile, choosing properties, clicking on the "Member Of" tab. Within  the Member Of tab, we click on "Add..." at the bottom, and add her into the "Domain Admins" category by choosing _ADMIN when we assign her the role. 
</p>
<br />

<p>
<img src="https://i.imgur.com/ahrPzd3.png" alt="11"/>
</p>
<p>
12. To enable us to log into our Client Computer as "Jane Doe" we need to assign login details to her account. She has been given the logon name "jane_admin" and her password was set in another menu. 
</p>
<br />

<p>
<img src="https://i.imgur.com/EpMcykM.png" alt="12"/>
</p>
<p>
13. Here we can see a successful login to Jane Does account within our Client computer and confirmation that she has is indeed an Administrator.
</p>
<br />

<p>
<img src="https://i.imgur.com/Re8GAJo.png" alt="13"/>
</p>
<p>
14. The next slide is to reiterate that our Clients DNS Servers are pointing to the Static IP address of the Domain Controller Server within Microsoft Azure. This will allow us to configure our Client computer as a member of the Domain we are controlling via the Domain Controller. 
</p>
<br />

<img src="https://i.imgur.com/jNQcgr3.png" alt="14"/>
</p>
<p>
15. Here, within our Client computer, we are making the Client machine a member of "mydomain.com" so it can be controlled via our Domain Controller. This is done by going into the "Computer Name/Domain Changes" menu within the system properties of the Client machine. In order to join the domain we enter the login details of Jane Doe who has permission to join the domain as an Administrator.
</p>
<br />

<p>
<img src="https://i.imgur.com/c6geY36.png" alt="15"/>
</p>
<p>
16. After successfully entering the login details we have connected to "mydomain.com"
</p>
<br />

<p>
<img src="https://i.imgur.com/8dbJOu9.png" alt="16"/>
</p>
<p>
17. Back in our Domain Controller,  when we go to the "Computers" folder of our domain, we can see our Client machine "Client-1-AD" has been added to the domain as a member.
</p>
<br />

<p>
<img src="https://i.imgur.com/9NX9xbj.png" alt="17"/>
</p>
<p>
18. At this end stage, to organise the domain, we have created an Organisational Unit named _CLIENTS and placed our Client machine inside this folder.
</p>
<br />

<p>
<img src="https://i.imgur.com/HtIqBq0.png" alt="18"/>
</p>
<p>  
LINK BACK TO THE MAIN PROJECT CONTENTS PAGE - https://github.com/cyberwahid01/Azure-Compute-and-Networking
