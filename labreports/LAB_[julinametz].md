# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Julina Metz  
**GitHub Handle:** [julinametz](https://github.com/julinametz)  
**Repository:** https://github.com/julinametz/cis411_lab2_arch  
___

# Step 1: Confirm Lab Setup
- [X] I have forked the repository and created my lab report
- [X] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [X] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve central is a web and mobile application that allows volunteers to register and search for service opportunities in their area.

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title | Volunteer Registration for Service Event |
| Description / Steps | 1. Volunteer selects event 
||2. Volunteer enters any information required for the event
||3. Volunteer confirms registration
||4. Volunteer is provided with additional details such as exact meeting time and location for the event
||5. Organization is notified a volunteer has registered.   |
| Primary Actor | Volunteer |
| Preconditions | 1. Volunteer has created an account |
| Postconditions | 1. Volunteer’s account updates to show they attended the service event 
||2. Service event updates to show current number of volunteers registered |

| Use Case #2 | |
|---|---|
| Title | Service Event Registration |
| Description / Steps | 1. Organization navigates to new event registration page
||2. Organization enters all necessary details including but not limited to: location, meeting time, and service event description.
||3. Organization confirms registration |
| Primary Actor | Organization hosting a service event |
| Preconditions | 1. Organization has created an account
||2. Organization has been verified |
| Postconditions | 1. The event is posted for volunteers to see |


## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Service Events | Available Events Feed | ShowEventsController  |
| Organization | Organization Information Page | ShowProfileController |
| Events | New Service Event Form | AddEventController |
| Volunteer | Volunteer Registration Form | RegistrationEventController |


## Step 2.3 Diagram a Use Case in Architectural Terms
![Use Case Diagram](/assets/Use%20Case%20Diagram.PNG) When an organization wants to add a new service event, they navigate to the New Service Event Form view. They will enter the service event information, which will be passed through the AddEventController to the Events Model. The Events Model will update the information in the database and update the view to show the organization a confirmation of the added event. 

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
I would continue using MVC as the architectural model even with the added requirements. Switching architectural models after several months of successful operation would be difficult and  since it isn’t necessary to incorporate the new features, it isn’t worth it. One drawback is that the MVC architecture could become difficult to maintain when more changes are required down the line. 

## Step 3.2 Revised Architecture Diagram
![Revised Diagram](/assets/Revised%20Diagram.PNG)  
The third party now has access to the model to input and retrieve data. The organization specific interface is connected to the controller and view to show that the user can interact directly with the website through the controller, or they can access the site from an organization specific interface and that will affect the view.

# Step 4: Scaling an Architecture
Load balancing should be implemented to handle the increase in traffic. It will be able to handle the bursts in traffic and deliver with latency of less than 15 seconds. The load balancing architecture also allows for redundancy and it will be easily scalable so we can handle the necessary 50TB of data storage. One downside for implementing load balancing is the cost.   

Microservice architecture would work well to satisfy the last two requirements because it can offer brokered communication for authorized parties to access the data they need. It would easily be able to examine patterns of volunteers. Microservice would also be able to handle increased traffic flow and is easily scalable for growing data storage requirements. 

A new architecture will be needed because the current architecture cannot handle the amount of traffic in the new requirements. Microservice is probably the best option for the current requirements, however load balancing is also a good option. 