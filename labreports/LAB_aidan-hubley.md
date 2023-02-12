# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Aidan Hubley
**GitHub Handle:** aidan-hubley  
**Repository:** [Aidan Hubley](https://github.com/aidan-hubley/cis411_lab2_arch/blob/main/LAB_INSTRUCTIONS.md)  
**Collaborators:** Nason Allen, Ray Truex, ChatGPT
___

# Step 1: Confirm Lab Setup
- [X] I have forked the repository and created my lab report
- [X] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [X] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.
___

# Step 2: Analyze the Proposal
Serve Central is an app that makes it easy for volunteers to connect with events. Event data is handled in the application.
___

## Step 2.1 Representative Use Cases  

| Use Case #1         |                                                                                                                                                                                                                                                                                                                                                                                             |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Title               | Organization Creates Event                                                                                                                                                                                                                                                                                                                                                                  |
| Description / Steps | 1. An organization navigates to an event page. </br> 2. The organization selects a <button>create event</button> button. </br> 3. They fill out a form with information such as the event name, the number of volunteers needed, and the location and time. </br> 4. The organization submits the form with a <button>confirm new event</button> button, they receive a confirmation email. |
| Primary Actor       | Organization                                                                                                                                                                                                                                                                                                                                                                                |
| Preconditions       | 1. This organization must have already signed into the application.                                                                                                                                                                                                                                                                                                                         |
| Postconditions      | 1. The event is visible when a user searches for it, and it is visible under the organization.                                                                                                                                                                                                                                                                                              |

| Use Case #2         |                                                                                                                                                                                                                                                      |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Title               | Volunteer searches for event                                                                                                                                                                                                                         |
| Description / Steps | 1. The user navigates to the map tab. </br> 2. The user can navigate the map to view events near them. </br> 3. The user can select an event, which will display the event details and allow them to sign up with a <button>Sign Up</button> button. |
| Primary Actor       | Volunteer                                                                                                                                                                                                                                            |
| Preconditions       | 1. The user has logged into their account. </br> 2. The user has allowed the app to access the location services.                                                                                                                                    |
| Postconditions      | N/A                                                                                                                                                                                                                                                  |
___

## Step 2.2 Define the MVC Components

| Model              | View                | Controller               |
|--------------------|---------------------|--------------------------|
| Profile            | Profile page        | displayProfileInfo       |
| Map                | Map page            | displayMapWidget         |
| Event              | Event page          | displayEventInfo         |
| Event Registration | Register Event page | displayEventRegistration |
___

## Step 2.3 Diagram a Use Case in Architectural Terms
Use case 1 - Organization Creates Event:

![MVC Use Case 1](/assets/MVC_Use_Case_1.png)
___

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
Given the new requirements of integrating with third-party entities and building organization-specific interfaces on top
of Serve Central, a **Microservices Architecture** is the most appropriate solution. Microservices provide brokered 
communication while supporting independent changes, making it perfect for this scenario.

In a microservice architecture, the application is broken down into smaller independent services, allowing third-party
entities to integrate easily using APIs to input and retrieve data from the Serve Central model/datastore. It also 
allows for the creation of custom interfaces that can be built on top of Serve Central's business and data logic.

However, the microservices architecture also comes with drawbacks such as increased complexity and overhead as each 
service is a separate entity. This added complexity can increase communication latency and make troubleshooting 
problems more difficult. Despite these potential issues, the benefits of a microservices architecture likely outweigh 
the drawbacks for Serve Central's specific use case.
___

## Step 3.2 Revised Architecture Diagram
The new architecture that includes a Microservices architecture:

![Revised Architecture](/assets/Revised_Architecture.jpg)
___

# Step 4: Scaling an Architecture
To fulfill the requirements of the Gates Foundation grant, microservice architecture is still the best option. This allows the creation of individual services to fulfill specific requirements, such as the availability of submitted opportunities, increased database servers, and examination of patterns. Load balancing would ensure that services don't get overwhelmed and can dynamically scale up or down as needed. The flexibility and scalability of microservices can handle the system's growth and data storage, allowing more databases to be added, and user requirements to be met. For researchers, a centralized database could be added to easily access data from all vendors.

The benefits of microservices include scalability and flexibility, allowing vendors to have their systems and centralized data storage.

The drawbacks of the complexity of the system could lead to testing and security issues. 
___

# Extra Credit
1. Create and embed a comprehensive diagram of your final architecture (i.e. one that meets all the requirements 
of this lab, including Step 4).

    1. I suggested that a microservice architecture is still is optimal structure: ![Revised Architecture](/assets/Revised_Architecture.jpg)


2. Augment/improve the assignment. Suggest meaningful changes in the assignment and highlight those changes 
in the extra credit portion of your lab report.

   1. Step 5 part 3: "Choose the base fork tangollama/cis411_lab0 is the target and that your fully updated main branch is the source."
I believe it should say this: "Choose the base fork trevordbunch/cis411_lab2_arch is the target and that your fully updated main branch is the source."