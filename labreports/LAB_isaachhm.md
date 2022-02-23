# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Isaac Ho
**GitHub Handle:** isaachhm  
**Repository:** https://github.com/isaachhm/cis411_lab2_arch.git
**Collaborators:** Azianna Yang (ay1191) collaborated with revising the architecture.
___

# Step 1: Confirm Lab Setup
- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central allows users to find volunteering oppurtunities throughout their area and registration all in one application.

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title |Volunteer|
| Description |This use case describes the steps taken by the volunteer to sign up for service event through the application.|
| Steps |1. Volunteer selects the event.</br>2. Volunteer inputs their details or the system automatically inputs their details if their details are saved. </br>3. Volunteer gets a confirmation on their registration.</br>4. The organization receives an email on the new volunteer that applied.|
| Primary Actor |The volunteer|
| Preconditions |1. The user has an account with all their details.</br>2. There are events nearby the volunteer.|
| Postconditions |1. The user was able to sign up for the event.</br>2. The user's details are saved for future use.|

| Use Case #2 | |
|---|---|
| Title |Organization Agent|
| Description |This use case describes the procedure of an organization agenct posting events on the application.|
| Steps |1. The agent navigates to the new event post page.</br>2. The agent inputs all the necessary details of the upcoming event such as description, location, time, and date.</br>3. The agent receives a confirmation of the new event posted.|
| Primary Actor |Service agent|
| Preconditions |1. The agent has an account on the application that is associated with the organization.</br>2. The agent has details on an upcoming event by the organization.|
| Postconditions |1. The agent is able to post a new event calling for volunteers.</br>2. Users are able to view the event posted and apply.|

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| User Account | Profile page | CreateUserController |
| Event Location | Event page | CreateEventController |
| Event Title | Event Feed | EventFeedController |
| Agency | Organization page | OrgAccountController |

## Step 2.3 Diagram a Use Case in Architectural Terms
![Use_Case_Diagram](/assets/useCase.jfif)
</br>When the user requests to make an account, the CreateUserController would manipulate the model to create the account as specified with the user details. The model then updates the profile page which is where the user will be able to view their account details.

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
I would continue using the MVC architecture and modify the structure based on the reevaluation. This is because, using a new architecture may cause issues and the current architecture works fine for our current situation. The MVC architecture can get very complex quickly as Serve Central would need to create an API for organizations to link their profiles, which is difficult if the model changes frequently. This API will be used for the third party to input data.

## Step 3.2 Revised Architecture Diagram
![Use_Case_Diagram](/assets/revisedCase.jpg)
</br>This diagram enhances the already established MVC model that was previously proposed. It incorporates the third party and receives data from organization-specific interfaces. The third party communicates with the model by returning information when the model sends information to the third party. The organization-specific interface is forked by the controller and data is passed through the view. This shows the user that they are able to interact with the organization's site.

# Step 4: Scaling an Architecture
Load balancing is needed in this case to handle the increased traffic. This will decrease the downtime, help with mainting the latency to less than 15 seconds, and create redundancy. Load balancing architecture will be easily scalable, hence, handling the 50TB of data storage will be easier. The cost of load balancing would be a drawback. 

However, implementing a microservice architecture would also be a good solution. With a microservice system, its broker-like system would allow multiple data servers to be connected and conjoined to store terabytes of data. The last two requirements can be satisfied with this architecture, due to the optimized framework of microservice. Therefore, the current MVC architecture should be replaced as it will not be able to handle the sheer amount of data coming in from 1 million registrations per month.
