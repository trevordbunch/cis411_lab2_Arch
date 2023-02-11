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
Serve Central is a mobile application designed to make it easier for users to find nearby volunteer opportunities. It can locate charities and other volunteer events, as well as allow for RSVPs and track total hours across events.

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title | Volunteer - Sign Up for Service Event |
| Description / Steps | **As a potential ServeCentral user, I want to find and sign up for a service event near me** |
| Steps | 1. A user navigates to the search menu in the ServeCentral app <br> 2. The user inputs the name of the event they want to join in the search bar <br> 3. The user selects the event they wish to sign up for from the list of events in the search menu <br> 4. The user clicks on the `Sign Up` button on the event page |
| Primary Actor | Volunteer |
| Preconditions | The user has already created an account on the service |
| Postconditions | 1. The user is signed up for a service event <br> 2. The user can access information about the event through a menu in the app <br> 3. The user can view the location of the event on a map in the app |

| Use Case #2 | |
|---|---|
| Title | Service Agency - Post Event |
| Description | **As a service agency, I want to add an upcoming event to ServeCentral so volunteers can sign up for it** |
| Steps | 1. A representative user of the service agency selects `Add Event` from their profile page <br> 2. The user fills in the form on the following page (Location, Address, Time, Description, Minimum/Maximum Participants) <br> 3. The user confirms the posting of the event |
| Primary Actor | Service Agency |
| Preconditions | The agency has already added themselves to ServeCentral as a service agency |
| Postconditions | 1. The event to be hosted by the agency is added to ServeCentral's database <br> 2. The event to be hosted by the agency can be found on the agency's profile page |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Volunteers | Create Account | Add User |
| Service Agencies | Profile | Add Event |
| Events | Map | Update Volunteer Count for Event |
| Map Data | Search for Event | Search Events |

## Step 2.3 Diagram a Use Case in Architectural Terms
![Actor to MVC diagram](../assets/ServeCentral_Actor_to_MVC.svg)

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
INSERT Architectural change proposal here, and how it meets the two new requirements.  Explain both the benefits and draw backs of your proposal.

## Step 3.2 Revised Architecture Diagram
INSERT IMAGE HERE with a Description.

# Step 4: Scaling an Architecture
INSERT Architectural change proposal here, and how it meets the four new requirements.  Explain both the benefits and draw backs of your proposal.  If the changes are significant, then you need to explain why the changes are necessary versus a nice-to-have enhancement.

# Extra Credit
If you opt to do extra credit, then include it here.