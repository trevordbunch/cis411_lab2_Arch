# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Robbie Dorsey  
**GitHub Handle:** airgo32  
**Repository:** [Repo](https://github.com/airgo32/cis411_lab2_arch)   
**Collaborators:** Micah Johnson (@mcjo163), Josiah McCracken (@scribhneoir)
___

# Step 1: Confirm Lab Setup
- [X] I have forked the repository and created my lab report
- [X] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [X] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
&nbsp;&nbsp;&nbsp;&nbsp;Serve Central is a solution to make volunteer events easier for people to find. Users can find and register for lots of local volunteer events all on one app.

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title | Create an event |
| Description / Steps | 1. The agency starts the process of creating an event<br>2. The agency adds a title, description, location, date and time, and event category<br>3. The agency adds any extra fields that they want attendees to fill out<br>4. The event is created and the information is stored in the Serve Central database|
| Primary Actor | Service Agency |
| Preconditions | 1. The agency is registered with Serve Central<br>2. The agency already has an idea and planned time and place |
| Postconditions | 1. The agency has an event scheduled with a time and place<br>2. Users can locate and register for the new event<br>3. The agency is notified about new attendees for their event |

| Use Case #2 | |
|---|---|
| Title | Register for an event |
| Description / Steps | 1. The user selects an event which they want to attend<br>2. The user fills out any information requested by the agency<br>3. The event is added to the user's list of upcoming events |
| Primary Actor | Volunteer |
| Preconditions | 1. The user must be registered on Serve Central<br>2. There must be at least one event scheduled by an organization |
| Postconditions | 1. The user is now registered for a specific event<br>2. The user is notified about time conflicts if this event overlaps with another |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Users | Create an account / Register an organization | Add new user to database |
| Organizations | Create a new event | Request data for event view |
| Planned Events | Browse nearby events | Update event attendance |
| Past Events | View user profile | Add new organization to database |
|  |  | Add new event to database |

## Step 2.3 Diagram a Use Case in Architectural Terms
This UML Sequence diagram describes the process for a user to view an event.    
![UML Sequence Diagram](..\assets\View_Event_UML_Sequence_Diagram.jpg "UML Sequence Diagram for viewing an event")  

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
&nbsp;&nbsp;&nbsp;&nbsp;For incorporating these new requirements, I think it would be feasible to stick with the MVC architecture. This could be handled by creating an API for accessing Serve Central data. This would meet the first new requirement by allowing third parties to access the data by using the API. The second solution could also be handled by the API, allowing the organizations to create their own forms and use the Serve Central API to access the database.     
&nbsp;&nbsp;&nbsp;&nbsp;The biggest benefit of this system would be that the existing functionality doesn't have to be recreated in a new architecture, since it's still using MVC. The existing architecture is also easily adaptable, which would make it very easy to implement new functionality. The biggest drawback to sticking with this system is probably the rigidity that third parties would have to adhere to when using the API. Since the same models providing data to the users are the same models that would use the API, a third party would have to format their data to match the models, and that party might want to track some information that wouldn't be easy to store without making changes to the model.

## Step 3.2 Revised Architecture Diagram
This use case diagram shows how the new functionality would be incorporated alongside the existing uses. Using MVC architecture, the custom built interfaces using the API would serve as the views. The controllers would update the database and the models should stay the same.
![Use Case Diagram](..\assets\Revised_Serve_Central_use_case_diagram.png "Updated Serve Central use case diagram")  

# Step 4: Scaling an Architecture
&nbsp;&nbsp;&nbsp;&nbsp;For scaling up the system, I would switch to a microservice architecture with some elements of a brokerage architecture. For one, microservice architecture by design lends itself well to scalability. This architecture would easily satisfy the third and fourth requirements, since those actions could be expressed through microservices. I decided to incorporate a brokerage architecture as well, since I think that architecture would be better for the first two requirements. The numerous servers of a brokerage architecture could decrease latency by increasing the number of requests that can be processed at a time, as well as support huge amounts of data. The biggest drawback is that the brokerage architecture has the potential to introduce a lot of overhead, which could interfere with the individual processes of the microservice architecture.