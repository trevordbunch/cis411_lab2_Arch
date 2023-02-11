# Lab Report: Lab Architechture
___
**Course:** CIS 411, Spring 2023  

**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  

**Name:** Xavier Zepiora

**GitHub Handle:** xzepiora

**Repository:** [Your Forked Repository](https://github.com/xzepiora/cis411_lab2_arch)

**Collaborators:** Ray Truex - rt1252
___

# Step 1: Confirm Lab Setup
- [x] I have forked the repository and created my lab report
- [x] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [x] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central's app makes it quick and easy for volunteers to get connected with organizations to make a difference in their communities all from one location.

## Step 2.1 Representative Use Cases  

| Use Case #1 ||
|---|---|
| Title |Volunteer Registers for Event|
| Description / Steps | The volunteer finds an event that they want to register for. Then they click the register button. The volunteer then has to fill out the registration form with the required information. The application then confirms that the volunteer wants to sign up. The volunteer is then redirected to their events page which shows them all the events they have signed up for. |
| Primary Actor |Volunteer |
| Preconditions |1: The volunteer is signed into their account. 2: The volunteer is eligible for the event. 3: The volunteer found an event they want to participate in.|
| Postconditions |1: The event is added to the volunteer's events page. 2: The volunteer recieves a confirmation that they signed up. 3: The voluneteer gets their app udated with the event's information if it changes since they registered. |

| Use Case #2 | |
|---|---|
| Title |Organization Posts Event|
| Description / Steps |The organization is able to post an event to Serve Center. The organization should hit a create event button which takes them to a page where they will have to fill out a form containing information such as (event title, event name, volunteers needed, location, and date). From there a confirmation will be sent to the organization letting them know the event was posted. Finally they will be redirected to a page that shows them all their posted events with the amount of volunteers that have signed up.|
| Primary Actor |Organization|
| Preconditions |1: The organization is logged into their account. |
| Postconditions |1: The event is shown on the organizations page with an amount of volunteers currently signed up. 2: Uses are able to find the event by searching for the event name or organization name. The organization is notified when new volunteers signup or unregister.|

## Step 2.2 Define the MVC Components

| Model | View | Controller |
|---|---|---|
|User| User Profile|showUserProfile|
|Event| Registration Page |showRegistrationInfo|
| Organization |Event Page  |showEventInfo|
|Map|Map Page|showEventMap|

## Step 2.3 Diagram a Use Case in Architectural Terms
Below is a MVC use case diagram showing how an event gets created.

![MVC Use Case](Images/Use%20Case.png)


# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
Due to increased use from thrid-parties and the goal to implement Serve Center on external website the best architecture to move forward with is microservices. This choice is a reuslt of the fact that microservices allows for independent changes at all layers of the application which is great for implementing third party vendors.

The first major benefit of using this system is that it is very scalable so vendors can get as many resources as they need but Serve Center can also add as many vendors as we need as we can just make new services for each new vendor.

The second major benefit is that each service can have different technologies on it. So not all of our vendors have to use the same tehcnology or coding language in order to work with our system. We can have a service that works for them and does not impact the funcitonality for our other vendors. 

One final benefit is that because all of the services are independent it is very easy for testing to occur for one particular vendor and it not impact the rest of the vendors. This also means that deployment for one vendor will not impact another vendor.

One major drawback of this system is that it is very complex which can make it difficult to utilize the structure to its full potential. It also makes it harder to make sure that things aren't going wrong and that systems running smoothly.

Another drawback is that since all of the services are independent as more are adding more resources begin getting consumed which means that costs go up. As a app that is helping orginzations with volunteer work we might not make enough money to sustain this architecure as it scales.

## Step 3.2 Revised Architecture Diagram
Below is a microservices diagram showing how the new architecture will work. This architecture is incredibly flexible so more systems can be added easily to the diagram below depending on the needs of the company
![Microservices Architecture](Images/Architecture%20Chart.png)

# Step 4: Scaling an Architecture
Based on all of the needs due to the rapid growth I believe that microservices is still the best choice for architecture going forward. Due to microservices flexibility and scalability the need for more users to be supported and increased data storage is easy to handle with this system. More databases can be added easily which could even be vendor specific which would allow for vendors to take care of their own data. It would also allow for the user requirments as more resources can easily be added to the system. To address the other two needs microservices is still great because if each vendor gets its own database they can determine who can access what they want them to acces. For researchers a centralized database can be added that would have data from all vendors that researchers could access quickly.

The benefits are largely the same as the first time the scalability of the system will allow for more users and events easily. The flexibility will still allow vendors to have the systems they need on their own services. One of the previous drawbacks from before is also gone since the Gates Foundation is sponsering the project. Funding will no longer be a serious concern as we will have the users to fund us but also the grant to make sure the app is able ot perform.

One major drawback though is that since the app is growing so rapidly the complexity of this system could create deployment problems and make things get overlooked in the testing process. As a result services could be buggy or insecure. As more services go up it will only continue to get more complicated which can make new deployments take longer.



