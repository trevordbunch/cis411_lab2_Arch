# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Your Name  
**GitHub Handle:** Your GitHub Handle  
**Repository:** Your Forked Repository  
**Collaborators:** 
___

# Step 1: Confirm Lab Setup
- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is a web and mobile app that allows users to find and register for service opportunities. The app will track user statistics and use Firebase and React Native. 

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title |Costumer creates account|
| Description / Steps | 
||Costumer opens app|
||System displays sign up button and login button|
||Costumer taps sign up
||System displays boxes to input name, password, and location
||Costumer inputs name, password, and location
||Name, password, and location are recorded
||Customer is redirected to their new home page
| Primary Actor |Customer|
| Preconditions ||
||First time app is being used or no sign in cookies on website
||Application server is running
| Postconditions |
||Customer's username and password are stored in database
||Location recorded in database and is used to give possible service opportunities in area

| Use Case #2 | |
|---|---|
| Title |Service agency creating event|
| Description / Steps | |
|| Service agency opens app
||System prompts with a login or sign up. 
||Service agency user presses login
||System displays input boxes for username and password
||User inputs username and password
||System redirects user to their home page
||User presses "create new event" which is displayed on screen
||User is prompted to input events description, location, and other relevant info. 
||User inputs data
||Data is set to database and the event is posted
| Primary Actor | Service agency user|
| Preconditions|
||Agency already has a registered account
| Postconditions | |
||A notification is sent out to all users within a locational range of the event

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
|Server|User's app GUI|User's app GUI|
|Database|Web app html/css file|Web app html file|
|Computer/App hardware|Direct server UI|Direct server UI|
|Database server|direct database UI|Direct database UI|

## Step 2.3 Diagram a Use Case in Architectural Terms
![Use Case](\../assets\UseCase.svg)
The web app html sends display info via a GUI to the user. The user sends input info back to the web app. Sends the input to the server. The server sends a data request to the database. The database sends data which is then converted by the server and sent to the web app. The web app then displays the info. 

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
I propose a Client sever architecture. 
This architecture will allow for a single collection of data in a single datastore which will allow third party services to easily input and receive data from the entire database. The Organization specific interfaces can also be simply added to the server. 
The main issue this architecture would present would be scalability. If the organization is growing swiftly then it may be hard to keep up with demand. 



## Step 3.2 Revised Architecture Diagram
![Architecture Revised](\../assets/ArchRevised.svg)
The users provide information or requests for data to the main or organization specific interfaces. Those interfaces send requests for data or data itself to the server. The server sends data and requests to the database. After receiving the data back, the server then sends that info back to the interfaces. 
# Step 4: Scaling an Architecture
Because we already have an ingrained client-server based architecture, we will continue with that strategy but switch to a XaaS model.  
We outsource our hardware (servers, storage space, etc.) to a cloud based provider. This will let us essentially keep our current architecture while allowing for close to infinite scalability in terms of storage and speed.  
Our system was already reliant on an internet connection, so moving everything online will not change our availability.  
The cloud based storage system and amount of servers can automatically scale to our current needs to match the bursts of volunteer opportunities and many TB's of data.
The largest issue will be finding a provider and navigating the complexities of a XaaS system.  

# Extra Credit
If you opt to do extra credit, then include it here.