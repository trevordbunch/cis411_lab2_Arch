# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Jeff Sinsel  
**GitHub Handle:** JeffSinsel  
**Repository:** [My Forked Repository ](https://github.com/JeffSinsel/cis411_lab2_arch)
___

# Step 1: Confirm Lab Setup
- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is an application that helps volunteers find events to help with.

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title |  Event Registration - Event Organizer |
| Description | **As a potential ServeCentral event organizer, I want to register an event, so that I can reach volunteers in my area.** |
| Steps |  1. An individual navigates to the ServeCentral webpage, and clicks `Organize Event`.  <br> 2. The individual completes an initial event registration form  (Event name, description,address, time, number of volunteers needed).  <br> 3. The registration form will validate the following conditions: address exists, time is in the future, and terms of service is checked.  <br> 4. After confirmation that the event is created, a message pops up on the site to let the user know, confirming the event. |
| Primary Actor | Event Organizer |
| Preconditions | 1. The User has logged in. <br> 2. has a valid Event Organizer account.  |
| Postconditions | 1. The user receives email confirmation their event has been published. |

| Use Case #2 | |
|---|---|
| Title |  Register for Event - Volunteer |
| Description | **As a potential ServeCentral volunteer, I want to register for an event, so that I can volunteer at said event.** |
| Steps |  1. An individual navigates to the ServeCentral webpage, finds an event they would like to volunteer at, and clicks `Register for Event`.  <br> 2. The individual picks the role and time they would like to volunteer.  <br> 3. The registration form will validate the following conditions: time slot and role are not full, time slot is not overlapping prior commits, and terms of service is checked.  <br> 4. After confirmation that the individual is registered for the event, a message pops up on the site to let the user know, confirming the volunteering. |
| Primary Actor | Event Organizer |
| Preconditions | 1. The User has logged in. <br> 2. has a valid Event Organizer account.  |
| Postconditions | 1. The user receives email confirmation their time slot has been reserved as well as directions to the event. |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Past Events | Event History List | loadPastEventsByUser |
| Upcoming Events | Event List | getCurrentEventsByDate |
| Event Organizers | Profile List | viewProfiles |
| Upcoming Events by distance | Map | sortAndDisplayEventsByDistance |

## Step 2.3 Diagram a Use Case in Architectural Terms
![diagram](../assets/MVC%20diagram.svg)

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
Based on the requirements, a suitable architecture for Serve Central would be a broker architecture. A broker architecture is a design pattern in software engineering that uses an intermediary component (a broker) to handle communication and coordination between different components or services within an application. In the context of ServeCentral, a broker architecture could be used to manage the flow of data and requests between the volunteers and the local events they wish to participate in.

Benefits:

1. Scalability: A broker architecture allows for easy scaling of the application. As the number of users (volunteers and events) grows, the broker can manage the increased traffic and distribute requests among different components, ensuring smooth and efficient communication.

1. Modularity: The use of a broker allows for greater modularity of the application. Different components can be developed independently and integrated with the broker, without having to worry about how they will communicate with other components.

1. Flexibility: The broker can be easily replaced or upgraded without affecting the rest of the application. This allows for greater flexibility in the development and maintenance of the app.   

Drawbacks:  

1. Complexity: The use of a broker adds a layer of complexity to the application, which may make it harder to understand, develop, and debug.

1. Single point of failure: The broker is a single point of failure in the system. If the broker fails, the entire application could be affected.


## Step 3.2 Revised Architecture Diagram
![diagram](../assets/arc%20diagram.svg)

# Step 4: Scaling an Architecture
In the context of a large-scale version of ServeCentral, a microservice architecture can provide several benefits:

1. Scalability: One of the primary benefits of a microservice architecture is its ability to scale independently. Each microservice can be scaled up or down based on its specific workload, allowing the application to handle a large number of users without overloading any particular component.

2. Flexibility: In a microservice architecture, each service is designed to perform a specific function, making it easier to develop, test, and deploy new features.

3. Resilience: Since each microservice is self-contained, a failure in one service does not necessarily affect the entire application.

4. Agility: With a microservice architecture, the application can be updated and deployed more quickly and efficiently. Each service can be updated separately, without affecting the entire application, allowing for faster iteration and deployment cycles.

Overall, a microservice architecture can help ServeCentral handle a large number of users while maintaining flexibility, resilience, and agility. However, it is important to note that implementing a microservice architecture can be complex, and requires careful planning and design to ensure that services are well-defined and communicate effectively with each other.