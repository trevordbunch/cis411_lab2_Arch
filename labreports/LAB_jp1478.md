# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2023  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Joshua Phillips  
**GitHub Handle:** jp1478  
**Repository:** https://github.com/jp1478/cis411_lab2_arch  
**Collaborators:** Aidan Hubley, Nason Allen
___

# Step 1: Confirm Lab Setup
- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is an app that allows users to find and sign up for
volunteering opportunities in their area and track their history of volunteering. 

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title | Find an Event - Volunteer |
| Description / Steps | 1. A volunteer logs in to the app. <br> 2. The volunteer navigates to the events page to see events sorted by distance from home. <br> 3. The volunteer clicks on an event they are interested in, taking them to that event's page. <br> 4. If the volunteer is looking for more detailed location data, they can navigate to the map page and select an event from there. |
| Primary Actor | Volunteer |
| Preconditions | 1. User must be registered as a volunteer. <br> 2. User must provide their location. <br> 3. Service Agencies must have created events. |
| Postconditions | The volunteer has reached the page for a specific event. |

| Use Case #2 | |
|---|---|
| Title | Create an Event - Service Agency |
| Description / Steps | 1. A service agency logs into the app. <br> 2. They navigate to the events page. <br> 3. They click on the "New Event" button. <br> 4. They complete an event form (Name, Location, Description, Capacity)|
| Primary Actor | Service Agency |
| Preconditions | User must be registered as a service agency. |
| Postconditions | An event is listed and available for registration. |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Events | Profile | RegisterUser - creates a user |
| Users | Map | CreateEvent - creates a new event |
| Volunteers | Events | DisplayMap - displays the map page |
| Service Agencies | New Event | SignUp - signs a user up for an event |

## Step 2.3 Diagram a Use Case in Architectural Terms
![MVC Use Case](assets/MVC%20Diagram.jpg)

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
INSERT Architectural change proposal here, and how it meets the two new requirements.  Explain both the benefits and draw backs of your proposal.

## Step 3.2 Revised Architecture Diagram
INSERT IMAGE HERE with a Description.

# Step 4: Scaling an Architecture
INSERT Architectural change proposal here, and how it meets the four new requirements.  Explain both the benefits and draw backs of your proposal.  If the changes are significant, then you need to explain why the changes are necessary versus a nice-to-have enhancement.

# Extra Credit
If you opt to do extra credit, then include it here.