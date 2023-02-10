# Lab Report: Architecture
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Shane Wahlberg  
**GitHub Handle:** CuriousOcean 
**Repository:**(https://github.com/CuriousOcean/cis411_lab2_arch)

**Collaborators:** 
___

# Step 1: Confirm Lab Setup
- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
**Server Central Description**: Severe Central is a moblie app that allows users to quickly find events that are in need of volunteers. On the app, users can see how far, what kind of event, what kind of volunteers are needed, and they can keep track of what kind of work they've done and for how long. 

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title | Service Agency - Posting a Volunteer Listing |
| Description / Steps | As a service agency, I want to post my service event so that potential voluneeters can see my event and help<ol> <li> Owner of Service agency navigates to app and clicks on "Post Event" </li><li> User fills out information pertaining to event, such as how many people are needed and what kind of work is expected. </li> <li> User clicks post and the event is posted <ul> |
| Primary Actor | Service Agency |
| Preconditions | <ol> <li> Account Created for User</li> <li> There are users nearby that see the event  |
| Postconditions | User is informed about who is volunteering and reserves the right to decline their services  |

| Use Case #2 | |
|---|---|
| Title | Volunteer - Signing Up for Volunteer Listing |
| Description / Steps | I want to sign up for events to volunteer. <ol> <li> User navigates to "Map" feature </li> <li> Nearby volunteer opportunities are displayed, showing the distance from their location to the event. </li> <li> User click on the icon and is displayed what type of event, what kind of services, and how many more volunteers are need. </li> <li> After reading, the user has the option of clicking the "Sign me Up!" button or going back to select a different event. </li>  |
| Primary Actor |Volunteer |
| Preconditions | There are nearby events looking for volunteers.  |
| Postconditions | User is emailed a reminder about the event so they do not forget.  |

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Profile | Sign in Page | Email users reminder about event signed up for |
| Map | Map with Nearby Events | Notify service provider who has volunteered |
| Event | Profile for volunteer and service | Take down volunteer option once event has filled up |
| Email | Post a event tab | Tell volunteer profile the amount of hours and what type of events they have volunteered for overall |

## Step 2.3 Diagram a Use Case in Architectural Terms
![assets](../assets/UseCase.drawio.png)

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
I believe that implementing the Microservice Architecture would meet the desired requirements. It's ability to leverage brokered communication would allow it to support adding third party services and connecting to other websites like churches or nonprofits. However, the recombination of all the layers could be time-consuming and difficult. 

## Step 3.2 Revised Architecture Diagram
![assets](../assets/microservice.drawio.png)
New Use-Case Diagram

# Step 4: Scaling an Architecture
Upon reviewing the new requirements to qualify for the Gates Foundation grant, I still believe that the Microservice architecture still best architecture to follow. It's scalability and ability to break the system down into smaller services would allow it to handle more users and process data faster. We can add more services with ease if the grant requirements changed or if Serve Central decides to implement more services down the road. 

However, the bigger the app and the more you scale it down, the more complex it becomes. Using Microservice runs the risk of getting lost in streams of data and connections. 

# Extra Credit
For step 2.1, clarification on how to list within a table would benefit students. Below is sample instructions

*To list within the table, type the following:*
```
ol> <li> text </li><li> text </li> <li> text <ul
```
If done correctly, you should get an output like this:
<ol> <li> text </li><li> text </li> <li> text <ul
