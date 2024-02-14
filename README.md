# Log-Observation
<h3 dir="auto" tabindex="-1">We will create our Subscription and Resources, then go over Failed Authentication and Log Observation.</h3>
<h4 dir="auto" tabindex="-1">Environments and Technologies Used</h4>
<ul dir="auto">
 	<li>Microsoft Azure</li>
 	<li>SQL Server</li>
 	<li>Event Viewer</li>
</ul>
<h3 dir="auto" tabindex="-1"><a id="user-content-operating-systems-used" class="anchor" href="https://github.com/fnabeel/Cloud-SOC-PreReq#operating-systems-used" aria-hidden="true"></a>Operating Systems Used</h3>
<ul dir="auto">
 	<li>VM Windows 10 PRO (21H2)</li>
</ul>
<h4 dir="auto" tabindex="-1">Actions and Observations<b></b></h4>
<ul>
 	<li>Create Windows 10 Pro Virtual Machine</li>
 	<li>Name the Resource Group: RG-Cyber-Lab</li>
 	<li><a href="https://vikaspatel.tech/wp-content/uploads/2023/04/6-1.png">
  <img class="alignnone size-full wp-image-180" src="https://vikaspatel.tech/wp-content/uploads/2023/07/Screenshot-from-2023-07-09-10-34-10.png" alt="" />
</a>
</li>
 	<li dir="auto">
<h5>Configure Network Security Group (Layer 4 Firewall) to allow all traffic inbound</h5>
</li>
 	<li>
<h5 dir="auto">A mini firewall will be configured for our virtual machine to allow all traffic in. We want to make this firewall look enticing to allow threat actors such as hackers, bots, and attackers to try to get into our virtual machine.</h5>
</li>
 	<li>
<h5 dir="auto">In resource groups, we will go inside it, and we can see all the things associated with the VM being created.</h5>
</li>
 	<li>
<h5 dir="auto">We will edit, the network security group, either by search or in the resource groups.</h5>
</li>
 	<li>
<h5 dir="auto">Based on the traffic coming into the network we can see the priority categorized in Azzure based on the set rules/protocols.</h5>
</li>
 	<li>
<h5 dir="auto">Create Inbound Security Rule, Any, Name it "DANGERAllINBound"</h5>
</li>
</ul>
&nbsp;

<ul>
 	<li>
<a href="https://vikaspatel.tech/wp-content/uploads/2023/04/6-1.png">
  <img class="alignnone size-full wp-image-180" src="https://vikaspatel.tech/wp-content/uploads/2023/07/Screenshot-from-2023-07-09-10-39-28.png" alt="" />
</a>
  
<a href="https://vikaspatel.tech/wp-content/uploads/2023/04/6-1.png">
  <img class="alignnone size-full wp-image-180" src="https://vikaspatel.tech/wp-content/uploads/2023/07/Screenshot-from-2023-07-09-10-34-10.png" alt="" />
</a>
    
  </li>
</ul>
&nbsp;
<ul>
 	<li>
<h5 dir="auto">Now try to ping the IP Address of the VM in CMD...<a href="https://vikaspatel.tech/wp-content/uploads/2023/04/6-1.png">
  <img class="alignnone size-full wp-image-180" src="https://vikaspatel.tech/wp-content/uploads/2023/07/Screenshot-from-2023-07-09-10-41-56.png" alt="" />
</a>
</h5>
</li>
 	<li><h5 dir="auto"> It didn't work because we need to remote in and change the firewall setting within the VM as well.</h5></li>
 	<li>
<h5>Now observe the changes in Terminal<a href="https://vikaspatel.tech/wp-content/uploads/2023/04/6-1.png">
  <img class="alignnone size-full wp-image-180" src="https://vikaspatel.tech/wp-content/uploads/2023/07/Screenshot-from-2023-07-09-10-46-17.png" alt="" />
</a></h5>
</li>
</ul>
&nbsp;
<ul dir="auto">
 	<li>
<h5 dir="auto">Install SQL server evolution</h5>
</li>
 	<li>
<h5 dir="auto">You can download from <span style="color: #ffff00;"><a style="color: #ffff00;" href="https://www.microsoft.com/en-us/evalcenter/download-sql-server-2022">here</a></span></h5>
</li>
 	<li>
<h5 dir="auto"> Install SSMS (SQL Server Management Studio) 
  
