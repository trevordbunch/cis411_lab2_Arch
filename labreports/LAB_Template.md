# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Nathan Bowman  
**GitHub Handle:** bowman3239 
**Repository:**   https://github.com/bowman3239/cis411_lab2_arch.git
**Collaborators:** 
___

# Step 1: Confirm Lab Setup
- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is a responsive web design that solves the problem of finding new and consistent leads in regards to volunteering research. Serve Central will be a user friendly application that allows the suer to have their own account, search for local events, and sign up for events they desire to help with.

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title | Signing up for an event |
| Description / Steps | Description: The volunteer selects a specific event they would like to sign up for.
Setps: 1. The volunteer inserts their zip code into a search bar. 2. The system provides available volunteer events within a 25 mile radius of the given zip code. 3. The volunteer selects a provided volunteer event. 4. The system displays more detailed information about the selected event, such as: date, time, location, job responsibilities, etc. 5. The voluteer selects "Sign up for event". 6. The system pulls the volunteers' information and sends it to the manager of that event. 7. Manager is notified.  |
| Primary Actor | Volunteer |
| Preconditions | 1. The volunteer is authenticated by logging into his/her account. 2. The availability of volunteer events is online.|
| Postconditions | 1. Volunteers who have signed up for events is stored in the system. 2. The manager of that event is notified of the new volunteer. |

| Use Case #2 | |
|---|---|
| Title | Creating an Event|
| Description / Steps | Description: The service agencies can create an event for volunteers to sign up for.
Steps: 1. The system asks basic questions about the project at hand, such as: the mission, time, date, location, jobs required, etc. 2. The service agency fills out the information about their volunteer event. 3. The system sends the information to the application to be listed as a possible event for volunteers to sign up for and attend. |
| Primary Actor | Service Agencies |
| Preconditions | 1. The service agency must complete a "background check" to make sure they are a real organization. 2. The prompted information is completely filled out by the service agency.|
| Postconditions | 1. The event is posted to the application page.|

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Events | Current Events | Add Event |
| Volunteers | Current Volunteers | Add Volunteer  |
| Organizations | Organizations | Add Organization |
| Locations | Current Locations | Add Location |

## Step 2.3 Diagram a Use Case in Architectural Terms
![alt text](https://viewer.diagrams.net/?tags=%7B%7D&highlight=0000ff&edit=_blank&layers=1&nav=1#G1KNIDqQDh5SRiP6THC06sZgTn1IUAuNCz)

Description: The view, in this case the current events, is the only thing that the volunteer can see. The view is altered by the controller, "add event". This controller has a two way relationship the model of "events" which would be connected to the database.

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
INSERT Architectural change proposal here, and how it meets the two new requirements.  Explain both the benefits and draw backs of your proposal.

## Step 3.2 Revised Architecture Diagram
INSERT IMAGE HERE with a Description.

# Step 4: Scaling an Architecture
INSERT Architectural change proposal here, and how it meets the four new requirements.  Explain both the benefits and draw backs of your proposal.  If the changes are significant, then you need to explain why the changes are necessary versus a nice-to-have enhancement.

# Extra Credit
If you opt to do extra credit, then include it here.