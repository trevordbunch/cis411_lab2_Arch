# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Tim Diana
**GitHub Handle:** Tim12-code  
**Repository:** https://github.com/trevordbunch/cis411_lab2_arch.git
**Collaborators:** HallieNicholas, el1303
___

# Step 1: Confirm Lab Setup
- done

# Step 2: Analyze the Proposal
It is a web/mobile application that allows users to find volunteer opportunities around them. It also tracks statistics of volunteering.

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title |As a user, I want to search for local volunteer opportunities so that I can donate my time|
| Description / Steps |User looks for events in the application to attend|
| Primary Actor |User|
| Preconditions |User does not have an event to attend|
| Postconditions |User is signed up for a volunteer event, and is sent confirmation|

| Use Case #2 | |
|---|---|
| Title | As a service agency, i want to find volunteers so that all our service opportunities will have volunteers |
| Description / Steps | service agencies put volunteer opportunity in the app, users find and sign up for event, service agency has volunteers for event |
| Primary Actor | service agency |
| Preconditions | service agency in need of volunteers |
| Postconditions | event has all needed volunteers |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| volunteer event | event list page | event sign up |
| profile | account page | profile signup/in |
| service agency | company about page | click for information |
| location of event | event info page | use gps locating for event |

## Step 2.3 Diagram a Use Case in Architectural Terms
![Use Case Diagram](/assets/2.3diagram.svg)

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Pattern
After the growth opportunity I believe that broker architecture would be most effective for the company. Broker architecture by nature makes service distribution transparent to clients. Which in this case are the volunteer entities. It also supports dynamic CRUD of entities, nodes, and objects. There is added security to accessing the server by adding a broker in between when working with different third-party services. It also helps building different interfaces on top of the Serve Central business and data logic safer going through the broker to the server. The one problem with this system might be the added complexity or possible overhead of the system. The system might run slower because of the security put in place with the broker.

## Step 3.2 Architecture Diagram
![Use Case Diagram](/assets/Part3Diagram.svg)

# Step 4: Scaling an Architecture
Peer to peer architecture will be the best architectural pattern for these new needs. Peer to peer architecture allows for lower latency because of its direct system eliminating middle men. This will allow for instantaneous transmissions of data. There is also a network of data rather than one server so allows for massive data increases. All parties with authorization will be able to access this data on the network and issue queries. With Researchers it would be easier for them to access the data in the network rather than going through the broker to the server. I problem with this system would be the lack of security. In this system cyber-criminals could potentially take data and it would be hard to get that data back or even know that its gone. In a non centralized architecture its hard to manage data as a whole, but there are strategies to combat it.

# Extra Credit
N/A