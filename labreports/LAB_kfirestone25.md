# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2022  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Kylie Firestone  
**GitHub Handle:** kfirestone25  
**Repository:**  https://github.com/kfirestone25/cis411_lab2_arch   
**Collaborators:** Cmcculler1, Richard-Pokrivka
___

# Step 1: Confirm Lab Setup
- [X] I have forked the repository and created my lab report
- [X] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [X] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central simplifies volunteering by informing users of service opportunities in the area and providing a simple registration process. Using both Firebase and React Native, the application will offer both a web and mobile experience. 

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title | Searching and Registering for Service Opportunity|
| Primary Actor | Volunteer |
| Description | This use case describes how the volunteer will search for possible volunteer opportunities in their area and complete the registration process. |
| Preconditions | 1) The user must be authenticated by logging into his/her account. 2) The Serve Central application is available and online.|
| Normal Course | 1) The volunteer gives the application permission to use their location. 2) The system provides general information (date, time, location, etc.) of service opportunities within close proximity of the volunteer. 3) The volunteer selects the desired volunteer opportunity. 4) The system provides an in-depth description of the tasks associated with the volunteer opportunity. 5) The customer will click the "Register" button, provide necessary personal information and click the "Submit" button. |
| Postconditions | 1) Both Serve Central and the specified agency are notified of completed volunteer registration. |

| Use Case #2 | |
|---|---|
| Title | Receiving Volunteer Applications for Service Opportunities| 
| Primary Actor | Service Agency Representative |
| Description | This use case describes how the service agency obtains, reviews, and chooses applications for specific volunteer opportunities via the Serve Central system. |
| Preconditions | 1) The service agency must be authenticated by logging into their organization's account. 2) The Serve Central application is available and open. 3) The Serve Central system has collected and processed volunteer registration/applications. |
| Normal Course | 1) The Serve Central system notifies the volunteer agency of new user applications. 2) The representative of the service agency must read through and review volunteer applications. 3) Representatives will either reject or accept the application. If rejected, the representative must provide a specified reason. |
| Postconditions | 1) Serve Central system notifies volunteers of the acceptance or rejection of their applications. 

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Service Agencies | Submitted Applications | Search Bar |
| Volunteers | Service Feed | "Register" Button |
| Service Categories | Profile | "Login" Button |
| Current Service Opportunities | Map | Location Enabling |

## Step 2.3 Diagram a Use Case in Architectural Terms
![MVCDiagram](https://docs.google.com/drawings/d/e/2PACX-1vRx86JKtg6Kg2g4OsjEfe9AlmDsajnEln8xW6tIQllByIdCRNXk5cjT9zF64FBoDXz4PudbhLzyZbLD/pub?w=956&h=682)

In the MVC model, the volunteer is able to both see the Service Feed (View) and use the Search Bar (Controller) to find Current Service Opportunites (Model). The Controller manipulates the data stored in the Model, and the Model then updates the View so volunteers are provided with the most current service opportunities. 

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
I propose a change from a MVC model to a Client-Server model for Serve Central. The two requirements both require involvement by third-party organizations (churches and service agencies). One major benefit of a Client-Server model is that it has a single server that controls all of the data for the organization. Therefore, all clients are utilizing the same source of data, increasing consistency across platforms. However, there is a downside to Client-Server architecture. Since all data is centralized to one server, a failure of the server will halt all Serve Central operations. 

## Step 3.2 Revised Architecture Diagram

![Client-ServerDiagram](https://docs.google.com/drawings/d/e/2PACX-1vROOiREkZlm8gs4ZFfJQZ-NAVWBybKLqHv5KgA_RWifqbsrGsng3ETvbEZPSCx6B0kq_7zf3cerLYMl/pub?w=961&h=630)

In the Client-Server model for Serve Central, three parties (local churches, Serve Central employees, and service agencies) interact with the Cloud (Internet) to access data from the centralized Serve Central server. 

# Step 4: Scaling an Architecture

I propose a change from a Client_Server model to a Blackboard model for Serve Central. Since Serve Central is expanding on a much larger scale with these four requirements, having one centralized server holding all information is not exactly the most practical option. Archtiectural changes are most definitely needed. The new requirements all include collecting, storing and analyzing large amounts of data. Blackboard is primarily used for large multi-faceted data sets. Also, it provides storage for both raw and calculated data, which can include both our collected and analyzed information. However, Blackboard can be a very expensive investment for Serve Central. Given the complexity of this model, there will most definitely have to be extensive training for those working with the architecture firsthand. 