<a href="https://vikaspatel.tech/wp-content/uploads/2023/04/6-1.png">
  <img class="alignnone size-full wp-image-180" src="https://vikaspatel.tech/wp-content/uploads/2023/07/Screenshot-from-2023-07-09-10-51-25.png" alt="" />
</a>
  
<a href="https://vikaspatel.tech/wp-content/uploads/2023/04/6-1.png">
  <img class="alignone size-full wp-image-180" src="https://vikaspatel.tech/wp-content/uploads/2023/07/Screenshot-from-2023-07-09-10-52-00.png" alt="" />
</a>

<a href="https://vikaspatel.tech/wp-content/uploads/2023/04/6-1.png">
  <img class="alignnone size-full wp-image-180" src="https://vikaspatel.tech/wp-content/uploads/2023/07/Screenshot-from-2023-07-09-10-52-32.png" alt="" />
</a>

<a href="https://vikaspatel.tech/wp-content/uploads/2023/04/6-1.png">
  <img class="alignnone size-full wp-image-180" src="https://vikaspatel.tech/wp-content/uploads/2023/07/Screenshot-from-2023-07-09-10-53-53.png" alt="" />
</a> 

<a href="https://vikaspatel.tech/wp-content/uploads/2023/04/6-1.png">
  <img class="alignnone size-full wp-image-180" src="https://vikaspatel.tech/wp-content/uploads/2023/07/Screenshot-from-2023-07-09-10-57-30.png" alt="" />
</a>

</h5>
</li>
 	<li>
<h5 dir="auto">Select "Mixed Mode", this is important because, with Windows Authentication Mode, we will only be able to log in with an online account, whereas, with a mixed mode, we can log in online and locally into the SQL Server.</h5>
</li>
 	<li>
<h5 dir="auto">Default Username: sa</h5>
</li>
 	<li>
<h5 dir="auto">Default Password: Cyberlab123! </h5>
</li>
 	<li>
<h5 dir="auto"> We can connect to our SQL Database</h5>
</li>
 	<li>
<h5 dir="auto">Firstly,<span style="color: #ffff00;"> <a style="color: #ffff00;" href="https://learn.microsoft.com/en-us/sql/relational-databases/security/auditing/write-sql-server-audit-events-to-the-security-log?view=sql-server-ver16" rel="nofollow">Configure</a> </span>the audit object access setting in Windows using audit-portal.</h5>
<ul dir="auto">
 	<li>
<h5 dir="auto">Enable logging for SQL Server to be ported into Windows Event Viewer</h5>
</li>
 	<li>
<h5 dir="auto">Open a command prompt with administrative permissions.</h5>
</li>
 	<li>
<h5 dir="auto">From the Start menu, navigate to Command Prompt, and then select Run as administrator.</h5>
</li>
 	<li>
<h5 dir="auto">If the User Account Control dialogue box opens, select Continue.</h5>
</li>
 	<li>
<h5 dir="auto">Execute the following statement to enable auditing from SQL Server.</h5>
</li>
 	<li>
<h5 dir="auto">Windows Command Prompt</h5>
</li>
 	<li>
<h5 dir="auto">Copy</h5>
</li>
</ul>
<h5 dir="auto"><span style=" color: #ffff00;"><code>audit-pol /set /subcategory: "application generated" /success:enable /failure:enable</code></span><span style="color: #ffff00;"><code></code></span></h5>
<ul dir="auto">
 	<li>
<h5 dir="auto">Close the command prompt window.</h5>
</li>
</ul>
<a href="https://vikaspatel.tech/wp-content/uploads/2023/04/6-1.png">
  <img class="align none size-full wp-image-180" src="https://vikaspatel.tech/wp-content/uploads/2023/07/Screenshot-from-2023-07-09-10-57-30.png" alt="" />
</a> 
    <!--img class="align-center" src="https://camo.githubusercontent.com/639d2f8358a8a9a63c2b5b6a2ed073a5d0dc5866f3c434ea2a29944361e7ff39/68747470733a2f2f692e696d6775722e636f6d2f4c436a4b6a49672e706e67" width="1809" height="333" /-->
 	<li>Now RegEdit and explore:
<p dir="auto"><code>HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\EventLog\Security</code></p>
<img src="https://user-images.githubusercontent.com/109401839/230749756-e9139c85-9cd7-4756-a400-307b02a4c81a.png" /></li>
 	<li>
