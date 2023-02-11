# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Wade Buhr  
**GitHub Handle:** wadebuhr  
**Repository:** https://github.com/wadebuhr/cis411_lab2_arch   
**Collaborators:** None
___

# Step 1: Confirm Lab Setup
- [ X] I have forked the repository and created my lab report
- [ X] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [ X] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is an app that attempts to solve the problems of serving. Serve Central's solution is for all registration to be in one app with all the event and company information as well. 

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title |Registering for a Service - Volunteers |
| Description | As a ServeCentral user, I want to register for an upcoming service event|
| Steps |1. An individual navigates to an organization's service page, and clicks register for event <br> 2. The registration automatically takes down their name and information and validates it <br> 3. The event confirms their registration and adds them to their overall count of volunteers.|
| Primary Actor |Volunteer |
| Preconditions |1. Must already have and account with ServeCentral |
| Postconditions |1. The user is registered to serve and the events scheduled time <br> 2. The user recieves an email confirmation |

| Use Case #2 | |
|---|---|
| Title |Registering a Service - Service Agency|
| Description |As a service agency, I want to register my service so that ServeCentral users can find and volunteer |
| Steps | 1. Service Agency navigates to ServeCentral webpage and clicks "Register an Event" <br> 2.Service Agency completes initial registration form (Company Name, address (Email and physcial), Companay Website, etc) <br> 3. Someone from ServeCentral has to go over the information and validate it as a beneficial volunteering event <br> 4. After validation, the Service Agency is sent a confirmation email |
| Primary Actor | Service Agency|
| Preconditions |1. Must be a real company <br> 2. Must have a account|
| Postconditions |1. The service agency has their event posted for ServeCentral users to view and register for <br> 2. The service agency recieves an email confirming their event |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Number of Volunteers at an Event | Service Event Page | User Registration Button |
| How Far Away is an Event | User Statistics Page | Event Registration Button |
| Total Hours Volunteered | User Registration Confirmation | View Even Information Button |
| Total Number of Available Events | Map of Events Near User | Update User Statistics Button |

## Step 2.3 Diagram a Use Case in Architectural Terms
![MVC](https://docs.google.com/drawings/d/e/2PACX-1vRBCAeBZ4gBYMuSR7qikOaVl_-QGxtfPe56JIhjVuoMHoGgBVndMZD5gP9c_X_de7henbcnK2jYAnlw/pub?w=480&h=360 "MVC Diagram")  
The above image shows how a User wanting to register for an event would look like given a MVC architecture.

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
I would try to use the Broker architecture. This archiecture meets the two new requirements because it declutters all the services through a communication broker. Thirdparty services to input and retrieve data from our datastore, and the building of organization-specific interfaces would be brokered so that they don't run the risk of interfering with each other and the main ServeCentral database. This will make service distrubion transparent to the clients and supports dynamic editing of entities. However this architecture runs the risk of adding two many factors to keep control of, and may be complex to handle. 

## Step 3.2 Revised Architecture Diagram
![BrokerArch](https://docs.google.com/drawings/d/e/2PACX-1vTgiPmi06HUbErHzwXKlLDvPL0hFZ3tvg6cZwkneD1jH1JUfPDqzjoPM4EISkfCvvMhRp28_1jpKKN-/pub?w=480&h=360 "Broker Architecture")
This image shows how broker allocates data to each service without the services being entangled with each other.

# Step 4: Scaling an Architecture

The Architectural pattern that I would employ with all these new needs would be microservice. This is now a big enough company with well defined boundries that we should incorporate a number of different tiny programs instead of buidling one big one for every new feature we want to add such as supporting a volunteer and event data store that will exceed 50TB of data. Some downsides that this may cause is the confusion of uses as parts of the app appear later than others, and the communication costs can be significant due to how spread apart the tasks are. But since this is a rapidly developing company, we need this sort of Architecture. These new changes are needed because technology is advancing and our company needs to advance with it, but mainly since we are gaining a ton of new users, we need are going to need more data space, and enhancements that will keep the users happy and coming back. 

