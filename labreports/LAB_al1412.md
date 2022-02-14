# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Adam Lenker    
**GitHub Handle:** @al1412  
**Repository:** https://github.com/al1412/cis411_lab2_arch  
**Collaborators:** Ricardo Padilla (@ricardoianpadilla)    
___

# Step 1: Confirm Lab Setup
- [X] I have forked the repository and created my lab report
- [X] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [X] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central helps its users to find volunteer work through a mobile application, with all registration for a volunteer position being done on one application as opposed to the long and often inconsistent registration process most volunteer positions have. Additionally, Serve Central provides a map of volunteer work that is nearby to the user, as well as how far each one is relative to their current location, and a description of each activity, making it easier for the user to narrow down their options for the work they wish to pursue.    

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title | Opening Serve Central app for the first time |
| Description / Steps | <ul><li> The user first sees the welcome page, then should click the sign up button on the page.</li><li> The user sees the sign up page, in which they fill out information such as their name, email address, and password. </li><li> After this, the user should click the submit button at the bottom of the page, which leads them to a confirmation page confirming that the information has been sent. </li><li> After getting to the confirmation page, the user should check their email for a confirmation message, then click the link in that email to log into Serve Central. </li><li> After logging in, the user should be directed to the main page of the Serve Central website for the location which they are volunteering at. </li></ul> |
| Primary Actor | Volunteer |
| Preconditions | Have an account through Serve Central, have location feature enabled |
| Postconditions | User gets confirmation email, information is sent to registar upon completion of application, the app is updates the number of volunteers at a location |

| Use Case #2 | |
|---|---|
| Title | View volunteering history |
| Description / Steps | The user clicks the profile option at the bottom menu of the app, then clicks on the "Volunteer History" section of the profile page to view the amount of volunteer positions they have had, as well as how many hours they worked for each one. |
| Primary Actor | Volunteer |
| Preconditions | Have an account through Serve Central, have volunteer positions secured through Serve Central |
| Postconditions | User gets a detailed history of all volunteer positions which they have gotten through Serve Central |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Email not verified | Displays a message telling the user to update their email | Checks if user has updated/verified their email |
| Location share not granted | Displays a message telling the user to allow location permissions | Checks if user has allowed location permissions |
| Confirm a volunteer position | Displays a message asking the user if they want to go through with a volunteer position they applied for | Checks if user has accepted the offer |
| Log out | Displays a message asking the user if they are sure they want to log out after clicking the log out button | Checks if the user really wants to log out of Serve Central or not |

## Step 2.3 Diagram a Use Case in Architectural Terms
![2 3 diagram drawio (1)](https://user-images.githubusercontent.com/97567307/153784356-c4e5be6f-f658-434b-89a3-f517d591fc16.png)


# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
Since the process in which a user can get volunteering information is direct, a layered architecture is the best option for this application. The layered architecture will create four layers: the User layer, the Presentation layer, the Business layer, and the Database layer. The User layer communicates with the Presentation layer to give a view of the page which the user can interact with to send a request to the Business layer. This is what the Business layer will use preset logic to determine what the request needs and/or if the request meets the logics preset. After the logic decision has been made to complete the request, the Business layer communicates with the Database layer to request data for the presentation layer which it updates.    

Pros:    
* A volunteering service can send volunteering data to be processed into the database    
* Simple and fast design    
* Volunteering services do not have direct access to the database for security purposes    

Cons:    
* If a layer has an issue, then the following layer cannot be used by the user     
* Not great with handling large loads of data    

## Step 3.2 Revised Architecture Diagram
![3 2 Revised Architecture Diagram drawio](https://user-images.githubusercontent.com/97567307/153790538-b6a934ab-542f-40f6-9e9b-e712ebfe6a6f.png)


# Step 4: Scaling an Architecture
As the website grows, loads become larger, and speed is a priority along with access to data and storage expansion. As a result, a flexible and fast data architecture is needed, which is why we propose the blackboard architecture.    

Because the user interface (UI) is tailored for volunteering only, this simplifies the option that the UI has making it faster and flexible when handling large loads of 10,000 or more users an hour. To further improve large numbers of users, a broker can redirect users in a manner that creates faster times.    

Because blackboards are flexible when it comes to the data store that will quickly exceed 50TB of data, we can simply add another database if needed. In addition, when it comes to users accessing statistics, statistical values for UI can be created to provide such data without compromising sensitive data. Lastly, when it comes to allowing authorized parties to issue queries to the database, another UI can be created to simplify the process, which allows direct access to the database with restriction of data changes based on the rules.    

# Extra Credit
If you opt to do extra credit, then include it here.
