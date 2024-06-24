# Lab Report: Architecture
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Abigail Garrido  
**GitHub Handle:** ag1454  
**Repository:** https://github.com/ag1454/cis411_lab2_arch  
**Collaborators:** n/a (#madscientistlife...I did have my dad (Randy) help me with this, though)
___

# Step 1: Confirm Lab Setup
- [**X**] I have forked the repository and created my lab report
- [**X**] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [**X**] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is a system that allows for users to see all volunteering opportunities within a certain area and register for them in one simple application. The app also tracks user statistics for organizations.

## Step 2.1 Representative Use Cases  

| **Use Case #1** | |
|---|---|
| **Title** | Volunteer Submits Application |
| **Description** | This use case describes how a volunteer applies for a volunteering opportunity. |
| **Steps** | <ol><li>Volunteer finds a volunteer opportunity of interest.</li><li>Volunteer fills out the application form for the volunteer opportunity and submits it once complete.</li></ol> |
| **Primary Actor** | Volunteer |
| **Preconditions** | <ol><li>Volunteer has a Serve Central account and is logged in.</li></ol> |
| **Postconditions** | <ol><li>Service agency receives application from volunteer for review.</li></ol> |

| **Use Case #2** | |
|---|---|
| **Title** | Service agency hosts an event on Serve Central |
| **Description** | This use case describes how a service agency hosts on event on Serve Central. |
| **Steps** | <ol><li>Service agency inputs volunteering event information.</li><li>Service agency uploads event information to Serve Central</li></ol> |
| **Primary Actor** | Service Agency |
| **Preconditions** | <ol><li>Serve Central has a special account option for service agencies.</li><li>Service agency has a Serve Central account and is logged in.</li></ol> |
| **Postconditions** | <ol><li>The service agency's event is able to be viewed by volunteers looking for volunteering opportunities.</li></ol> |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| model receives location info | view shows volunteering opportunities near the location info | user inputs location into map |
| model is notified that the user has switched displays | view displays the volunteering events list | user toggles to events list |
| model is notified that a user has logged into the system | view displays what a logged in user would see | user logs into Serve Central |
| model receives the completed volunteering application and the type of volunteering signed up for | view updates to notify the user that their application has been submitted and adds the type of volunteering to their types of volunteering hours statistics | user submits volunteering application |

## Step 2.3 Diagram a Use Case in Architectural Terms
![UML](../assets/UML.PNG)

The actor (Volunteer) performs a volunteering application submission action (Controller). The service agency and the Serve Central user statistics tracking will receive the application and type of volunteering that the volunteer applied for, respectively (Model). Volunteer will be notified that their application went through and their statistics will change (View).

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
Proposed architectural change: broker architecture. Both of the proposed changes to the architecture involve either third-parties accessing Serve Center or Serve Center accessing third-parties. Advantages include transparent service distribution for clients and support of dynamic CRUD. A disadvantage is potential complexity for smaller projects.

## Step 3.2 Revised Architecture Diagram
![Broker Diagram 1](../assets/Broker1.PNG)

A client on Serve Central will see volunteering opportunities from third-parties. If they interact with the volunteering opportunities from third-parties, they will be redirected to that third-party. The ability to retrive data from Serve Central will be given to the third-parties.

![Broker Diagram 2](../assets/Broker2.PNG)

A client on a third-party service agency that wants to register for a volunteering opportunity will be redirected to a Serve Central server in order to fill out the registration form.

# Step 4: Scaling an Architecture
The architectural change I propose is the microservice architecture. Based on the following future needs, the system is becoming both larger and more complex; it needs to handle more volunteer opportunity submissions, store more data, and allow ways for the queries of authorized parties to traverse that data. The microservice architecture allows for ease of scalability and understanding, smaller and faster deployments, and improved fault isolation. However, debugging can be harder, global testing is difficult, and more services means needing more resources. ([Source](https://cloudacademy.com/blog/microservices-architecture-challenge-advantage-drawback/))

I also propose the peer-to-peer (P2P) architecture, specifically for the future need of consuming bursts of over 10k new volunteering opportunities per hour with a latency of 15 seconds between the submission and availability in the registration service. The main reason I propose P2P is that if a large group of peers join the network at one time, the network can easily handle the increased load. However, with the need of a mobile experience, the P2P architecture may pose problems, as the mobile devices aren't always on, so it's difficult for users to contribute to the network without draining battery and using up mobile data. ([Source](https://student.cs.uwaterloo.ca/~cs446/1171/Arch_Design_Activity/Peer2Peer.pdf))

# Extra Credit
My only suggested change is for step 2.1: when reading through the elements we must include, I found the Description / Steps element confusing. I interpreted it as needing one or the other, and then wondered if it mean the description and steps were meant to go together. What I eventually did was make separate sections in the use case tables so that its appearance would align more closely to the ones in Dennis, Wixom and Roth (2014). I would rewrite Description / Steps as two separate elements so that it's better understood that they're both needed.