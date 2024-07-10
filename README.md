<p align="center">
<img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/7ddd433c-a1ae-4f50-8075-20cd11ef33c0"/>
</p>

<h1>Exploring Active Directory</h1>

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computers)
- Remote Desktop Protocol (RDP)

<h2>Creating Organizational Units (OUs)</h2>

<p>
(OUs) are containers that help organize and manage objects such as users, groups, computers, and other OUs within a domain. OUs provide a way to logically group resources for easier administration and to apply policies. 
</p>

<p>
To create an OU you must:

<ol>
  <li>Open Server Manager</li>
 
  <li>Select Tools located in the top-rigth of the screen.</li>
  
  <li>In the tools drop down list select "Active Directory Users and Computers"</li><br></br>
  <img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/641b6798-fcae-4b7b-b5eb-9ac8a6809e34"/><br></br>
  
  <li>In ADUC my domain is on the right side, if I click the arrow I'll see folders. When Active Directory is intalled it comes with one default OU called Domain Controllers. These are where future DCs that may be added to the domain are located. You can tell its   an OU becasue of the yellow like book symbol in the folder.</li><br></br>
  <img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/089c7fea-b045-4808-9e09-190c73dd7f29"/><br></br>

  <li>To create the OU, right-click the domain name -> New -> Organizational Unit</li><br></br>
  <img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/ed14f89b-72a0-44f7-983d-d6d5f562cff8"/><br></br>

  <li>Name it and it will be created. Im going to make two OUs. One will be for Admins and the other for Employees. You should see them added to the list.</li><br></br>
  <img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/b287b23f-5e63-4d80-8e67-2e613761e1d9"/><br></br>

  <h4>Creating OUs in AD is really simple. Next I'll create Users to add to these OUs that will be able to sign-in to the Client-1 computer I made in <a href="https://github.com/SpyderSec30/Active-Directory-within-Azure">Active-Directory-within-Azure
</a>I'll add that computer to the domain after I create the users.</h4>
</ol>
</p>

<h2>Creating Users inside OUs</h2>
<p>
Creating Users is also a simple process, you just right-click the OU you want the user to be in and go to New -> Users. <br></br>
<img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/ad4cfc49-9543-494f-8fe7-c013da505c38"/><br></br>

<h4>Jane Doe will be my Admin</h4>
<img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/b1e9345f-4400-402f-8c72-53258fe28a50"/><br></br>

If you double-click a user, you can view there Properties. In here you can adjust user information.<br></br>
<img src="https://github.com/SpyderSec30/Working-with-Active-Directory/assets/174487140/c7237834-c2c6-4a08-b07b-4fea3d005722"/><br></br>

The Account tab is where you can unlock a user account if they ever go over the password entry limit and they get locked out. <br></br>
<img src="https://github.com/SpyderSec30/Working-with-Active-Directory/assets/174487140/8de070bc-bf86-495f-a545-731362452b51"/><br></br>

By clicking Logon Hours, you can adjust the time in which that user is allowed to log in to the domain. With the Log On To you can control which computers they're allowed to use.<br></br>
<img src="https://github.com/SpyderSec30/Working-with-Active-Directory/assets/174487140/bbeb7402-09bd-47c9-abe5-376344923f96"/><br></br>

Resetting a password is not that hard either. Just simply right-click the user and choose "Reset Password". You'll also notice this is where you can disable an account as well.<br></br>
<img src="https://github.com/SpyderSec30/Working-with-Active-Directory/assets/174487140/3a050867-2db3-47f3-8e6c-46fd38ff738e"/><br></br>

<h4>I'll create a user for the EMPLOYEES OU. Then I'll finish this Lab by adding Client-1 to the domain.</h4>
</p>

<h2>Adding Client-1 to the Domain</h2>
<p>
The process of adding a computer to a domain is not that complicated. The first and most important thing to do is make DC1 the primary DNS server of Client-1. We can do that by:

<ol>
  <li>Use the Windows run utility and type control to get to the control panel.</li><br></br>
  <img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/9b9dfef5-42a9-4906-95de-a2c588f01a1a"/><br></br>

  <li>From the Control panel click Network and Internet.</li><br></br>
  <img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/c22651e3-c544-407c-8f4f-b9ec0af3c77f"/><br></br>

  <li>Inside of Network and Internet click Network and Sharing Center.</li><br></br>
  <img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/8490ac30-917a-40b9-b874-f2b5230da294"/><br></br>

  <li>Inside on the left click Change adapter settings.</li><br></br>
  <img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/72c1d500-dc4c-46b5-9313-7f2abc0e596c"/><br></br>

  <li>Right-click the adapter and go to properties.</li><br></br>
  <img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/ce6dee14-f264-4d9c-a2f6-93d1de63dcd4"/><br></br>

  <li>Higlight Internet Protocol Version 4 (TCP/IPv4) and click Properties.</li><br></br>
  <img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/40871e9f-c4e9-4e7f-911d-da7fd64fd2a1"/><br></br>

  <li>Check the circle that says "Use the following DNS server address" and enter DC1's private IP address in the Preferred DNS server.</li><br></br>
  <img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/da1e40b0-d72d-49a0-abb4-2e4e6ae88d58"/><br></br>

  <li>After I did this I went back to the Azure portal and restarted Client-1.</li><br></br>

  <li>Once restarted, use RDP to connect back to Client-1. After you connect, right-click the windows buttom and select System.</li><br></br>

  <li>In the System Setting on the right hand side click Rename this PC (advanced).</li><br></br>
  <img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/d6997dac-b238-4f71-8fa0-86b19f59e7f2"/><br></br>

  <li>Select change</li><br></br>
  <img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/063f6e3b-7d7f-4330-ab75-2bcfe65984ec"/><br></br>

  <li>Check the Domain circle and enter the domain name.</li><br></br>
  <img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/04bd4030-2daa-4514-9166-ce10a33fc9fe"/><br></br>

  <li>Enter the Admin Jane Doe's credentials</li><br></br>
  <img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/3010c6e6-57ab-4610-aeed-1d99e1b4d34b"/><br></br>

  <li>Succesfully added Client-1 to testdomain.com</li><br></br>
  <img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/933c68f8-5162-4dce-9ddc-9df87e462981"/><br></br>

  <li>You can Verify this by going back to DC1 and in the computers folder you should see Client-1</li><br></br>
  <img src="https://github.com/SpyderSec30/Active-Directory-within-Azure/assets/174487140/63070d07-db31-4fa2-81dc-4750637b1206"/><br></br>
</ol>
</p>

<h2>Finished</h2>
<p>
In this lab I have demonstrated how to create OUs, Create Users, Reset Passwords, Disable Accounts, Recover locked out Accounts, and join computers to a domain. These are one of many ways to do so in Active Directory
</p>








