# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021 
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch) 
**Name:** Ryan Donat
**GitHub Handle:** ryandonat 
**Repository:** https://github.com/ryandonat/cis411_lab2_arch.git
**Collaborators:** referenced Julina Metz, Joeseph Tonnies, and Alec Chapel's work for inspiration and understanding.
___
 
# Step 1: Confirm Lab Setup
- [X] I have forked the repository and created my lab report
- [X] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [X] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.
 
# Step 2: Analyze the Proposal
   Serve Central is a fully funded and resourced project which attempts to solve some common issues with volunteering research, such as finding new oppertunities, as inconsistent and confusing registration processes. Serve Central its a moible and web application which solves these issues by putting all registration in one simple application, all event and company information in one location, and have user statistic tracking.
 
## Step 2.1 Representative Use Cases 
 
| Use Case #1 | |
|---|---|
| Title | Volunteer Registration Request for Service Event |
| Description / Steps | (1.) User logs into account
|| (2.) User searches for prefered event based on location and event title/  descriptions.
|| (3.) User selects event and enters any information required.
|| (4.) User confirms registration.
|| (5.) User is provided confirmation of registration and additional event details such as meeting times and meeting location.
|| (6.) Listing organization is notified of user registration for event. |
| Primary Actor | Volunteer/User |
| Preconditions | (1.) Volunteer/User has created an account.
|| (2.) Organization has event listed.
|| (3.) Volunteer/User passes necessary event requirements  |
| Postconditions | (1.) Volunteer/User's account updates/notifies user of any changes or updates for event/
|| (2.) Service event organization provides a list of current volunteers that are registered.
|| (3.) Organization is updated of any user cancelations or changes.    |
 
| Use Case #2 | |
|---|---|
| Title | Service Event Registration |
| Description / Steps | (1.) Organization logs into account.
|| (2.) Organization selects new event registration.
|| (3.) Organization enters in necessary details about event.
|| (4.) Organization confirms registration.
|| (5.) Organization is provided confirmation of event registration. |
| Primary Actor | Organization |
| Preconditions | (1.) Organization has an account registered as an organization, not a volunteer.
|| (2.) Even meets required volunteering conditions. |
| Postconditions | (1.) Event is posted for volunteers to see and register |
 
## Step 2.2 Define the MVC Components
 
| Model | View | Controller |
|---|---|---|
| Service Events | Available Service Events Page | eventsController |
| Organization | Organization Page | profileController |
| User | Volunteer Registration Form | volunteerRegistrationController |
| Event | Event Registration Form | eventRegistrationController |
 
## Step 2.3 Diagram a Use Case in Architectural Terms
![Use Case Diagram](/assets/Lab3diagram1)
 
This diagram depicts the use case of a volunteer registration request. When a user wants to register for an event, they navigate to the volunteer registration form. A user will enter the necessary information, which using the volunteerRegistrationController will go through the volunteer registration model. From there, a database will be queried and then the update the view for the user.
 
# Step 3: Enhancing an Architecture
 
## Step 3.1 Architecture Change Proposal
 
Serve Central should continue to use the MVC (Model, View, Controller) architecture since change to architecture is tedious and costly, and the MVC model can be manipulated to fill the new requirements necessary. These changes of growth and oppertunity actually support the MVC model since it is popular opinion that the MVC model doesn't work effeciently for smaller applications. Sticking with the MVC model will save the Serve Central money and issues from switching models. A possibler drawback is that the complexity curve of MVC architecture is steep, which means frequent changes and updates to the model can be tough on views.
 
## Step 3.2 Revised Architecture Diagram
![Revised Diagram](/assets/Lab3diagram2)
 
This diagram depicts the revised use case of a volunteer registration request. When a user wants to register for an event. This model allows for third party services to retrieve data from the model/database, as well as allow information from the model to be updated to an organization specific interface or view of the form.
 
# Step 4: Scaling an Architecture
 
The first implementation Serve Central should make is load balancing. In order to handle more than 100k daily active users and 1M event registrations per month (more specifically being able to hand the burst of traffic with 10k+ new oppertunities per hour with less than 15 ms latency with submissins), load bnalancing architecture will allow for redundancy and will be much more easily scalable so that the exceeding 50TB of data storage space can continue to grow/be managed.
 
Another architecture that would help satisfy authorized party queiries that traverse the database and enabling examination of volunteer opportunities would be microservice. Microservice architecture is very flexible in the using of technologies and capabilities, especially in the negotiation of data requests.
 
There would need to be a new implementation of architecture since the current MVC model can't handle the scalability that is planned for, or even already happening, and will get too complex too quickley. Microservice looks to be the best solution for satisfying current requirements.
 
# Extra Credit
If you opt to do extra credit, then include it here.

