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

| Model              | View                       | Controller                                                                           |
| ------------------ | -------------------------- | ------------------------------------------------------------------------------------ |
| Users Registered   | Visual string containing   | Upon registartion, add one more user to the registration count for a specific event. |
| Event Details      | Visual Event Display Page  | Upon event creation or event update, modify the changed data values.                 |
| Client Information | Visual Client Display Page | Upon client data creation or update, modify the changed data values.                 |
| User Infromation   | Visual User Display Page   | Upon user data creation or update, modify the changed data values.                  |

## Step 2.3 Diagram a Use Case in Architectural Terms

![User Registration, Use Case #1](../assets/User%20Registration%20Form%20Dia.pdf)

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal

INSERT Architectural change proposal here, and how it meets the two new requirements.  Explain both the benefits and draw backs of your proposal.

## Step 3.2 Revised Architecture Diagram

INSERT IMAGE HERE with a Description.

# Step 4: Scaling an Architecture

INSERT Architectural change proposal here, and how it meets the four new requirements.  Explain both the benefits and draw backs of your proposal.  If the changes are significant, then you need to explain why the changes are necessary versus a nice-to-have enhancement.

<!-- # Extra Credit

If you opt to do extra credit, then include it here. -->
