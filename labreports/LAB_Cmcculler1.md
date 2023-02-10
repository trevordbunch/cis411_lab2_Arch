# Lab Report: Architecture
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Corum McCuller  
**GitHub Handle:** Cmcculler1  
**Repository:** https://github.com/Cmcculler1/cis411_lab2_arch.git  
**Collaborators:** richard-pokrivka kfirestone25
___

# Step 1: Confirm Lab Setup
- [ ] I have forked the repository and created my lab report
- [ ] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [ ] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
The % of United States volunteers from the years of 2002-2014 has decreased a significant amount. A reason behind that is the difficult process to actually become a volunteer, Serve Central is an application to make the volunteering process much easier and quicker for people interested in volunteering. 
## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title:     |Finding and Completing Registration for Volunteer Oppurtunities |
| Description / Steps:|Users must create an account within the application. Users can navigate to the "map" function, and find an event through that interface. Or users can use the "events" function to find a service oppurtunity. |
| Primary Actor: |Volunteers|
| Preconditions |Users must comply with a mandatory background check, that may have to be updated due to legal circumstances. The service event application is within the Serve Central application. A new application must be submitted for each Service event. |
| Postconditions |User gets notified if he/she was accepted for declined for the service opputunity that was applied for. Application is submitted to the agency  |

| Use Case #2 | |
|---|---|
| Title | Obtaining Applications for Volunteer Work  |
| Description / Steps |1.Each orginization should create their own authenticated account. 2. These accounts can access applications and post details about service oppurtunities. 3. Orginizations should make sure to include additional information for the service opputunities posted.  |
| Primary Actor |Service Agencies |
| Preconditions |The service agency has an account that can access all applications submitted. Orginaztions receive confirmation of background checks to their account.   |
| Postconditions |Agencies must send out an acceptance or decline letter. If application is accepted, agency sends out an email to the volunteers providing an iteniary for the event and any other neccesary details.  |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Agencies  | List of all agencies  | "Agencies" section of app  |
| Volunteers | Submitted applications | "Applications" tab button |
| Service locations  | Map interface   | Button to choose location  |
|Sercive types  | Alphabetical list of categories | Search bar  |

## Step 2.3 Diagram a Use Case in Architectural Terms
![Use Case](https://docs.google.com/drawings/d/e/2PACX-1vS_WRr5E88Wdq050I2xlC925IKLejVcICb8TdiZT41l1be7n0NFXst5dDB9Btnc7t-aKzj_oWwq3yCM/pub?w=960&h=720)
In this diagram the volunteer is viewing the map interface and uses the controller "button to choose location" to pick a location which uses the data from the "service locations" model to return back the information to the Volunteer on the map interface.

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
For the neccesary changes being made to Serve Central, the architecture pattern we are using "Client-server". This pattern was chosen because of the amount of collaboration that is now being used with Serve central. Using Client-Server allows people from all orginizations to access the database and input or retrieve information at any time. A potential issue is the risk of your server crashing and not having any back-up servers.

## Step 3.2 Revised Architecture Diagram
![Use Case](https://docs.google.com/drawings/d/e/2PACX-1vRLjEMrb5hf0rccQ5RA3-IkzW6Tmd7duVCZZB7EnFGBfxe0wSRwhsbgHpbDN1xSisa3nwwyLyVkFGJ7/pub?w=960&h=720)

For the Client Server model, third party organizations, Serve Central employees and Service agencies can all access the cloud that the databases are stored on and that is connected to the main server that Serve Central is using.

# Step 4: Scaling an Architecture
For the four new requirements along with creating a mobile application for Serve Central, the architectural pattern that will be used is Blackboard. The number one benefit of this pattern is the massive amount of data that it has retention for. This pattern allows a large area for new data to be added. Based off research, the management of data in this pattern is very flexible. There are some downsides to using Blackboard. It is fairly more expensive than other styles and is very complex so it will require time in training beforeheand.

