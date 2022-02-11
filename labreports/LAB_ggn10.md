# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Garrett Nissley  
**GitHub Handle:** ggn10  
**Repository:** [ggn10/cis411  ](https://github.com/ggn10/cis411_lab2_arch) 
**Collaborators:** N/A
___

# Step 1: Confirm Lab Setup
- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.

# Step 2: Analyze the Proposal
Serve Central offers a software solution to the problem of the decline of volunteer service in the United States. It allows aspiring volunteers to have all of the volunteer registration and event information in one simple application.

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title | Register for Volunteer Event |
| Description | This use case describes how a user would register for a volunteer event. |
| Primary Actor | Volunteer User |
| Preconditions |  1. User is authenticated as normal user 2. Registration application is available and online |
| Steps | 1. User opens the application 2. User selects 'Register for Event' button 3. User verifies their personal information 4. System stores their user and event information 5. System notifies the user their registration status |
| Postconditions | 1. New registration is created and stored in database 2. Volunteer event capacity updated |

| Use Case #2 | |
|---|---|
| Title | Create Volunteer Event |
| Description | This use case describes how a event manager would create a volunteer event. |
| Primary Actor | Event Manager User |
| Preconditions | 1. User is authenticated as Event Manager user 2. Event creation application is available and online |
| Steps | 1. User opens the application 2. User selects 'Create Volunteer Event' Button 3. User provides all required information to create volunteer event. 3. System stores event information 4. System notifies user the status of their created event |
| Postconditions | 1. New volunteer event is created and stored in database 2. New volunteer event is made available for registration  |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Event Registration Data from Firebase | Event Information React Page | Registration.js |
| Event Data from Firebase | Create Event React Page | eventCreation.js  |
| User Data from Firebase | User Sign-Up React Page | createUser.js |
| User Data from Firebase | User login React Page | getUser.js |

## Step 2.3 Diagram a Use Case in Architectural Terms
![Use Case Diagram ](/assets/UseCaseDiagram.png) 

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
I propose that Serve Central continue supporting their already developed MVC software architecture and also develop specifics Microservices. The benefit of adding a microservice architecture to Serve Central is that it solves their scaling issue. The seperate portions of Serve Central that are in high demand will be able to be developed and scaled seperately based on their need. Specifically, the registration service of Serve Central will be a microservice available for churches to embed into their website. With the sustaining of the MVC architecture, Serve Central will allow third-party services to input and retrieve data from Firebase as usual.

## Step 3.2 Revised Architecture Diagram
![Revised Architecture Diagram](/assets/RevisedArchitectureDiagram.png)

# Step 4: Scaling an Architecture
INSERT Architectural change proposal here, and how it meets the four new requirements.  Explain both the benefits and draw backs of your proposal.  If the changes are significant, then you need to explain why the changes are necessary versus a nice-to-have enhancement.