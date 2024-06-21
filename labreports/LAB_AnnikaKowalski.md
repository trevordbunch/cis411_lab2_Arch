# Lab Report: Continuous Integration
___
**Course:** CIS 411, Spring 2021  
**Instructor(s):** [Trevor Bunch](https://github.com/trevordbunch)  
**Name:** Annika Kowaslki 
**GitHub Handle: https://github.com/AnnikaKowalski/cis411_lab2_arch
**Collaborators:** 
___

# Step 1: Confirm Lab Setup
- [ yes ] I have forked the repository and created my lab report
- [ yes ] I have reviewed the [lecture / discsussion](../assets/04p1_SolutionArchitectures.pdf) on architecture patterns.
- [ NA ] If I'm collaborating on this project, I have included their handles on the report and confirm that my report is informed, but not copied from my collaborators.

# Step 2: Analyze the Proposal
Serve Central is an app that allows users to locate volunteer/serving opportuniues in the local area. It allows users to register for the event throguh the mobile app. 

## Step 2.1 Representative Use Cases  

| Use Case #1 | Volunteer |   
| Title | Signing up for a Service Event |   
| Description / Steps | This use case will show how to sign up for a service event that is taking place. |  
| Primary Actor | Volunteer |  
| Preconditions | The volunteer must have an account with Serve Central. To create an accoutn you will click the "create account" button. There must be an event in the local area that the volunteer can sign up for. |  
| Postconditions | The service event team leader must be able to view all the members who have signed up for volunteer for the event. |

| Use Case #2 | Companies Offering Service Events |    
| Title | Adding a Service Event |      
| Description / Steps | This use case will describe how a company will list volunteer spots on the Serve Central app for lacal people to sign up for. |    
| Primary Actor | Company Hosting the Event |    
| Preconditions | The company msut sign up for a Serve Central service agent account, to do so click the "service agent account creator" button. The company already has a Serve Central account under the sevice agent category, this allows them to create events. |  
| Postconditions | The company's event is then added to the lisst for the locals to see as an opportunity for service/volunteering. |

## Step 2.2 Define the MVC Components
| Model | View | Controller |  
| Name | Organizations Page | Event Feed Controller |    
| Location  | Volunteer's Feed Page  | Volunteer Feed Controller |  
| Event Title | Event Feed Page | Event Feed Controller |  
| Event Description  | Decription Feed Page | Description Feed Controller |  

## Step 2.3 Diagram a Use Case in Architectural Terms
The volunteer makes a request to the controller for a Serve Central account. The controller then sends it to the model. The model creates the account for the volunteer and sends that to the view. The view allows the volunteer to view service opporunitites and they can sign up for ones that interst the. 

# Step 3: Enhancing an Architecture

## Step 3.1 Architecture Change Proposal
I will continue to use the MVC model at this time. Down the road I would consider changing the the model but not at this time since I do not feel that it woudl be necessary. I would add a third party API which would allow users to navigate to the website of the organization they are volunteering for. By adding this feature those who are volunteering can understnad the organization's mission and see if that service project is someting thet are interested in. By adding the API users will be able to connect to the website pages easier than before. A set back would be that the MVC model can becoe very complicated very quickly which can cause the viewers page to change with the MVC updates made. 

## Step 3.2 Revised Architecture Diagram
The data will flow very similarly to the graph that was shown prior. There are some changes and they include...the model now sends information to the thrid party. This is where the the thrid party gets the website information adn sends it back to the model. The view sends the information to the organization's page which is how the serivce organization's page updates for the unsers. The view receives the information from a button that the user clicks, it deos not directly interact with the controller. The user is then able to view the service organization's information wihtout leaving the app for any reason. 

# Step 4: Scaling an Architecture
It is great that the organization is growing but with the bursts it can be challenging for the company. With the large amouts of traffic the best way to handle that would be to add a load balancing technique/system. This technique would decrease down time on the app and reduce repitition which would allow users to have a better experience. To make this possible I reccomend adding hot spots which allow the app to have better response times as well as reducing risks for cyberattacks and other attacks to out network and app. In order to make sure these additons are successful and working properly it would be best to monotior to ensure that no hacking is taking place. It would also be important to make sure that informtaion is not repetitive on the user end as this can cause some lag time and create a slower app for the user. All of these additons that were just made will need additional architecture to ensure that the system can handle these revisions. 

# Extra Credit
If you opt to do extra credit, then include it here.