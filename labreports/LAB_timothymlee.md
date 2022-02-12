# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Timothy Lee  
**GitHub Handle:** timothymlee  
**Repository:** [Your Forked Repository](https://github.com/timothymlee/cis411_lab2_arch)  
**Collaborators:** 
___

# Step 1: Confirm Lab Setup
- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is a mobile and web app that offer a simple solution for being unable to find volunteering events. It uses user location to find local events, display relevant information, and allow for the user to easily sign-up, all from one place.

## Step 2.1 Representative Use Cases  

| Use Case #1 | Volunteer Event Sign-up |
|---|---|
| Primary Actor | Volunteer |
| Description | A volunteer signs-up for a listed service event |
| Preconditions | <ul><li>The user is authenticated by loggin into their account</li><li>The user is sharing location data</li></ul> |
| Steps | <ol><li>User opens list of nearby service events</li><li>User select desired event</li><li>The system provides details about the service agency and the event</li><li>The user selects to sign-up for the event</li><li>The system pulls the user's stored information from the account and prompts for number of participants to sign-up</li><li>The system adds the event to the user's account and updates the event</li></ol> |
| Postconditions | <ul><li>The event is added to the user's account</li><li>The number of participants is updated for the event</li></ul>|

<br>

| Use Case #2 | Service Agency Event Creation |
|---|---|
| Primary Actor | Service Agency |
| Description | A service agency creates a service event|
| Preconditions | <ul><li>The service agency is a registered agency</li></ul> |
| Steps | <ol><li>The user selects to create a new event</li><li>The system prompts the user for a description and information about the date, cause, maximum number of participants, and location.</li><li>The system pulls information about the service agency to add to the event description</li><li>The user enters and confirms data.</li><li>The system adds the event to the database</li></ol> |
| Postconditions | <ul><li>The event is added to the database</li></ul> |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| User's Events | List of events user signed up with summaries of the events | Selecting event will bring up all details for the event |
| Agency's Events | Lit of events the agency is hosting with event detail summaries | Selecting events will allow for more details about the details and allow for editing of details |
| Available Events | List of nearby service events | Changes list of options depending on user location |
| Event Creation | Form with different fields to fill out | Updates database of events and outputs confirmation |

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