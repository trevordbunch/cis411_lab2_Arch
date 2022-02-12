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
- [X] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [X] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

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
![MVC DIAGRAM](../assets/mvc%20diagram.png)

This diagram is shows a set of MVC component for a situation in which the model is the volunteer, the view is the volunteer registration from and the controller is registration for a event. 

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
If Service central as to expand their services, I think it would be most effective to continue using MVC as the architectural model. Since it is not required, switching would be quite difficult. MVC is easy to adopt the changes necessary, therefore updating the exisitng mdoel would not be complicated. Also MVC archtecture components are reusable and they can be independently deployed or mainted. However, the issue with this is supporting multion views on the same model can be quite difficult. Also, mainting these changes would also be challenging. 

## Step 3.2 Revised Architecture Diagram
![MVC Diagram 2](../assets/mvc%20diagram%20updated.png)

This diagram add the "Third Party" to the model as the specific interface. By looking you can see that the flow of data continues mainly in the same path. This is because we are editing the current MVC model. 

# Step 4: Scaling an Architecture
Load balancing should be implemented to handle the increase in traffic. With the large burst of users, the use of this technique will decrease downtime, increase perfomance and creat redundancy. Load balancing will also assist with handling the necessary 50tb of data storage. However, the downside with load balancing is the cost. For the last two requirment using a Microservice architecutre would be best. The patterns of volunters can be easily examined.

A new architecture will be needed because the current one cannot handle the amout of traffic in the new requirements. With the organizaiton progessing at this rate, it is quite evident that the upgrades in all areas is necessary and will beneficial - it is important that the organzaiton is ready to accomadate an large amount of users. 