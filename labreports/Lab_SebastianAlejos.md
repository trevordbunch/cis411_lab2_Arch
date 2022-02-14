# Lab Report: Architecture

___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Sebastian Alejos
**GitHub Handle:** SebastianAlejos
**Repository:** <https://github.com/SebastianAlejos/cis411_lab2_arch>
**Collaborators:**
___

# Step 1: Confirm Lab Setup

- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central ... ENTER A BASIC SYSTEM INTRODUCTION HERE (1-2 Sentences).

This system would allow a user to find service oportunities near them. It would also allow organizations to find volunteers in their area.

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title | User Signs up to volunteer at a service oportunity|
| Description / Steps | The user selects and confirms the service opportunity. |
| Primary Actor | Volunteer User.|
| Preconditions | 1. User has signed in. </br> 2. Service opportunity is still available. </br> 3. Service opportunity need volunteers.|
| Postconditions | 1. Confirmation of attendance is stored in the database.</br> 2. Confirmation of attendance is notified to user and organization.|

| Use Case #2 | |
|---|---|
| Title | Organization wants to set up an event|
| Description / Steps | Organization needs to put up an event for volunteers to be able to find it.|
| Primary Actor | Organization|
| Preconditions | 1. The user has signed into the organization account. </br> 2. The user enters the information for the event and saves it.|
| Postconditions |1. The event is saved in the database. </br> 2. The event is displayed in the events page.|

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
|Service Opportunities|Events List|ShowEvents  |
|Profile|Account Page|ShowProfile |
|Event location|Event information page|ShowEvent|
|Volunteers| Event Page|SignUp|

## Step 2.3 Diagram a Use Case in Architectural Terms

This is the use case for the Volunteers model.

![Volunteer Use Case](/assets/usecase.png)

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal

### Broker Architecture

Broker archtecture is best suitable in this case as it is designed for service distribution. A pro is that it facilitates communication between entities. It also adds security when working with third parties (volunteer organizations). A con would be that a broker adds a layer to the architecture, which can slow down the system.

## Step 3.2 Revised Architecture Diagram

![Broker Architecture](/assets/broker.png)

# Step 4: Scaling an Architecture

Microservice seems to be the best architecture for this type of demand. A new service could be implemented for each of the new requierements. A service can be created to manage different loads at different times, keeping a low latency. Another service would be implemented to allow researchers access to the data that they need to find patterns. A disadvantage is that up front cost to implement is high as the services need to be developed. An advantage of this type of architecture is that it is easily scalable as new services can be added as needed.

# Extra Credit

If you opt to do extra credit, then include it here.
