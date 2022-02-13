# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Your Name  
**GitHub Handle:** Your GitHub Handle  
**Repository:** Your Forked Repository  
**Collaborators:** 
___

# Step 1: Confirm Lab Setup
- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is a system hoping to solve the problem of decreasing number of volunteers in the U.S. Serve Central hopes to acheive this by making the process of volunteering easier for volunteers by creating a system that requires users only to apply once before being track and apply to all volunteering oppportunities.

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title | sign up for an event |
| Description / Steps |  1.0 Register for a volunteering opportunity <br> 1.The volunteer specifies a location near which they can work <br> 2.The system lists all the different events and also provides a map <br> 3. The volunteer picks an event <br> 4. The system sends the service agency a notification that the user wishes to volunteer and sends the necessary registration information <br> 4. The volunteer receives a confirmation of the registration for the event |
| Primary Actor | Volunteer |
| Preconditions | 1. The user has already created an account <br> 2. The user is signed in|
| Postconditions | 1. The volunteers registration information is stored by the service agency <br> 2. The volunteer receives a reminder when the time of the event approaches |

| Use Case #2 | |
|---|---|
| Title | Publish an event |
| Description / Steps | 1.0 Publish an event <br> 1. The service agency specifies the location, the category and the timeframe of the volunteering opportunity <br> 2. The service agency specifies the information required from volunteers <br> 3. The system sends confirmation that the event has been published |
| Primary Actor | Service Agency |
| Preconditions | 1. The Service Agency has created an account |
| Postconditions | 1. The volunteers near the event are notified of the new event |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| User Logins | Sign In Page | Login Controller |
| Users | Profile Page | Retreive User Information Controller |
| Events | Event list Page | Sign Up Controller |
| service Agencies| Add new service Agency page | Add new Service Agency Controller |

## Step 2.3 Diagram a Use Case in Architectural Terms
* Diagram of volunteer signing up for an event 
![Use Case Diagram](../assets/useCase1.svg)

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
INSERT Architectural change proposal here, and how it meets the two new requirements.  Explain both the benefits and draw backs of your proposal.

## Step 3.2 Revised Architecture Diagram
INSERT IMAGE HERE with a Description.

# Step 4: Scaling an Architecture
INSERT Architectural change proposal here, and how it meets the four new requirements.  Explain both the benefits and draw backs of your proposal.  If the changes are significant, then you need to explain why the changes are necessary versus a nice-to-have enhancement.

# Extra Credit
If you opt to do extra credit, then include it here.