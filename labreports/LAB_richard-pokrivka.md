# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Richard Pokrivka  
**GitHub Handle:** richard-pokrivka  
**Repository:** https://github.com/richard-pokrivka/cis411_lab2_arch.git  
**Collaborators:**
Cmcculler1
kfirestone25
___

# Step 1: Confirm Lab Setup
- [X] I have forked the repository and created my lab report
- [X] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [X] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
The percentage of US volunteers from 2002-2014 drastically fell with the primary reasons being finding new opportunities being difficult and registration processes being inconsistent and confusing. ServeCentral serves to remedy that by creating a product that makes registration in one simple application and lets the user use a friendly mobile app that can store organization's information. 
## Step 2.1 Representative Use Cases  

| Use Case #1 |Volunteers|
|---|---|
| Title |Signing up and Finding Service Opportunities Made Easy|
| Description / Steps |The prospective volunteer first signs up and creates an account. Then, the volunteer can search for an event by name or type or can look at the map and look at local organizations.|
| Primary Actor |Volunteers|
| Preconditions | User must submit to a background check upon account creation. (Note: User may be subject to addition background checks and clearances depending on state laws and volunteer areas). The volunteer event application is within the ServeCentral app. A new application is submitted for different organizations|
| Postconditions | The application gets stored in the cloud until the agency looks at it.  |

| Use Case #2 | Organizations |
|---|---|
| Title | Obtain applications for volunteer work |
| Description / Steps |Each organization has their own authenticated account. These accounts can access applications and post details about events including dates, times, type of work, and number of volunteers needed. The organization can describe additional requirements if neccessary for the work. Upon, deciding or denying candidates, rejection or acceptance notifications are sent out.|
| Primary Actor |Service Agencies|
| Preconditions |The organization has an account that has access to all of the applications submitted. Notice of confirmation for successful background checks recieved by the organization account|
| Postconditions |Agency notifies the user if the application for service opportunity was rejected or accepted. If application is accepted, agency sends out an iteniary along with other volunteering details via email to the volunteer.|

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
| Agencies | Organizations in an area | Submit button for applications |
| Volunteers | Organizations that work with animals | Search bar |
| Location of Services | Open positions for acencies | Refresh button  |
| Service Categories | List of applicants | Button to open list of agencies/volunteers |

## Step 2.3 Diagram a Use Case in Architectural Terms
![MVC Diagram](https://docs.google.com/drawings/d/e/2PACX-1vQvT_A1TLuMr0RkoMfti673tYVo8G_b0zHqpn_D8yRY39IlFE2yaUPcuvNJuV8YGXlmKXt5uQ9-Sqbt/pub?w=1365&h=720)
For this diagram, the view component would be the user wanting to know a list of organizations that do service work with animals. This would be done through a search bar which is the controller which would run code that searches a service categories database which is the model for the key word animals. The list would be retrieved from the database and then shown back to the user as an easy to understand list.

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
The architecture pattern that would appropiately and adequately cover the new requirements would be client-server. 
A benefit for the Thirdparty services would be the capability to input and retrieve data from a centralized server via the internet which allows access from everywhere. Accessibility is another benefit because every client is provided with the opportunity to log into the system. Organization-specific interfaces would be created because third-party services already have access to the data via a centralized server and could easily be connected through the centrally controlled shared data. One drawback to using the client-server architecture would be if the server were to crash the data would be inacessable until restored unless a local copy was on clients hardware and reliability if the server receives a lot of traffic.

## Step 3.2 Revised Architecture Diagram
![Client Server](https://docs.google.com/drawings/d/e/2PACX-1vSD0DYT0pUVsMm2RhQPSuOu2v-iSPuojJWcgrLjdzNOpf1PlqgqLLXqrE2d1OgrkYPbRtJ5AjpcvqJH/pub?w=960&h=720)
The diagram illustrates how the information is accessed via the internet and a server. This method prevents the need for localized access to the data and can be accessed by many different clients or users at once and from anywhere. If the connection is broken, there would be no centralized way to access the server.
# Step 4: Scaling an Architecture
The architectural pattern that will be employed to support the four new needs ServeCentral has to resolve is Blackboard. The benefits of Blackboard include its ability to manage and utilize large multi-faceted data sets and storage of that data. Its multi-component architecture and flexibility contributes to its ability to manage massive amounts of data and quickly. This remedies the latency issue when presented when massive amounts of data uploaded, allows parties to manage and traverse the massive amount of data it can store, and handles the four requirements. One consquence of Blackboard is the difficulty of testing and it is difficult to establish good control. The changes are neccessary because client-server is not suited to large projects with massive amounts of data and Blackboard is suited to large scale and not small scale. These requirements would far surpass the small scale that client-server could easily handle.
