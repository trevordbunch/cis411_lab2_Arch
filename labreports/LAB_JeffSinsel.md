# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Jeff Sinsel  
**GitHub Handle:** JeffSinsel  
**Repository:** [My Forked Repository ](https://github.com/JeffSinsel/cis411_lab2_arch)
___

# Step 1: Confirm Lab Setup
- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is an application that helps volunteers find events to help with.

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title |  Event Registration - Event Organizer |
| Description | **As a potential ServeCentral event organizer, I want to register an event, so that I can reach volunteers in my area.** |
| Steps |  1. An individual navigates to the ServeCentral webpage, and clicks `Organize Event`.  <br> 2. The individual completes an initial event registration form  (Event name, description,address, time, number of volunteers needed).  <br> 3. The registration form will validate the following conditions: address exists, time is in the future, and terms of service is checked.  <br> 4. After confirmation that the event is created, a message pops up on the site to let the user know, confirming the event. |
| Primary Actor | Event Organizer |
| Preconditions | 1. The User has logged in. <br> 2. has a valid Event Organizer account.  |
| Postconditions | 1. The user receives email confirmation their event has been published. |

| Use Case #2 | |
|---|---|
| Title |  Register for Event - Volunteer |
| Description | **As a potential ServeCentral volunteer, I want to register for an event, so that I can volunteer at said event.** |
| Steps |  1. An individual navigates to the ServeCentral webpage, finds an event they would like to volunteer at, and clicks `Register for Event`.  <br> 2. The individual picks the role and time they would like to volunteer.  <br> 3. The registration form will validate the following conditions: time slot and role are not full, time slot is not overlapping prior commits, and terms of service is checked.  <br> 4. After confirmation that the individual is registered for the event, a message pops up on the site to let the user know, confirming the volunteering. |
| Primary Actor | Event Organizer |
| Preconditions | 1. The User has logged in. <br> 2. has a valid Event Organizer account.  |
| Postconditions | 1. The user receives email confirmation their time slot has been reserved as well as directions to the event. |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Past Events | Event History List | loadPastEventsByUser |
| Upcoming Events | Event List | getCurrentEventsByDate |
| Event Organizers | Profile List | viewProfiles |
| Upcoming Events by distance | Map | sortAndDisplayEventsByDistance |

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