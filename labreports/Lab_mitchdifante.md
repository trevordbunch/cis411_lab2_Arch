# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2023  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Mitch DiFante  
**GitHub Handle:** @mitchdifante  
**Repository:** https://github.com/mitchdifante/cis411_lab2_arch.git
**Collaborators:** N/A
___

# Step 1: Confirm Lab Setup
- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central ... ENTER A BASIC SYSTEM INTRODUCTION HERE.

- Serve Central is an app that allows people to find numerous different volunteer opportunities around their area. The app also allows users to track their total hours served. 

## Step 2.1 Representative Use Cases  

| Use Case #1 | |
|---|---|
| Title | Serve Central within the high school student body. |

| Description / Steps: 

This use case describes how high school students can use Serve Central. 
    1. Students create an account and allow the app to access their location in order to determine their school and where it is located.
    2. Students will browse the various volunteer opportunites offered.
    3. Students complete volunteer opportunites and log them within the app. 


| Primary Actor | Students in high school |

| Preconditions:

1. Students should create an account and volunteer work must be authenticated.
2. Students must list their interests and why they wish to volunteer.
3. Activities must be school approved and bring a benefit to the community in some way.

| Postconditions:

1. Volunteer opportunites must be logged within 24 hours of completion.
2. Teachers and faculty must aid in finding student opportunites in order to place them on the app.

| Use Case #2 | |
|---|---|
| Title | Serve Central within schools nationwide. |

| Description / Steps: 

This use case describes how schools nationwide can use Serve Central to benefit their communities.
    1. Schools who wish to use Serve Central should create an account that students can branch off of.
    2. Schools should create volunteer opportunites for their students and people around the community in order to do good.

| Primary Actor | Schools |

| Preconditions:

1. Schools must put volunteer opportunities up weekly in order to keep users busy and continuing to benefit the community.
2. Schools must create a maximum and minimum number of people for sign ups so opportunites do not get overcrowded.
3. Schools can create the same volunteer opportunity numerous times on different days.
4. Users must sign a terms of agreement before beginning volunteering to prevent harm to others and the school.

| Postconditions:

1. Volunteer opportunites must be approved within a 72 hour time span.

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|

| Map of Activities | User can browse a map of their area and view various opportunites available. | Serve Central allows user to agree to access location and creates a map with numerous different volunteer opportunities available to the user. |
----------
| Volunteer Opportunites | User taps on certain opportunites that they wish to attend and has the ability to sign up with other users around the area. | Serve Central lists out several different options and writes user information to sign them up. |
----------
| Log Hours | User types in number of hours and can see a pie chart depicting their types of volunteering. | Serve Central adds the added hours into the date base to give a complete total number of hours. |
----------
| History Log | User has the ability to view the opportunities they have completed in the past under their statistics. | Serve Central remembers what services were completed and creates a list that users can view. |

## Step 2.3 Diagram a Use Case in Architectural Terms

https://docs.google.com/drawings/d/19QS9mQyzEdBdba2ZeGUt88Wop2GxB38nERei9kKm6Wg/edit?usp=sharing

Here is the diagram for a use case in architectural terms. This contains the user, server, and data base. 

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal

In order to build popularity and receive more information from users. There are numerous possibilities that can be used. One possibiility is by collaborating with larger coportations and companies around the area. Examples of this can be the American Red Cross, Key Club, etc. This will allow for an increase in opportunites around the area, but a downfall of this can be that certain opportunites are only available at certain times which can lead to users not having volunteer opportunites available every day of the week. Another possibility could be that of leaving out devices at volunteer opportunites in order for users to sign in and log their hours. An example of this is the app called Humanity where they take one central device and keep user log-ins available to the user on that device. This allows users to log their hours without any fear of forgetting. However, the reprucussions of this can spike the questions of what happens if the device's data is somehow corrupted, and numerous other possible fears. Finally, Serve Central can use a Load balancer. This would allow for numerous user inputs to enter the system coming from the four volunteer entities and can even create a way for more opportunites to be created. However, this can lead to no single point of failure if something goes wrong. 

## Step 3.2 Revised Architecture Diagram

https://docs.google.com/drawings/d/1DZOEB-Frq1vKK3kFRo6dXpB-xUf2dV6HOjbklJ8SU5o/edit?usp=sharing

Here is a revised version of a network architecture diagram.

# Step 4: Scaling an Architecture

There are a pletora of ways in which these four requirements can be reached. For the first requirement. For the first requirement, a load balancer will be put in place. This will allow for a large amount of volunteer opportunites to be inserted with little latency issues. However, if the load balancer goes down, it will lead to numerous time restrictions and can lead to those requirements not being hit for the day. The second requirement can be reached by a central cloud storage device. This will allow for 50TB of storage to be stored quickly and safely so users do not need to fear losing any progress on their hours volunteering. The only downfall to this form of storage would be that of internet access. If the company in charge of keeping the cloud storage available loses internet connection, users will not be allowed to send their new hours in to log. The third requirement can be completed by allowing bigger companies to have access to the saved data within the database. This will allow queries to be entered and to move through the large amount of data quickly and easily. However, the downfall of this can be that a terms of agreement must go out to all users and this can lead to people declining and leading to troubles with sorting data. Finally, the fourth agreement can be completed by hiring a group of employees to search through and find patterns, that, or produce a code that searches for patterns between users volunteer work and possible grants. However, the code could fail numerous times and lead to possible false claims if not set up properly.