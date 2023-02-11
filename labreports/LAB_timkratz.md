# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2023  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Tim Kratz  
**GitHub Handle:** timkratz  
**Repository:** https://github.com/timkratz/cis411_lab2_arch.git  
**Collaborators:**  None
___

# Step 1: Confirm Lab Setup
- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is a mobile application that allows users to find events that are looking for volunteer opportunitites. On the app you are able to see what the event is, where the event is located, and what kind of volunteers are needed.

## Step 2.1 Representative Use Cases  

| Use Case #1 |Volunteer|
|---|---|
| Title | Signing up to volunteer |
| Description / Steps |<ol> <li> User will login to their account </li><li> User searches through desired events based on the time, event type, and location </li><li> User selects an event and fills out required information </li><li> User will confirm their registration </li><li> User is given registration confirmation </li><li> User is directed back to original search page  |
| Primary Actor |Volunteer |
| Preconditions |<ol> <li> User has created an account </li><li> Serve Central is running and available to use |
| Postconditions |<ol> <li> User is notified of completed signup </li><li> User is notified with instructions about the event and any changes that may occur  |

| Use Case #2 | |
|---|---|
| Title |Creating Volunteering Event |
| Description / Steps |<ol> <li> Orgainization will login to their account </li><li> Organization selects new event registration </li><li> Organization fills out information about event </li><li> Organizations confirms registering their event </li><li> Organization is given confirmation of registered event </li><li> Organization is directed back to original page |
| Primary Actor |Organization |
| Preconditions |<ol> <li> Organization has created an organization account </li><li> Serve Central is running and available to use  |
| Postconditions |<ol> <li> Organization is notified of completed event registration </li><li> Event is displayed so that volnteers can see it |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
|Service Events  | Available Events  |EventController  |
|User Registration |User Account Registration  |UserRegistrationController  |
|Event Location  |Event Information  |EventLocationController  |
|Event  |Event Registration  |EventRegistrationController  |

## Step 2.3 Diagram a Use Case in Architectural Terms
INSERT IMAGE HERE with a Description.

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
INSERT Architectural change proposal here, and how it meets the two new requirements.  Explain both the benefits and draw backs of your proposal.

## Step 3.2 Revised Architecture Diagram
INSERT IMAGE HERE with a Description.

# Step 4: Scaling an Architecture
INSERT Architectural change proposal here, and how it meets the four new requirements.  Explain both the benefits and draw backs of your proposal.  If the changes are significant, then you need to explain why the changes are necessary versus a nice-to-have enhancement.

# Extra Credit
If you opt to do extra credit, then include it here.