# Lab Report: Architecture Selection
___
**Course:** CIS 411, Spring 2022  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Andrew Coldsmith  
**GitHub Handle:** [andrewcoldsmith](https://github.com/andrewcoldsmith)  
**Repository:** [Forked Repository](https://github.com/andrewcoldsmith/cis411_lab2_arch)  
**Collaborators:** [Grace Schlauder](https://github.com/grace-schl); [Michael Mourelatos](https://github.com/MichaelMourelatos)
___

# Step 1: Confirm Lab Setup
- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is a mobile and web app that allows users to easily view and register for volunteer events. It also allows volunteer services to post events for sign up.

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title | Service Registration |
| Description | The user volunteers for an available event. |
| Steps | |
| | 1. The app displays a map view of the user’s area. |
| | 2. The user selects an event from the map. |
| | 3. The app displays dates and times the user can sign up for. |
| | 4. The user selects a date and time they would like to volunteer for. |
| | 5. The app notifies the user that they have been successfully registered and lists all prerequisites for the event. |
| | 6. The app notifies the service agency so the new volunteer can be vetted.|
| Primary Actor | Volunteer |
| Preconditions | The user must be logged in with a registered Serve Central account. |
| Postconditions | |
| | 1. The app notifies the service agency of the new volunteer. |
| | 2. The prerequisites for the service opportunity are added to the users tasks. |

| Use Case #2 | |
|---|---|
| Title | Event Posting |
| Description | The user publicly posts a future event for their Service Agency. |
| Steps | |
| | 1. The app displays options related to the service agency. |
| | 2. The user selects the “new event” button. |
| | 3. The app displays an event form. |
| | 4. The user enters information such as the title of the event, brief description, and dates and times. |
| | 5. The app posts the event for volunteers to register. |
| | 6. The app notifies the user that the event has been successfully posted. |
| Primary Actor | Service Agency Representative |
| Preconditions | The user must be logged in with a registered agency in the Serve Central system. |
| Postconditions | The app posts the event for volunteers to register. |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| user_credentials | Login Form | credent_verify |
| event_registration | Volunteer Registration Form | volunteer_register |
| events | Event Map | select_event |
| events | Service Agency Event Form | post_event |

## Step 2.3 Diagram a Use Case in Architectural Terms
This diagram shows the processes that take place within the system architecture when a user volunteers for a service event.

![Use Case Diagram](/assets/serve_central_use_case_diagram.jpg)

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
I would redesign the architecture moving away from a MVC approach toward a microservice design.

**Benefits**

 - Microservice architectures are great for integrating third-party services.
 - Microservices divide most services into individual databases, making it easy to embed forms into separate websites.
 - The microservice approach may be a good choice anticipating future growth of the service.
  
**Issues**

 - It would be a big undertaking to restructure the architecture. However, it would be worth it in the long run. 

## Step 3.2 Revised Architecture Diagram
A diagram of the Serve Central architecture revised to have a microservice design.

![Revised Architecture Diagram](/assets/revised_architecture_diagram.jpg)

# Step 4: Scaling an Architecture
I would keep the microservice architecture previously implemented.
1. Microservice architectures run individual services separately which greatly reduces latency compared to other architectures.
2. Since most services in a microservice architecture have their own databases, storage is not generally an issue.
3. Having separate databases for different purposes would make it easy to allow other parties to read and write information without giving them read or write access to important info like user credentials.
4. The separate databases would also make it simple to only give researchers access to relevant data related to volunteer patterns.

No changes are needed since the microservice architecture satisfies all the requirements. A disadvantage of a microservice architecture is that it would require significant security and maintenance support.

# Extra Credit
A comprehensive diagram of the Serve Central architecture.

![Comprehensize Architecture Diagram](/assets/final_architecture_diagram.jpg)

**Assignment Improvements**

1. Some other students and I were very confused with step 2.2. Based on the description, we thought we needed to find software used to create models, views, and controllers. It wasn’t until we compared what we had with other students that we realized we had done it completely wrong. Specifying that the table was supposed to be filled with examples of models, views, and controllers would have made the objective much more clear.
2. I also think making the assignment focus on our personal project proposals would be a very beneficial change. Requiring us to think through our proposals more thoroughly would be a great exercise.