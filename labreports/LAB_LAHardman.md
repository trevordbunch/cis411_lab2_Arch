# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** [Luke Hardman](https://github.com/LAHardman)  
**GitHub Handle:** [LAHardman](https://github.com/LAHardman))  
**Repository:** https://github.com/LAHardman/cis411_lab2_arch  
**Collaborators:** 
___

# Step 1: Confirm Lab Setup
- [X] I have forked the repository and created my lab report
- [X] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [X] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is a mobile and web based application solution to connect volunteers to volunteer opportunities. It will make use of Firebase and React Native to construct an application in which a user can create an account, find & register for events, and track their volunteering history.

## Step 2.1 Representative Use Cases  

| Use Case #1 | Volunteers |
|---|---|
| Title | Event Search - Volunteer |
| Description | As a ServeCentral user, I want to search through events by type, so that I can better find a volunteer opportunity for me. |
| Steps | 1. An individual navigates to the ServeCentral webpage, and clicks `Login`.</br > 2. The individual provides their login credentials. <br> 2. The authentication server with validate their credentials. <br> 3. The individual is taken to their ServeCentral page, and clicks `Events`. <br> 4. The individual enters keywords into the search bar. 
| Primary Actor | Volunteer |
| Preconditions | 1. The individual has an account with ServeCentral. |
| Postconditions | 1. The individual receives events matching their keywords near their area. <br> 2. If there are no events matching their search in their area, the page informs the individual of that. |

| Use Case #2 | Service Agency |
|---|---|
| Title | Event Creation and Management - Service Agency |
| Description | As an organization, I want to create and manage events on the ServeCentral platform, so that I can reach and engage with potential volunteers in my community.  |
| Steps | 1. The organization logs in to their ServeCentral account. <br> 2. The organization navigates to the event creation page and inputs the required information (event name, date, time, location, description, number of volunteers needed, etc.). <br> 3. The organization can preview the event information before submitting it for approval. <br> 4. The event information is reviewed and approved by ServeCentral staff. <br> 5. The event is added to the ServeCentral platform and becomes visible to potential volunteers. <br> 6. The organization can view the list of volunteer sign-ups for their event and manage volunteer information (e.g. t-shirt size, special requirements, etc.) <br> 7. The organization can communicate with volunteers through the ServeCentral platform for any updates or information related to the event. <br> 8. After the event has taken place, the organization can provide feedback and rate the volunteers, and the volunteers can rate their experience at the event.|
| Primary Actor | Service Agency |
| Preconditions | The organization must have a registered and activated ServeCentral account. |
| Postconditions | 1. The organization has successfully created and managed an event on the ServeCentral platform. <br> 2. The event information is saved in the organization's account for tracking and reference. |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|-------|-------|-----------|
| User | User Registration | User Registration Controller |
| Event | Event Search and Sign-Up | Event Search and Sign-Up Controller |
| Organization | Event Creation and Management | Event Creation and Management Controller |
| Activity | Volunteer Activity Tracking | Volunteer Activity Tracking Controller |

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