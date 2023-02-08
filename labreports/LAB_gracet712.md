# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2023  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Grace Taylor  
**GitHub Handle:** gracet712 
**Repository:** https://github.com/gracet712/cis411_lab2_arch 
**Collaborators:** 
___

# Step 1: Confirm Lab Setup
- [X] I have forked the repository and created my lab report
- [X] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [X] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is an app designed to offer information about and registration for volunteer events in a single, centralized location. It also provides statistics for volunteers regarding past events they participated in.

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title |Event Registration - Volunteer |
| Description / Steps |1. The user navigates to the Event List webpage and selects an event.<br/> 2. The user selects ```Register for Event```.<br/>3. The user submits a form containing additional fields the Service Agency requires that are not already associated with the user's account.<br/> 4. The form validates that all required fields are filled.<br/>5. An email is sent to the Service Agency informing them of the new volunteer.<br/>6. The web page generates confirmation that the user is registered for the event and sends the user a confirmation email. <br/>7. The user is redirected to the home page. |
| Primary Actor |Volunteer |
| Preconditions |1. The user has an account. <br/> 2. The user is logged in. |
| Postconditions |1. The user is registered for the event in Service Central's systems.<br/>2. The user receives a confirmation email regarding their registration.<br/>3.The Service Agency associated with the event receives an email informing them of the user's registration. |

| Use Case #2 | |
|---|---|
| Title |Create Eent - Service Agency |
| Description / Steps |1. The user selects ```Create Event``` on their home page.<br/>2. The user completes an Event Creation form (event title, category, date, time, location, description, max number of volunteers, registration cutoff date, and additional information required from volunteers).<br/>3. The form validates that all required fields (title, date/time/location, max number volunteers) is filled out.<br/>4. The webpage confirms that the event has been created, and a confirmation email is sent to the user.<br/>5. The user is redirected to their home page. |
| Primary Actor |Service Agency |
| Preconditions |1. The Service Agency has an account.<br/>2. The Service Agency is logged in. |
| Postconditions |1. The new event is created in Service Central's systems and displayed to users (volunteers) who enter appropriate search criteria.<br/>2. The Service Agency receives a confirmation email regarding the event's creation. |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Databse of events (contains information such as event title, cateogry, location, date/time, max # volunteers, required volunteer information, registration cutoff date, description, associated Service Agency, etc.) |Event List Webpage (accepts search criteria and displays list of events to users)  |Processes input search criteria (ex: location, category, date, etc.) and returns a list of events that match those criteria  |
|Database of Volunteer accounts (contains information such as names, email, password hash, event registration, etc.)  |Sign-up / Login Webpages for Volunteers  |For sign-up: Processes input data on sign-up form, validates it, and adds to the database; returns confirmation<br/><br/>For login: Processes input email and password, finds account in database, and initiates session  |
|Database of Service Agency accounts (contains information such as name, contact name, email, password hash, etc.)  |Sign-up / Login Wepages for Service Agencies  |For sign-up: Processes input data on sign-up form, validates it, and adds to the database; returns confirmation<br/><br/>For login: Processes input email and password, finds account in database, and initiates session  |
|Statistics Database - contains aggregated information on all Volunteers' and Service Agencies' completed events |Wepage displays overall statistics for Service Center's users  |Runs predefined queries on the database and returns graphics for wepage to display  |

## Step 2.3 Diagram a Use Case in Architectural Terms

![Use Case for Volunteer Viewing Event List](/assets/Use_Case_Architectural_Terms.jpg)

**Description:**

The above diagram shows the interaction between an actor (volunteer) and the models, view, and controller necessary to allow the user to view an appropriate list of volunteer events. In 8 steps, it demonstrates how the user inputs search criteria on a webpage (view) which are then processed by a controller. The controller queries the database (model) for appropriate events and returns a list to the view, which displays them for the user.

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
INSERT Architectural change proposal here, and how it meets the two new requirements.  Explain both the benefits and draw backs of your proposal.

One architectural pattern that would help meet these two new requirements is the load balancing architecture model. This supports the first new requirement by providing a way to support a large number of users, as third-party services input and retrieve large volumes of data and many more volunteers begin using the service. The second requirement can be supported by designing the load balancing architecture model in such a way that the web interface can be embedded in another website and still securely send user input back to Service Center's servers. A drawback is the expensive infrastructure required to maintain a load balancing model and the complex requirements to make sure the main/helper databases and replicated web servers are always synced.

## Step 3.2 Revised Architecture Diagram
![Revised Architecture Diagram - load balancing](/assets/lab2_architecture_diagram.jpg)

**Description:**

The above diagram presents a load-balancing architecture that would help support the requirement for third-party services to input and retrieve large volumes of data, as well as increased usage from volunteers. It also demonstrates how certain components, such as the form for registratration services, could be isolated to allow it to be embedded in other websites. In this diagram, both the web servers and databases are replicated to allow for load balancing.



# Step 4: Scaling an Architecture
INSERT Architectural change proposal here, and how it meets the four new requirements.  Explain both the benefits and draw backs of your proposal.  If the changes are significant, then you need to explain why the changes are necessary versus a nice-to-have enhancement.

# Extra Credit
If you opt to do extra credit, then include it here.