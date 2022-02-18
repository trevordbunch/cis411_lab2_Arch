# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Logan Ossman  
**GitHub Handle:** loganossman  
**Repository:** https://github.com/loganossman/cis411_lab2_arch  
**Collaborators:**
___

# Step 1: Confirm Lab Setup
- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is an application meant to post and locate places in need of volunteers. This app is made in response to the lowering amount of volunteers in recent years.

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title | Search for Volunteer Opportunities |
| Description / Steps | 1. User will enter parameters for the distance and type of events. <br />2. User will sign up for certain events with more credentials. <br /> 3. User will use the app to make their way to the event. |
| Primary Actor | Potential Volunteer |
| Preconditions | 1. The user has created a login, and is verified upon logging in. <br /> 2. The system is not down for maintenance.|
| Postconditions | 1. User is not flagged for certain events. <br /> 2. Event requires another worker. <br /> 3. Event hosts accept the user as an event worker. |

<br />

| Use Case #2 | |
|---|---|
| Title | Create an Event |
| Description / Steps | 1. User will create an event with a location and a description. <br /> 2. User will designate whether the event is private or public. <br /> 3. User will invite particular individuals through the app to work the event. |
| Primary Actor | Potential Hosts |
| Preconditions | 1. The user has created a login, and is verified upon logging in. <br />2. The system is not down for maintenance.|
| Postconditions | 1. User is not flagged for any type of event. <br /> 2. Event has all required fields filled in, otherwise it will be saved as a draft.|

<br />

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Account Entity | Login Screen | Login Acceptance Code |
| Location Entity | Settings Screen | Google Maps API Code |
| Organization Entity | Events Creation Screen | Update Available Events Code |
| Event Entity | Map Screen | Register for Event Code |

## Step 2.3 Diagram a Use Case in Architectural Terms
[MVC Diagram](assets/MVC_Diagram.png)

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
Moving from MVC, the best architecture to change to would be a Microservices setup. It allows us to scale with incredible efficiency, which will help streamline the speed of inputing and retrieving data. This especially makes sure that small volunteer accounts do not take up too much data. A Microservices architecture will also allow for easy embedded integration with our provided API services. Finally, should we grow at an incredible rate, it is a good base for growth. The only difficulty is tracking and joining data between the app and embedded services. However, the larger companies would likely have accounts on each, so it is an easy issue to fix.

## Step 3.2 Revised Architecture Diagram
[Microservices Diagram](assets/Microservices_Example_Diagram.png)

# Step 4: Scaling an Architecture
Thankfully, most of the new requirements needed in this part are covered by the Microservices architecture. This fast load time and scalability easily knock out the first and second requirements. However, the third and fourth are difficult requirements to achieve with Microservices alone. To accomplish this, the system will become a Microservices/Client-Server hybrid. Most operations will be done on the Microservice end of things, although large-scale queries and views need a centralized location that is lacking in a regular Microservices system. As such, the best solution would be for a central database to store as much data as possible to streamline the queries needed for researchers and authorized parties.

# Extra Credit
If you opt to do extra credit, then include it here.