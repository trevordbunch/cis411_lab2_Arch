# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Alanah Inniss  
**GitHub Handle:** alanahinniss  
**Repository:** https://github.com/alanahinniss/cis411_lab2_arch.git  
**Collaborators:** 
___

# Step 1: Confirm Lab Setup
- [X] I have forked the repository and created my lab report
- [ ] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [ ] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is a mobile and web application that makes volunteering easier by storing information about service activities so that users can be aware of different service opportunites near them. Users also are able to sign up for events through the apps and statisitcs are also collected based their performance.  

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title | Signup for Volunteering Opporunity |
| Description | This describes how volunteers can sign up for service opportunities in the Service Central Application based on location. |
| Steps |  1. Users log into the Service Central application. |
| | 2. User browses and select an event. |
| | 3. User enters information required for the event. |
| | 4. User confirms registration. |
| | 5. Additional information about the confirmed service event is provided for the user. |
| | 6. The organization is notified that a volunteer has registered. |
| Primary Actor | Volunteer |
| Preconditions | 1. User has an account with Service Central. |
| | 2.  User location is enable for this application. |
| Postconditions | 1. Once a user is signup, a confirmation is sent. |
| | 2. The user's registartion information is sent to the Service Agency. |
| | 3. Service event is updated to show the current number of volunteers registered. |
| | 4. The user attends the volunteer event. |
| | 5. The user statistic is updated. |

| Use Case #2 | |
|---|---|
| Title | Posting a Service Opportunity |
| Description | Describes how a service agency can post a service opportunity. |
 Steps | 1. Service Agency employee logs into the Service Central Application. |
| | 2. Employee provides information about the event such as the location, description, time and the number of volunteers needed. 
| | 3. Once completed, the information presented by the service agency is sent to the Service Central to be reviewed and posted. 
| Primary Actor | Service Agencies |
| Preconditions | 1. Sevice Agency has an account. |
| | 2. Serivce Agency must be looking for volunteers. |
| Postconditions | 1. The event is posted on the Service Central Application with a sign-up sheet available. |
| | 2. Users that are near in location are notified that there is a new event available. | 

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Agency | Service Agency page  | Events advertisment controller |
| User Account | Login page | User stored information |
| Events | New Event Form | Add new events |
| Volunteer | Volunteer Registration Form | Registration for Events |

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