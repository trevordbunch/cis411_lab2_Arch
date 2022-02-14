**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Gloria Houngbeke
**GitHub Handle:** GlorKemH
**Repository:** GlorKemH/ cis411_lab2_arch
**Collaborators:**  ryandonat & issachhm
___

# Step 1: Confirm Lab Setup
- [X ] I have forked the repository and created my lab report
- [X ] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [ X] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central ... ENTER A BASIC SYSTEM INTRODUCTION HERE (1-2 Sentences).

Serve central stores and keep user's information while maintianing location based help to assit user's in their desired area. Serve central store user's data in a friendly way and applies to the application a user is using, so nothing will ever be confusing and lost.

## Step 2.1 Representative Use Cases  

| Use Case #1 | |

Title: Rake Leaves
Description / Steps:

On Friday morning the volunteers must arrive at the destined location 15 minutes before the start time. The volunteers split in twio groups. The first group goes to the back yard. The second group goes the front yard. Each group rakes the fallen leaves. The each group baggs the leaves. The bagged leaves are then tossed.

Primary Actor: Volunteers
Preconditions: It is friday

Postconditions: There are leaves on in the yards.

| Use Case #2 | |

Title: System sign up
Description / Steps:

User with their personal devide must in their homes. The user will search for "help.org". Once the user has accessed the site. The site will prompt user to create an account. The user will click on the option and follow the step to creat and account. The user will put personal information within the system. Once the user is done they will submit their information. The system will store the user's information for future use.

Primary Actor: The system

Preconditions: The user with their own device

Postconditions: "Help.org" needs a users information to operate

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
|The service in events in the database  | event page | user's are able to sign up for events |
|user's account |  the login/ sign up page| Section for storing password and user information  |
|reporting function| Information on the listed events | reports of event listed in our system |
| Data receiving | recorded data from outside source | storing the data apropriately | 

## Step 2.3 Diagram a Use Case in Architectural Terms

![Use case picture](../assets/Architecture%20Drawing.svg)
This diagram is a representation of the volunteers and the overall steps taken to make an account, search for events. The volunteer would create and account then the system will save the users information. Once the user signs up the will have the option to search for events, create/host events. The provider's are able to see who create and host an event and record it in their database while also creating events and notifying the user. 

![mv picture](../assets/Mv.svg)
This is a diagram of mv about the user interaction. The user would login then the system would store their information and utilize it when it is needed.
# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
INSERT Architectural change proposal here, and how it meets the two new requirements.  Explain both the benefits and draw backs of your proposal.

I would like to expand the server central so that it is not only a local service but an international/ cross country service. I would incoparate strong security within the system to strenghen it so that when it is expanded it will not be suceptable to attacks and bugs. The system would record the data and store them in an easily accesible place. The benefits of the expanded system is that it would allow the services to reach more people and expand and gain more data. A downfall for this system is if it is not excecuted properly it would crash and many vulmerabilities and attacks could enter the system. 


## Step 3.2 Revised Architecture Diagram

![step 3](../assets/3%20Diagram.drawio.svg)


# Step 4: Scaling an Architecture

 I believe peer to peer architecture would be best. PTP architecture allows for equal control throughout the system. This is very convinient if we had over one thousand user trying to enter the system. Peer to peer is beneficial for this becuase of the lack of a central server. This will eliminate the middle man and process time. There is also a lot of data in the system which would be better of distrubuted. Anyone would be able to access this data. Researchers would additionally be able to make future predictions and investments based on what they see. This change would be necessary because with the other architecture pattern there is a more wait time due to the middle component. In order for outside sources such as researchers to look inside our database and make predictions, it would need to be an open-source and easily accessible through more means. An  issue that might occur is that there would be some difficulties to backup all the spread out data because it is not on a centralized server. If something were to happen and data was lost, it would be extremely hard to get it back. Security is also an issue in a decentralized environment such as this due to the fact that all the nodes would have access to the data. This would create a risky security field for the open access system.






# Extra Credit
If you opt to do extra credit, then include it here.