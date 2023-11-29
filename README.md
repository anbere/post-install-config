<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>Post-Install Configuration Objectives</h2>

- Creating/Configuring
  - Roles
  - Departments
  - Teams
  - Agents
  - Users
  - SLA/Help Topics

<h2>Configuration Steps</h2>

<p>
   ![image](https://github.com/anbere/post-install-config/assets/90169033/1e939f18-c037-47a0-89f7-f54c6b058639)
</p>
<p>
  Congratulations and welcome to the landing page of osTicket, which we configured from scratch, following the previous tutorial. Now we will do some system administration and begin the post installation setup. We   will first get practice configuring new roles within osTicket.

  <h2>Roles</h2>

  Click on Admin Panel -> Agents -> Roles. 

  We will create a 'Supreme Admin' given all permissions. Click on `Add New Role` then enter the name of the role. In our case it will be 'Supreme Admin'.

  ![image](https://github.com/anbere/post-install-config/assets/90169033/05708856-952f-4109-8bd4-44620abf221a)

  Navigate to the permissions tab and check each option. Keep in mind, roles are used to determine a user's permissions, not all users should have unlimited access. 

  Once they are all checked, click `Add Role`.

  ![image](https://github.com/anbere/post-install-config/assets/90169033/df1e6423-5a32-473e-9775-545255393e62)

  We have succesfully created a role titled, 'Supreme Admin' which we can assign to different users, if we would like.

  ![image](https://github.com/anbere/post-install-config/assets/90169033/ddf39705-2f64-4e50-973c-88c454aea2d5)

</p>
<br />

<p>

  <h2>Departments</h2>

  Now we will practice creating a new department. Each Agent is assigned to one or multiple departments depending on their assigned role. We will be creating the 'System Administrators' 
  department for the Supreme Admin to be assigned to. Navigate to the department tab by going to Agents -> Departments, within the Admin Panel.

  By default, there is a 'Maintenance' and 'Support' department. We will create a new department by clicking on `Add New Department`.

  ![image](https://github.com/anbere/post-install-config/assets/90169033/c4d5cc38-3a14-433b-9d91-e5ceebbe1b4f)

  We will keep things simple and create the department with default settings. Only change the Name section to 'System Administrators, then click `Create Department` at the bottom of the page.

  ![image](https://github.com/anbere/post-install-config/assets/90169033/2d4eb1a9-2084-48d5-94b2-00743d0d48b8)

  We will designate Agents to this department later, for now lets move onto Teams. 

</p>
<p>

  <h2>Teams</h2>

  Teams allow you to pull Agents from different Departments and oprganize them to handle a specific issue or user. For example, you could create a team filled with Agents that are designated 
  to different departments.

  To create a Team we will navigate to Agents -> Teams from the Admin Panel. By default there is a Level I Support Team. Click on `Add New Team`. For the name, we will use 'Level II Support'.
  We can add ourselves to the team if we like by navigating to the Members tab, on the `Select Agent` dropdown we choose our name and click Add. Then finally we can click on `Create Team`.

  ![image](https://github.com/anbere/post-install-config/assets/90169033/4fac7c39-d444-4d42-a5d8-1243cbc6946b)

  We now have a team we created which we can add different Agents to, however at the moment we dont have other Agents registered. Before moving to the next section we will allow anyone to create 
  tickets. Navigate to Admin Panel -> Settings -> Users -> Settings.

  On the option for 'Registration Required', make sure the box is unchecked. 

  ![image](https://github.com/anbere/post-install-config/assets/90169033/5c10fa58-8caa-482b-889b-8f6a3ebbe853)

  Now to create new Agents!

</p>
<br />

<p>
  <h2>Agents</h2>

  Agents are given access to the help desk with the intent to respond and resolve tickets. When adding an Agent to the help desk, they will need to be assigned a Primary Department and given a Primary Role.

  To create new Agent accounts, we will navigate to the Agents tab from the Admin Panel. Click on `Add New Agent`. We will use the name 'Jane Doe' and a dummy email jane.doe@osticket.com. For the scope of this project we wont need access to the emails related to the user. Click on Set Password
  and make sure to uncheck `Send the agent a password reset email`, as well as the `Require password change at next login` boxes.

  ![image](https://github.com/anbere/post-install-config/assets/90169033/c4f87ef3-50d7-45f1-976c-7c877b18b2a6)

  Before clicking on `Create`, navigate to the 'Access' tab and for the Primary Department we will assign the Agent to the System Administrators department we created. We will also give them the role of Supreme Admin which we also created. In the Teams tab we can add them to the Level II Support
  Team that we created as well. Now we can finalize the Agent by clicking on `Create`. Redo the same process to create another Agent with a name of your choice, I will be using John Doe. In the Access tab, set their primary department as Support and their Role as View only. We now have two agents
  registered in osTicket!

</p>
<p>

  <h2>Users</h2>

  Users can now create an account and log-in to create a ticket or check a ticket's status. The User Directory, located on the Agent Panel, allows Agents to search tickets by user as well as create Organizations
  to associate the user to. We will create two Users so we can get an idea of what the ticket submitting process looks like from their end.

  From the Agent Panel, navigate to the Users tab and click on `Add User`.

  ![image](https://github.com/anbere/post-install-config/assets/90169033/5425af40-b4bc-44d7-8369-a1a1aa427236)

  We will create a user with the name Karen Smith, and a dummy email to go along with the account. Click on `Add User` and then redo the process and create one more user with the name Ken Tanaka.

  ![image](https://github.com/anbere/post-install-config/assets/90169033/7e1b5b23-eeb1-4be9-a7c4-658931f7d87d)

  In the next Tutorial we will get practice creating tickets, for now we will move to the next section.

</p>
<br />

<p>

  <h2>SLA Plans</h2>

  SLA Plans or Service Level Agreements provide a length of time in which the help desk Administrator expects tickets to be closed. We will create SLA Plans by navigating to Admin Panel -> Manage -> SLA Plans.

  Click `Add New SLA Plan`. The first plan we create will be named 'SEV-A' which will be our highest priority SLA. The 1 hour grace period and 24/7 schedule means that the ticket needs to be resolved within 
  an hour, no matter when it gets submitted.

  ![image](https://github.com/anbere/post-install-config/assets/90169033/7cd96b0c-de9c-43a0-96be-b5e2f40d21a6)

  Our second SLA will be named 'SEV-B' and it will have a 4 hour grace period and also a 24/7 schedule. Tickets with this SLA designation will need to be resolved within 4 hours no matter what time or day 
  they are submitted.

  ![image](https://github.com/anbere/post-install-config/assets/90169033/669754ed-f653-4cfb-a86e-34c6943637ab)

  The third SLA will be named 'SEV-C' and it will have an 8 hour grace period and a Schedule of 'Monday - Friday 8am - 5pm'. This means tickets with this SLA will need to be resolved within 8 hours, only 
  within business hours.

  ![image](https://github.com/anbere/post-install-config/assets/90169033/454fb85f-e625-484d-9673-ea93fae7793d)

  These will have more context when we create tickets within the next Tutorial.
  
</p>
<br />

<p>
  <h2>Help Topics</h2>

  Help Topics will help streamline your end-user's help desk experience to ensure proper assignment and prompt response to the ticket. Help Topics will determine what department the ticket is routed to which
  will determine which Agents have access to the ticket. To configure Help Topics, navigate to Admin Panel -> Manage -> Help Topics. Once there, click on `Add New Help Topic`.

  We will create the topics with the following names and default settings:

  - Business Critical Outage
  - Personal Computer Issues
  - Equipment Reset
  - Password Reset

  ![image](https://github.com/anbere/post-install-config/assets/90169033/ac807c42-4308-42b6-98ed-fe2047f68ea0)

  
</p>












