# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Thomas McVey
**GitHub Handle:** ThomasMcVey  
**Repository:** https://github.com/ThomasMcVey/cis411_lab2_arch 
**Collaborators:** None
___

# Step 1: Confirm Lab Setup
- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is an all-in-one event registration solution which aims to grant its users a simple, consistent, and streamlined process for signing up for volunteering events. 

## Step 2.1 Representative Use Cases  

| Use Case #1       |                                                                                                                                  |
|-------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Title             | Sign up for highway cleanup                                                                                                                                                                |
| Description/Steps | 1. User logs into account 2. Map loads showing user's location and nearby events. 3. If user sees desired event, and meet the criteria for it, they apply and registration data goes to the server. 4. If not, user can broaden and limit search range and conditions. 5. If the user still cannot find a cleanup event that meets their conditions after repeated searches, a prompt will appear asking the user if they want to report a missing event. 6. If the user clicks yes, the user enters information on the type of event, what organization was hosting it, and any additional comments they may have. |
| Primary Actor     | Volunteer                                                                                                                     |
| Preconditions     | 1. User is logged into account. 2. User has access to Serve Central database server.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Postconditions    | Successful attempts to sign up for an event are recorded for statistic tracking, as well as failed searches.                                                                                                                                                                                                                                                            |

| Use Case #2 | |
|---|---|
| Title |Organization schedules event|
| Description / Steps |1. Organizer signs into organizer account. 2. Organizer selects create event, and enters in relevant data. 3. This data is passed to the server and waits for the event to be approved (This is to prevent abuse or misuse of events). 4. If the event is approved, then the event shows up on the map to be searched for. 5. If the event is rejected, user gets detailed report as to why, and steps they can take to get it approved.|
| Primary Actor |Event organizer|
| Preconditions |1. Organizer has all relevant data for event. 2. Organizer goes through the standard process for event registration and creation.|
| Postconditions |1. Event data is sufficient to allow showing up on map. 2. If the event is cancelled, it is updated immediately to prevent users from registering for a non-existant event. 3. Once an event is over, is automatically removed from map.|

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
|Loads startup data.  | User clicks on ServeCentral app from smartphone. |Launches ServeCentral app.  |
|Login information is received and allows user to login | User prompted to enter login infomation. | Login information sent to model to determine user.  |
|Gives back data on event.  | User clicks on event. | Event information request is sent to model. |
|Model is updated to reflect the new user registered for the event. |User applies for an event.  |User information is sent to model.  |

## Step 2.3 Diagram a Use Case in Architectural Terms
![alt text](/assets/Use_Case_Architecture.drawio.svg)

Details how a volunteer would go about signing up for a highway cleanup, as well as how it interacts with the view, model, controller, etc.

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
The new architectural pattern I would suggest is using the layered architectural pattern. The reason for this is that it would presumably allow the different third-party services to access data from the data store layer, and with the ability to add autonomous enhancements, should allow businesses to develop and implement their own specific interfaces. A drawback to adopting this pattern, however, would be the extra management and observation for the newly created layers, especially as those used to the previous structure will likely be unfamiliar with the new one.

## Step 3.2 Revised Architecture Diagram
![alt text](/assets/Layered_Architecture.drawio.svg)

Makes use of various layers for businesses to implement their specific interface implementations and access to other useful datasets.

# Step 4: Scaling an Architecture

The changes I propose are adopting a Peer-to-Peer Architectur, Load Balancing Broker, and Microservice based architecture. Peer-to-Peer would be useful to satisfy the sponsor's desire's and can be used to cut down on latency issues by having events(and other devices signed up for the event) within a certain distance of the user be used to update the interface, which would then be cross-referenced with a load balancing broker for consistency. Furthermore, the broker would then tie in with the microservice architecture, which would be used to traverse large, terabytes worth of data. Using microservice would also allow for examining patterns by seeing the changes made across the entire database by user and organizer input.

These changes are needed because the previous two architectures are either too limited in their ability to store and access data, or could result in potential delays that would customer satisfaction. This is not without potential difficulties though, as both peer-to-peer and microservice require a rather significant amount of foresight and understanding of how they work in order to properly implement. The benefits of utilizing these patterns, however, warrant the difficulties due to the aforementioned benefits.