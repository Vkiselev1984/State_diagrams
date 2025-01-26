# Basics of Statecharts

State is the current position of an object or system. It can be physical or logical. It is described using properties and parameters.

Sometimes we need to implement a simple program with several states: for example, a program for working with a barrier. The barrier can be in two states: "open" and "closed". This is enough to perform its main task. A similar example is a kettle with two modes: "on" and "off".

More complex states can be used to describe a car: for example, its speed, direction of movement, amount of fuel in the tank, and so on. The state of a computer can be described as the load on the processor, the available amount of RAM, and so on.

To describe all states, a state diagram is used - one of the most powerful tools for modeling and analyzing systems that change over time. A state diagram allows you to visualize possible states of a system and transitions between them, as well as describe the actions that occur in each state.

Example: Gray stickers are states, yellow ones are actions that lead to a state.

![stickers](/img/stickers.png)

## What does a state diagram look like?

A simple state diagram consists of the following elements:

- State — a phase or configuration in which an object or system is at a certain moment. In the diagram, it is represented as a rectangle with rounded corners and the name of the state.
- Transition — a mechanism that allows you to move from one state to another. Denoted by an arrow.
- Entry — a condition that can cause a transition from one state to another. This is a kind of start of events or an entry point into a state. For example, when you press the "Start" button, the system can move from the "Stopped" state to the "Running" state. The entry in this case is the "Pressing the start button" event.
- Exit — a condition that can cause a transition from one state to another.
- The final stage of all states. For example, when the system moves from the "Running" state to the "Stopped" state.

![simple state diagram](/img/simple_state_diagram.png)

## State diagram in the context of the development life cycle

To understand how different roles work with different system states, let's look at the entire software development process from the perspective of the SDLC model.

![SDLC](/img/software_development_life_cycle.png)

The SDLC development life cycle consists of the following stages:

1. Requirements analysis and planning — studying the needs of users and analyzing their possible solutions.
2. Design and implementation — creating specifications, diagrams, and
   other documents describing the architecture and design of the system.
3. Testing — checking and correcting found errors and deficiencies.
4. Deployment and support — installing the product at the customer’s site and supporting it.

## Tools for collecting information about an object

There are several tools:

- Logic and open sources. Together with the team, we can generate
  many ideas about how the system should look and what it should
  do. After that, ideas with descriptions of states need to be verified with the customer. Or better yet, invite a representative of the customer to participate in generating ideas.
- Interviews with stakeholders. Stakeholders are all those interested in the project. For example, to create a CRM system, stakeholders may be:
  - Salespeople
  - Customers
  - HR
  - Marketing
  - IT
  - Other stakeholders
  - We can ask them about their needs and expectations. This will help us to understand the requirements of the system.
  - User testing. We can ask users to try the system and give us feedback. This will help us to understand the requirements of the system.
- Business process analysis. As a rule, a company has regulations or established practices. We can analyze them and take them into account in the development of our system.
- Mind map creation. This is a method of information visualization. The main advantage is that visualization of concepts helps to find missing links and supplement them.

Example of mind map:
![mindmap](/img/mind_map.png)

Information is collected not only at the beginning of software development, but also at any other time — to update and supplement the state of the object.

Let's consider a state diagram using the example of an employee from the sales department.

Let's imagine that we need to implement a software product for this
specialist. The state diagram of a sales employee can be used to track and analyze his work at different stages of the sales process. It can include the following states:

- Customer acquisition: the employee searches for and attracts new customers for the company.
- Preliminary contact: the employee makes initial contact with the
  customer, discusses his needs and offers suitable products or services.
- Presentation: the employee presents products or services to the customer, answers his questions.
- Closing the deal: the employee closes the deal with the customer and closes the sale.
- After-sales service: the employee provides after-sales service to the client.

To collect this data, we can:

- Ask a sales representative.
- Interview a stakeholder.
- Analyze the company's regulatory documents on working with clients.
- Conduct an analysis of business processes.
- Use logic and open sources.

All this can be visualized using a mind map.
![mindmap](/img/mind_map_example_2.png)

## State diagram from the perspective of different roles

### Doctor appointment software

Online doctor appointment software allows patients to make an appointment online without having to visit a medical institution in person.

The functionality that the program may include:

- viewing available doctors and their schedules;
- choosing the time and date of the appointment;
- confirming the appointment via email or SMS;
- canceling or changing the appointment;
- appointment reminder;
- providing access to information about the patient's medical record and
  record history.

The system has many functions and objects whose states we can describe. To begin with, let's take the role of the program user (clinic client) and describe the state diagram for him from the point of view of the product manager - a specialist responsible for the development and management of the product.

Product manager responsibilities:

- identifying customer and market needs for product development;
- creating a product development strategy and plan;
- communicating with the development team and much more.

Our customers are the main users of the system, so the product manager
must have a clear idea of ​​what state they may be in. This will help
understand how to improve the product and what profit this improvement will bring.

1. First, let's describe all user states in the system:

- Not authorized: the user is not authorized in the application and does not have access to the appointment with a doctor function.
- Authorized: the user is authorized in the application and has access to the appointment with a doctor function.
- Select a doctor: the user selects a doctor from the list of available
  doctors.
- Select date and time: the user selects the date and time for
  an appointment with a doctor.
- Confirm appointment: the user confirms the appointment with a doctor and receives confirmation of the appointment.
- Cancel appointment: the user cancels the appointment.
- Visit to the doctor: the user has visited the doctor.

2. Let us formulate the actions in the system that transfer the user from one state to another:

- Not logged in: the user has not registered in the application.
- Logged in: the user has entered their login and password in the system.
- Doctor selection: the user has clicked on the doctor's profile and selected a doctor.
- Date and time selection: the user has clicked the date and
  time selection button.
- Appointment confirmation: the doctor has logged in and clicked the "Confirm appointment" button.
- Appointment cancellation: the user has clicked the "Cancel appointment" button.
- Visit to the doctor: the doctor has left information about the appointment in the system.

3. Let's draw a state diagram:
   ![doctor appointment software](/img/patient_status_chart_for_clinic.png)

4. Let's define the tasks from a product manager's perspective: what do we want to add at a particular stage.

- Not logged in: onboarding and registration for users who are not yet logged in.
- Logged in: improving the login system for already registered users (login by phone).
- Doctor selection: allowing users to select and view profiles of different doctors.
- Date and time selection: allowing users to select a date and time for an appointment.
- Appointment confirmation: implementing a confirmation function so that doctors can approve or reject an appointment request.
- Appointment cancellation: allowing users to cancel appointments if necessary.
- Doctor visit: tracking and information about doctor visits.