<h5 dir="auto">Restart SQL Management, Disconnect Connection, Reconnect, and Choose SQL Managements Authentication Method.</h5>
</li>
 	<li>
<h5 dir="auto">Now, Intentionally enter the wrong username and password to do a failed login attempt.

<a href="https://vikaspatel.tech/wp-content/uploads/2023/04/6-1.png">
  <img class="alignnone size-full wp-image-180" src="https://vikaspatel.tech/wp-content/uploads/2023/07/Screenshot-from-2023-07-09-11-13-27.png" alt="" />
</a></h5>
</li>

 <li>
<h5 dir="auto">Test SQL logging to make sure it’s working properly</h5>
</li>
 	<li>
<h5 dir="auto">Enter Event Viewer, Select Application, and View SQL Management Logs Entries:
  
  <a href="https://vikaspatel.tech/wp-content/uploads/2023/04/6-1.png">
  <img class="alignnone size-full wp-image-180" src="https://vikaspatel.tech/wp-content/uploads/2023/07/Screenshot-from-2023-07-09-11-14-15.png" alt="" />
</a></h5>
</li>
 	<li>
<h5 dir="auto">Here we can see the failed login attempt and the reason.</h5>
</li>
</ul>
&nbsp;

&nbsp;
<h2 dir="auto" tabindex="-1">A precursor to Security Operations (Failed Authentication and Log Observation) PT2</h2>
<h5 dir="auto">We will create a VM in the cloud that will be our target of the attack, and we will observe logs and see what they look like. The ultimate goal of this lab is to differentiate between false negatives, false positives, true positives, and true negatives.</h5>
<p dir="auto"><b>Actions and Observations</b></p>

<ul dir="auto">
 	<li>
<h5 dir="auto">We are creating an attack vm the goal is to have a different region so it looks like a threat is attacking our windows-VM.</h5>
</li>
 	<li>
<h5 dir="auto">I have created one different vm in different zone.<a href="https://vikaspatel.tech/wp-content/uploads/2023/04/6-1.png">
  <img class="alignnone size-full wp-image-180" src="https://vikaspatel.tech/wp-content/uploads/2023/07/Screenshot-from-2023-07-09-11-23-25.png" alt="" />
</a></h5>
</li>
 	<li>
<h5 dir="auto">We will now generate some failed RDP (remote desktop protocol) logs against the windows-vm from the attacker vm.
  <a href="https://vikaspatel.tech/wp-content/uploads/2023/04/6-1.png">
  <img class="alignnone size-full wp-image-180" src="https://vikaspatel.tech/wp-content/uploads/2023/07/Screenshot-from-2023-07-09-11-27-49.png" alt="" />
</a></h5>
</li>
 	<li>
<h5 dir="auto" >We will attempt this 5 times with the wrong username and password.</h5>
</li>
 	<li>
<h5 dir="auto">We then go to event viewer and see all the failed login attempts <a href="https://vikaspatel.tech/wp-content/uploads/2023/04/6-1.png">
  <img class="alignnone size-full wp-image-180" src="https://vikaspatel.tech/wp-content/uploads/2023/07/Screenshot-from-2023-07-09-11-31-16.png" alt="" />
</a></h5>
</li>
 	<li>
<h5 dir="auto">After this, we will install SSMS within attack-VM and generate some failed MS SQL Auth logs against windows-VM.</h5>
</li>
 	<li>
<h5 dir="auto">Enter the wrong password 5 times
<a href="https://vikaspatel.tech/wp-content/uploads/2023/04/6-1.png">
  <img class="alignnone size-full wp-image-180" src="https://vikaspatel.tech/wp-content/uploads/2023/07/Screenshot-from-2023-07-09-11-42-18.png" alt="" />
</a>

  <a href="https://vikaspatel.tech/wp-content/uploads/2023/04/6-1.png">
  <img class="alignnone size-full wp-image-180" src="https://vikaspatel.tech/wp-content/uploads/2023/07/Screenshot-from-2023-07-09-11-46-34.png" alt="" />
</a>
</h5>
</li>
 	<li>
<h5 dir="auto">It's important to also take note of EventIDs, messaging, source IP Addresses, etc...</h5>
</li>
</ul>
