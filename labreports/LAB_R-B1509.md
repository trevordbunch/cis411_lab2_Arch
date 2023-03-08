# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Rachel Beattie
**GitHub Handle:** [GitHub Handle](https://github.com/R-B1509)
**Repository:** [Your Forked Repository](https://github.com/R-B1509/cis411_lab2_arch)  
**Collaborators:** 
___

# Step 1: Confirm Lab Setup
- [ X] I have forked the repository and created my lab report
- [ X] I have reviewed the [lecture / discussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [ X] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central's system proposes to record the information and processes needed for users to use an account to sign up for different events, through the use of Firebase and React Native. The User-Profile is linked with an email, within its records are history of volunteer work as well as the type; on maps, events and volunteer work type is recorded, with more details on another page including  how many volunteers are registered and which company is holding the event.
## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title | Registration for event - Volunteer |
| Description| **To register for an event through the application** | 
|Steps| 1. Navigate to webpage or application<br> 2. Login to account|
|Action Path Map (Cont. from step 2)| 3. Access maps<br> 4. Click on an event pin for more information<br> 5. Register for event if desired, else repeat Step 4 with a different pin or move to Action Path List|
|Action Path List (Cont. from either step 2 or Path Map)| 5. Access the list of events<br> 6. Select desired event or update areas<br> 7. Register|
| Primary Actor | User of Application |
| Preconditions | Registration of Account: See [UseCase_Sample](https://github.com/R-B1509/cis411_lab2_arch/blob/main/assets/UseCase_Sample.md) |
| Postconditions | Volunteer registered for event |

| Use Case #2 | |
|---|---|
| Title | Event Registration - Service Agency|
| Description | **For want of an event to be held, volunteers are needed**|
|Steps| 1. Navigation toward webpage or application<br> 2. Login to account<br> 3. Register the event (include a description, type of event, location, time of being held, singularity or repeated status, and capacity limitations if need be)<br> 4. Close registration at designated time of choice, if desired |
| Primary Actor | Service Agency |
| Preconditions | Agency has been registered in database |
| Postconditions | Event registered in directory along with location, description, type, timing, status of repetition and volunteer numbers |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| User Information | User Profile including Name, Email, and Activity History | Change Information: Name, Email, Update Profile Picture, Link with Event List Model |
| Service Agencies | Registration of Events, company information | Allows for agencies to register an event for users to register for, including event information such as Location, Type, current number of attendees, and description |
| Event List | Event Name, Distance from User Location, and Attendees | Update area List, allows user to register for an event |
| Location Services  | User's Local Location, events within the Local Location, Map of area | Allows users to click an event pin linked to event list, allows for location details including distance from user to be accessed by Event List |

## Step 2.3 Diagram a Use Case in Architectural Terms
![Use Case for App](/assets/UseCaseRegisterForEvent.drawio.svg)
 ##### Use Case 1
- Summary: User, Actor, registering for a selected event in the Event List. Top-down level Use Case Diagram
  
![Use Case Combination](/assets/Lab2Diagram.drawio.svg)
##### Use Case Combination
- Summary: Actors such as user registers or logins, Location tracks event data and Users, while using the data to show the location of events in relation to users. Agencies create accounts, login, or create events, of which event creation is tied to Agent account while forwarding the information to event Register, which displays to User and allows User to register through their account. User accounts are used in response to registration in event register data, keeping past history which can be viewed.

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal

<p> The use of packaging and a 3-tiered system may work. The retrieval of information with different application servers aids in organization-specific interface design in addition to any third-party service. That being said, combining different application servers to a main database would be taxing on network speed. Using elements of "packaging" to enable customization, but without the complexity or time-consumption of custom building, known as the "workarounds", should allow organization-specifics as required even with third-party proxies but still use Serve Central's logic. 
</p>
<p> Unfortunately, updates with the main server's code may end up impeding third-party services and specific interfaces, possibly causing the data storage to suffer though a local memory storage would aid in this. That being said, customization of specific applications and interfaces, as well as the ability for scaling to multiple parties would be beneficial.
</p>

## Step 3.2 Revised Architecture Diagram
![Revised Diagram](/assets/Lab2Part3.drawio.svg)


# Step 4: Scaling an Architecture
  <p> Here continuous integration would be a major help. Processing thousands of data with less than 15 seconds latency would be a lot to do, so with continuous integration setting up the configuration, the "jobs" would be multiple events being registered, then pushed into cloud environment to handle the vast amount of data. That aspect of the hybrid cloud would be able to allow for expansion of storage as needed for event and volunteer data but still keep data secured in Serve Central's main network, which would run a storage area network. This way of storage would allow for multiple parties to access data but in a way that the server places out multiple "storage" servers that can be traversed separately but still connected. With everything in a "major" network, it enables data to be kept tracked of by researchers.
  </p>
  <p> The benefits of continuous integration is speed, the benefit with cloud computing is its scalability, which is a coinciding benefit with a storage area network. That being said, there is the possibility of data loss from a "cloud" crashing, and there is a dependency on the network running smoothly and having services that can run without grid-locking each other. Without cloud, there would be a delay in scalability, thus making it nearly impossible to handle third-party applications in addition to thousands of TB in data. The server virtualization is necessary for queries to be able to search through the vast amount of data from multiple points, and continuous integration is necessary to update that data. Without continuous integration, I don't see how it's possible for over 10k of volunteer activities to be registered without a build-up delay, even if they're coming in at various times over each hour, doing it all at once or as they come in would keep increasing the delay time, much like how appointments run over at a doctor's office.
  </p>
