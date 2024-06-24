# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Felix Zarate 
**GitHub Handle:** @felixzrte  
**Repository:** felixzrte/cis411_lab2_arch  
**Collaborators:** 
___

# Step 1: Confirm Lab Setup
- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is an application that will make volunteering easier and simpler. Finding volunteer opportunities can be a hard process and registering constantly can be confusing. This app will make registration easier.````

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title |Find an Event |
| Description |This use case describes how the user finds an event |
|Steps|User uses search bar to type in an event they are looking for|
| Primary Actor |User|
| Preconditions |User creates an account, User gives location data,  Events are available in the Events database|
| Postconditions |List events searched for/ or in the area, Registration for event|

| Use Case #2 | |
|---|---|
| Title |Sign Up For An Event|
| Description|This use case describes how the user registers for an event|
| Steps |Click on event to bring up event info, Click on register, Fill out registration form, submit registration|
| Primary Actor |User|
| Preconditions |Find an event, Events are available in the Events database, Registration form is available|
| Postconditions |Registered for event, Will be contacted later about registration|

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Event Database| Search Bar| Search Controller |
| Registartion Database | Registration Page | Registration Controller |
|  Login Database|  Login Page| Login Controller |
| Map Data | Map View |Map controller  |

## Step 2.3 Diagram a Use Case in Architectural Terms
![Use Case Diagram](../assets/Use%20Case.png)
# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
Service central would need to allow the data they collect from users to be available for other 3rd part services. They would need to change the architecture so that they are able to make their data modifiable by others. Service Central would need to develop an app so that other websites can use their registration process embedded within their site.
## Step 3.2 Revised Architecture Diagram
INSERT IMAGE HERE with a Description.

# Step 4: Scaling an Architecture
1. Consuming bursts of 10k+ new volunteer opportunities per hour with a latency of less than 15 seconds between submitting an opportunity and it's availability in the registration service.
These interactions would be client-to-server. The servers need to be able to handle this capacity of volunteer opportunities. The opportunities need to be able to communicate directly to the web server and be able to update the daatabse that stores all available events. There also needs to be a check on the availability. 
2. Supporting a volunteer and event data store that will quickly exceed 50TB of data.
The expansion of data storage is necessary because there will be a lot of data being modified, stored, and deleted. Each of the controllers needs to be able to communicate with all the models and those models need to be able to have enough storage so that operations can run smoothly.
3. Allowing authorized parties to issue queries that traverse the TB's of data stored in your datastore(s).
Allowing authorized authorities to be able to update data instantly is important. With many users, there will be many queries being sent back and forth and when admins need to be able to do something with the data, it is important that they can transverse the queries.
4. Enabling researchers to examine patterns of volunteer opportunities as a way of determining future grant investments.
With all the upgrades to the datstore, it would be a good idea to analyze all the data collected. It is important because by analyzing teh data, Service Central is able to capitalize off that and improve user experience, business opportunities and overall experience.
# Extra Credit
If you opt to do extra credit, then include it here.