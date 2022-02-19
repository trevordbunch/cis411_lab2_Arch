# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Christian Reames   
**GitHub Handle:** @christianreames    
**Repository:** Your Forked Repository  
**Collaborators:** @richard-pokrivka
___

# Step 1: Confirm Lab Setup
- [Y] I have forked the repository and created my lab report
- [Y] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [Y] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central ... ENTER A BASIC SYSTEM INTRODUCTION HERE (1-2 Sentences).

Serve Central is an application that helps people to find new volunteer opportunities as well as give event and company information so people may find these opportunities and build a network. The app uses React Native and Firebase to create a user-friendly mobile application and uses user statistic tracking to help users.

## Step 2.1 Representative Use Cases  

| Use Case #1 ||
|---|---|
| Title |Send out a mass email to all volunteers|
| Description / Steps | An organization would go into the app and set up an event. The system would have to allow the company to send emails to people who have volunteered before and tell them about the event that's coming up.  |
| Primary Actor | A non-profit organization looking to get volunteers for an upcoming event. |
| Preconditions | The company had to have already put in the event. Also, the company would have had to go in and select the people who've already volunteered with them. |
| Postconditions | The system would send an email to all of the people that were chosen. |

| Use Case #2 ||
|---|---|
| Title |Find places that are relevant to volunteer.|
| Description / Steps | The user would go in and find opportunities that companies have posted near them. The system goes in and lists events for whoever's using the app. |
| Primary Actor | The user/volunteer |
| Preconditions | The volunteer has already made an account and put their information in the system. Also, the user would have to tell the system their location and how far they're willing to travel to go to an event. Also, companies would have to actually put in events for the person to sign up for.|
| Postconditions | The system would show results depending on where the person lives. |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Volunteers | Account Registration Page | Register Account |
| Local Agencies | Event Dashboard | Add an event|
| Types of Service | Company Page | Sign up for event |
| Where services are locally. | Event Registration Page | Follow a company |

## Step 2.3 Diagram a Use Case in Architectural Terms
![Use Case](https://docs.google.com/drawings/d/e/2PACX-1vTM3sKfIrnuV1XrHxY4Y7WRLrx6OoAmYaf3xBMXsJ-79zgfy0nAshml31klgBmjMGlweMKrEmcd8djc/pub?w=960&h=720)



# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal

After an initial release and a few months of operation, Serve Central encounters a tremendous growth opportunity to extend their service and provide a volunteer recruitment and management interface to four of the primary volunteer entities in the United States. As such, a reevaluation of the architecture is required, one that allows:

- Services (most likely 3rd party) that bring data in as well as retrieve it from their database. An example of this could be getting opportunities to volunteer from across the country so that you aren't just limited to local opportunities. 
- Building an interface or many interfaces that are specifically for Serve Central. An example of this is allowing people to register for services in the website of another non-profit group or a church. 

To support these objectives:

I think that an Event-driven architecture would be the way to go. Within an event-driven architecture, Serve Central would be able to build a centralized unit that is able to accept data and then direct it to other modules that could handle the particular type of data (generate an "event"). This would help them handle different environments at a time as data could get chaotic with the development of new interfaces. It also would scale easily as Serve Central continues to grow and create more opportunities than just locally. 


## Step 3.2 Revised Architecture Diagram
![UseCase](https://docs.google.com/drawings/d/e/2PACX-1vQuAmXjdsizf4-3GJwlk93UtEO3SWoebZraraXYsLLARgxEKnMu5W38EqjPf_YOwNyXnulJw3BgnfQM/pub?w=960&h=720)

# Step 4: Scaling an Architecture

The master-slave type of architecture would be a good way to go in order to support the needs of the company as it will help keep the site reliable and can handle a lot of traffic. This is because the master serves as the keeper of the information while the slaves are given the task of reading the data. Each slave is able to do something different but still be able to get the same data from the master. Even though that the event-driven architecture operates in a similar way because of the centralized unit, I still think that the master-slave would have more power and be able to handle more requests because of the larger work load it would have to do. While this could be a good thing, it could also repeated information through the slaves being given the same task which, as a result, would return the same information to the master.


