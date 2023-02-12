# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2023  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Nason Allen  
**GitHub Handle:** 02NRA  
**Repository:** https://github.com/02NRA/cis411_lab2_arch  
**Collaborators:** Aidan Hubley
___

# Step 1: Confirm Lab Setup
- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Due to various factors (human error, lack of centralization, etc.), it can be difficult to find service opportunities. Serve central is a mobile app that seeks to solve this issue using maps, Firebase, React Native, and more.

## Step 2.1 Representative Use Cases  

| Use Case #1    |                                                                                                                                                                                                               |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Title          | User Viewing Activities                                                                                                                                                                                       |
| Description    | **As an individual user, I want to be able to sign up to volunteer at an event, so that the hosting organization knows how much more help they need.**                                                        |
| Steps          | 1. Search for an event, or choose an event from the home page.<br>2. Choose a time slot, if there are more than one offered.<br>3. Click the "Sign Up" button.                                                |
| Primary Actor  | Individual User (not an organization)                                                                                                                                                                         |
| Preconditions  | 1. The user must have an account.<br>2. The user must be signed into his or her account.                                                                                                                      |
| Postconditions | 1. The user will now get a push notification reminder when the event that they signed up for is about the begin.<br>2. The user is listed as a volunteer, visible to the organization that created the event. |

| Use Case #2 |                                                                                                                                                                                                                                                                                    |
|-------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Title       | Delete a User Account                                                                                                                                                                                                                                                              |
| Description | **As an administrator, I want to be able to delete a user account, so there is some force behind our policies.**                                                                                                                                                                   |
| Steps       | 1. The administrative user must navigate to the "Find User" menu.<br>2. The administrative user must click the "Delete Account" button next to the user's name.<br>3. The administrative user must fill out a report form with the reasoning for why the user account was deleted. |
| Primary Actor | Administrative User                                                                                                                                                                                                                                                                |
| Preconditions | 1. An administrative user must have an account.<br>2. The administrative user must be logged into his or her account.<br>                                                                                                                                                          |
| Postconditions | 1. The user account is inaccessable to its user.<br>2. The account in question can be recovered by filling and having approved an appeal form.<br>3. The deleted user is unlisted from any event that they were signed up to colunteer at.                                         |

## Step 2.2 Define the MVC Components

| Model        | View                    | Controller                       |
|--------------|-------------------------|----------------------------------|
| Profile      | User Info Page          | View, Edit, Delete               |
| Event        | Event Page              | View, Sign Up For, Inquire About |
| Organization | Organization Cover Page | View, Edit, Follow, Join         |
| Reminder     | Upcoming Page           | View, Set                        |

## Step 2.3 Diagram a Use Case in Architectural Terms

![MVC Diagram](assets/MVC_Diagram.png "MVC Diagram")

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
A client-server architecture would be best in this situation. It would be very difficult to ensure a good end user experience by properly translating the third party tools that we are now concerned with. In a peer-to-peer relationship, for example, this would be an issue, but not with a client-server relationship.

This structure would also allow any changes to the app to be deployed quickly and simultaniously.

A potential problem with this decision is that volunteering opportunities may have very specific time windows, which does not allow a margin time for a server to be down for service and in case of attack.

## Step 3.2 Revised Architecture Diagram
![Client-Server Diagram](assets/Client-Server_Model.jpg "Client-Server Diagram")

# Step 4: Scaling an Architecture
A single server, as was proposed in Step 3, could quickly be overwhelmed with high traffic, so it would be best to switch to a brokered relationship. The primary drawback of a brokered connection is the overhead expense for small projects, which is the opposite of the expressed problem in this case.

In this new model, the system can assign user sessions to different servers, which addresses our user speed and volume concerns.

The different servers also allow for more data storage, and faster access to that storage. The storage can be synced such that the broker does not need to be called every time data was needed (i.e. a user could not be "assigned to the wrong server).

Instead of tracking the inputs and outputs of a multitude of different servers, a researcher can see patterns and draw conclusions from the broker, and where its metadata is stored.

# Extra Credit
In "Doing the Lab", it is said that one "wheres" many hats, and it should be "wears" many hats.

In LAB_INSTRUCTIONS, "Thirdparty" should be "Third party". I would also suggest removing the comma after "100k daily"