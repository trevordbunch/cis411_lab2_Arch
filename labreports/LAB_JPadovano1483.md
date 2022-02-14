# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Jamie Padovano
**GitHub Handle:** JPadovano1483
**Repository:** https://github.com/JPadovano1483/cis411_lab2_arch
___

# Step 1: Confirm Lab Setup
- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is a a moblie application that will allow the user to easily find new volunteer opportunities and register for them. It will track user statistics so they will be able to see what types of events users have preferred to volunteer for in the past. 

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title | Volunteer Looking for Service Opportunities |
| Description / Steps | Describes how the user finds and signs up for service opportunities in their area |
| Primary Actor | Volunteer |
| Preconditions | 1. Volunteer has an account and is signed in <br>2. Location services are turned on on the user's device <br>3. Volunteer finds an opportunity to sign up for |
| Postconditions | 1. Volunteer is signed up for service opportunity <br>2. Volunteer is sent a confirmation of signup along with all the necesary details (i.e. organization, location, time, type of service, etc.) |

| Use Case #2 | |
|---|---|
| Title | Service agency lists upcoming service opportunities |
| Description / Steps | Service agency is looking for volunteers and inputs the event info into the application which stores this info in its database|
| Primary Actor | Service Agency |
| Preconditions | 1. Service agency has an event planned <br>2. Agency is looking for more volunteers |
| Postconditions | 1. Service agency is notified of all volunteers that sign up through the application <br>2. Agency runs the event |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Service event is listed in the application's database | Nearby service event list | Tells view to display service event info |
| Login credentials checked | Login Page | Tells view to change based on login attempt success |
| New user sign up| Account sign up page | Tells view to change based on new account creation |
| User volunteer history data | Home page | Tells view to display user data |
| Organization information | Organization Page | Tells view to display organization information |

## Step 2.3 Diagram a Use Case in Architectural Terms
This diagram demonstrates the interaction between the user from the use case and the set of MVC where the user creates an account. The specific MVC in question is the new user sign up.

![UseCase-MVC Diagram](../assets/UseCaseMVC.svg)

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal

I believe switching to a brokered architecture could be quite beneficial here. Since the Serve Central service would need to be receiving information about new events from different organizations in different locations across the country, having this "middle-man" or broker could prove beneficial. The broker could coordinate communication between the main server at Serve Central and the outside parties involved, sending requests to the main server and returning the results of those requests back to the initial party. These third party organizations would be able to send and receive data from Serve Central and still have a high level of security. Since these communications are happening across the country, between Serve Central and four other organizations, the communications would need to be monitored closely to ensure the security of the data. Building organization-specific interfaces should not be an issue since the organization, a local church for example, should be able to receive permission to embed the registration service into their website. They would still need to go through the broker, which would add a bit more complexity to this process, but should still result in the service being available on their website. One downside to this architecture is that all the organizations need to go through the broker, adding in an extra step in communication. This will mean communicatoin will take slightly longer since the broker needs to process all the requests. It would also mean more involvement on Serve Central's side of monitoring communication and general upkeep of the services.   

## Step 3.2 Revised Architecture Diagram
This diagram represents the updated architecture of Serve Central to accomodate four third party organizations to communicate with the Serve Central server. This is a broker architecture which makes use of a broker to act as an intermediary between the organizations and the main server. 

![Broker Architecture Diagram](../assets/Broker%20Architecture.svg)

# Step 4: Scaling an Architecture

Since this service is rather simple overall, a microservice architecture could be implemented and would allow for the development of services to meet the needs of each new requirement along with the existing ones. For example, a service can be developed to allow researchers to examine patterns of volunteer opportunities. Services would need to be implemented to handle the 10k+ new volunteers per hour as well and still keep low latency. Some drawbacks of this architecture would be that the services will take some time to develop and implement. It also might be rather difficult to ensure low latency if too many requests are coming in at the same time. A microservice architecture seems like it should not be too difficult to implement coming from a brokered architecture since microservice already leverages brokered communication to support independent changes. If changes are not made to the brokered architecture, I believe it will have too high of a latency to meet these requirements.