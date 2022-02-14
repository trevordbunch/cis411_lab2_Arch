# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Ricardo Padilla 
**GitHub Handle:** Ricardoianpadilla  
**Repository:** https://github.com/Ricardoianpadilla/cis411_lab2_arch  
**Collaborators:** al1412 (Adam Lenkdr)
___

# Step 1: Confirm Lab Setup
- [ ] I have forked the repository and created my lab report
- [ ] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [ ] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is a proposal to a mobile application to centralize the application and discovery process of volunteering. This application will simply a complicated process when it comes to finding and signing up for volenteering.

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title |Using ServeCentral to volenteer|
| Description|How to navigate and use SerceCentral to find Volunteering opurtunities|
|Steps|<ul><li>System: App opens with basic welcome page</li><li>User: Clicks the tab for volunteering options represented by 3 line</li><li>System: Displays list of volunteering opurtunities.</li><li>User: Chooces and clickes on a volunteering option</li><li>System: Shows more details about the selected volunteering opurtunity</li><li>User: Clicks sign up.</li><li>System:Shows a confirmation message while sending an email to the user to confirm.</li></ul>  
| Primary Actor |Potental Volunteer |
| Preconditions |An account and local data and location agreement|
| Postconditions |volunteering convirmation email,information about the volunteering such as location and time and date.|

| Use Case #2 ||
|---|---|
| Title |Finding Volunteering History|
| Description |The navigation of the app to find Volunteering History|
|Steps|<ul><li>System: App opens with basic welcome page</li><li>User: Clicks the tab for settings </li><li>System: Displays pie graph of Volunteering History.</li><li>User: Clicks on more details button to see each Volunteering event they were apart of</li><li>System: Shows full list of Volunteering History.</li></ul>
| Primary Actor |User / Volunteer|
| Preconditions |An account and local data,location agreement and past volunteering history through app|
| Postconditions |Volunteering History on system viewing page|

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
|Email Varification | Shows that email has not been verified | User click ingore or verify |
|Location app permission| App ask for location permmisions | User clicks allow oe deny |
|Confirming a Volunteering permission| Show if the user wants to confirm a volunteering position| User clicks confirm or back |
|Log out|Show the user if they are sure they want to logout|user click confirm to logout|

## Step 2.3 Diagram a Use Case in Architectural Terms
![Fork Diagram](cis411_lab2_arch/labreports/2.3 diagram.drawio.png)
# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
Because the process in which a user can get volunteering information is direct, it is appropriate to propose a layered Architecture. This Architecture will create four-layer the User layer, the Presentation layer, the Business layer, and the database layer. The User layer will communicate with the Presentation layer to give the viewer a view of the page which the user can interact with to send a request to the Business layer which the business layer will use preset logic to determine what the request needs and/or if the request meets the logics preset. After the logic decision has been made to complete the request the business layer communicates with the database layer to request data for the presentation layer which it updates.

Pros:
-A volunteering service can send volunteering data Buessnes layer to be processed into the database.
-Simple and fast design
-Volunteering services do not have direct access to the database for security purposes

Con:
-If a layer has an issue the following layer cannot be used by a user.
-Not great with handling large loads

## Step 3.2 Revised Architecture Diagram
![Fork Diagram](cis411_lab2_arch/labreports/3.2 Revised Architecture Diagram.png)

# Step 4: Scaling an Architecture
As the website grows, loads become larger and speed is a priority along with access to data and storage expansion. A flexible and fast data Architecture is needed. This is why I propose The Blackboard Architecture.Because UI interphase is tailored for volunteering only this simplifies the option that the UI haves making it faster and flexible when handling large loads of 10k+ users an hour. Also to further improve large numbers of users a broker can redirect users in a manner that creates faster times.Because blackboards are flexible when it comes to the data store that will quickly exceed 50TB of data we can simply add another database if needed. In addition, when it comes to users accessing statistical values for UI can be created to provide such data without compromising sensitive data. Lastly, when it comes to allowing authorized parties to issue queries to the database. Another UI can be created to simplify the process allowing direct access to the database with restriction of data changes based on rules.

# Extra Credit
If you opt to do extra credit, then include it here.
