# Lab Report: Architecture

---

**Course:** CIS 411, Spring 2023  
**Instructor:** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Jonah Robinson  
**GitHub Handle:** [jrmakr2123](https://github.com/jrmakr2123)  
**Repository:** [https://github.com/jrmakr2123/cis411_lab2_arch](https://github.com/jrmakr2123/cis411_lab2_arch)  

<!-- **Collaborators:** someone else -->

---

# Step 1: Confirm Lab Setup

- [X] I have forked the repository and created my lab report
- [X] I have reviewed the [lecture / discussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.

<!-- - [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators. -->

# Step 2: Analyze the Proposal

Serve Central is a volunteering signup hub. By using Serve Central, the user can become more aware of and register for volunteering events in their area. For clients using Serve Central, user statistics and registration will be taken care of in a singular location.

## Step 2.1 Representative Use Cases

| Use Case #1         | |
| ------------------- | ---------------------------- |
| Title               | Register for an Event - User |
| Description / Steps | As a Serve Central user, I want to volunteer for an event in my area. (:D)<br /><br />1. The user navigates to the Serve Central homepage and clicks ``Find Events Near You!``.<br />2. If the user is not already logged in, the website changes to the login page. Otherwise, the page changes to a map with several volunteering events and their locations.<br />2a. After inputting the proper user credentials (username and password), page changes to a map with several volunteering events and their locations. <br />3. The user selects which volunteering event they are interested in and the page changes to a registration form.<br />4. After the user confirms their name, birth date, email address, and home address, an email will be sent to the user with a copy of the instructions provided.<br />Congratulations, you have just registered for a volunteering event. |
| Primary Actor       | User / Volunteer |
| Preconditions       | Must have a user login. |
| Postconditions      | 1. The volunteering event organizers are notified that another user registered for their event.<br />2. The number of volunteers registers increases by 1 on the Serve Central site.<br />3. The user receives an email containing registration and event information. |

| Use Case #2         |                              |
| ------------------- | ----------------------------|
| Title               | Event Registration - Client|
| Description / Steps | As a Serve Central Client, I want to register my volunteering event.<br /><br />1. The client navigates to the Serve Central homepage and clicks ``Register an Event!``.<br />2. If the client is not already logged in, the website changes to the client login page. Otherwise, the page changes to an *Event Registration Form*.<br />2a. After inputting the proper client credentials (organization name, username, password), the page changes to an *Event Registration Form*.<br />3. The client fills out the *Event Registration Form* by verifying the following . . .<br />     organization name, address, and contact credentials,<br />     event title (as in event name), description, requirements, location,<br />     event director contact credential (if they are different from the organizations contact credentials),  <br />     any other information that seems useful to the user<br />4. The client summits the digital *Event Registration Form* by clicking ``Submit``and receives an email confirming the submission.<br />5. The client will be redirected to the client homepage that includes past, current, and pending volunteer events. |
| <br />Primary Actor | Client / Service Agencies / Volunteer Organizer |
| Preconditions       | Must be a registered client.<br />Must have an event able to be registered. |
| Postconditions      | 1. Serve Central's client homepage must update to show that a new event was added.<br />2. The client receives and email concerning the event registration submission |

## Step 2.2 Define the MVC Components

| Model              | View                       |   Controller         |
| ------------------ | -------------------------- | -------------------- |
| Users Registered   | Visual string containing   | Upon registration, add one more user to the registration count for a specific event.                                              |
| Event Details      | Visual Event Display Page  | Upon event creation or event update, modify the changed data values.                                                                  |
| Client Information | Visual Client Display Page | Upon client data creation or update, modify the changed data values.                                                                  |
| User Information   | Visual User Display Page   | Upon user data creation or update, modify the changed data values.                                                                  |

## Step 2.3 Diagram a Use Case in Architectural Terms

![User Registration, Use Case #1](../assets/User%20Registration%20Form%20Dia.jpg)
This diagram shows a simplified edition of Use Case #1. The user sees the homepage, makes the request to register to change the page, and then the information is collected and displayed. This process continues until the user completely registers for the event they are interested in. 
# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal

The architecture of Serve Central, to accompany the new changes to the overall structure, would need to change. I am proposing a change to the Broker architecture. Where before, the users, clients, and possible apis would need to go to the website, view the information directly, and supply commands to change the outcome of the request, the broker architecture provides a complex central structure for different uses. If a user is interfacing with Serve Central's website, the only information they generally need to know is the event data. The clients interfacing with Serve Central would need to know and change the event data and their client information. Now with the introduction of third party apis, the information needs to become more flexible and autonomous.

The benefit of changing to a broker architecture.
- Clients, third party apis, and users can access the information that is pertinent to their use case. 
- All the information can still be stored in a central location. 
- Information is better controlled for each individual use case such that apis get certain information rather than receiving and deciphering an entire web page. 
- Broker architectures provide a better experience for larger use cases with more information and more requests. 

The disadvantage of changing to a broker architecture.
- Broker architectures are difficult to set up especially for projects concerning smaller issues. 
- Broker architectures require careful tunning and configuration.
- Apis need to be adjusted to suit a broker architecture (although that would have happened anyway).

## Step 3.2 Revised Architecture Diagram

![Broker architecture](../assets/broker%20architechture.jpg)

# Step 4: Scaling an Architecture

For the new implementation supplied graciously by the Gates Foundation, I would implement the Microservice architecture. Since we are adding criteria to the the original Serve Central implementation, there are only a few architectures that are able to support the requirements. A microservice architecture has the benefit of the broker architecture wile also attaining the ability to scale rapidly. Furthermore, the microservice architecture can be expanded to support a large scale operation. For programs that are all over the world, the application architecture will be stored in multiple locations. Having a microservice architecture, this task is simple and makes the user, client, and third party's jobs easier. 

Benefits to the microservice architecture.
- Replaces the centralized framework for decentralized amoebous framework (this is mainly for tasks that are worldwide).
- Makes the application capable of processing Terabytes of requests at a given time from anywhere on the globe (internet depending). 
- It is easier to change a part or issue a fix if a problem is encountered with the application framework. 

Disadvantages to the microservice architecture. 
- The expanded nature of the application framework makes updating the whole application more difficult. 
- A ton of data will need to be used.

Overall, the benefits outweigh the disadvantage of the microservice architecture. Since the amount of storage the application will be dealing with is massive, the expansion of the application framework will need to be equally as large. By using the microservice architecture and spreading the bearing of the application over a larger scale, more information and ata can be moved efficiently.

<!-- # Extra Credit

If you opt to do extra credit, then include it here. -->
