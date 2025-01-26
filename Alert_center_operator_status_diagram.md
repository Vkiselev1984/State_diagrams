# Alert center operator status diagram

Let's say that city X has frequent fires, which create serious problems for local residents. The local government decided to implement an automatic fire alarm system to ensure the safety of citizens and
reduce the number of incidents.

## System Description

The system includes the following steps:

1. Installing smoke alarms or high temperatures indoors
2. Testing software
3. Training personnel to work with software and obtaining permission to work with the system
4. Conducting training for Fire Safety Control Center operators and other system specialists
5. Receiving a signal by the Center
6. The Center operator checks the received signal. In case of a malfunction, sends a request to the technical maintenance department
7. The Center operator determines the level of fire hazard (local, high, emergency), records sensor data. In case of an emergency, calls the head of the department for further coordination of the operators' work
8. The Center operator sends a fire alert to registered users of the system depending on the level of fire hazard
9. The Center operator sends a message to social services, the fire department
10. Registered users receive a fire notification and evacuation information
11. The fire department receives a notification of the fire and its location and sends a fire brigade to the scene.

## Operator States

1. Undergoing training by the Center operator
2. Obtaining permission to work with the system
3. Logging into the system (training, service)
4. Receiving a signal:

- Via the Contact Center
- Activation of sensors

5. Checking the signal:

- Surveying users
- Notifying the building owner
- Registering a request for a technical service specialist to check the sensors

6. Confirming the fire hazard, registering the request.
7. Determining the level of fire hazard (local, high, emergency).
8. Determining the presence of victims, people in danger.

- Notifying users
- Notifying the fire safety service, social services
- Calling the manager to monitor the situation and coordinate actions in the event of an emergency

9. Briefing users to localize the hazard or evacuate
10. Receiving a signal about the end of the fire hazard
11. Registering a request for reinstallation of sensors and testing the system.

## Diagram

Here is the full table:

| Initial State                                                                               | Current State                                                                                    | Event                                                                                                                                              | Next State                                                              |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| Training and Education                                                                      | Operators undergo regular training on new protocols and system updates.                          | Completion of training and acquisition of all necessary knowledge.                                                                                 | Obtaining clearance to work with the system.                            |
| Obtaining clearance to work with the system                                                 | Operators are granted clearance to work with the system after successful completion of training. | Obtaining all necessary permits and certificates.                                                                                                  | Login to the system.                                                    |
| Login to the system (training, service)                                                     | Operators log in to the system to start their shift.                                             | Successful login.                                                                                                                                  | Receiving a signal.                                                     |
| Receiving a signal                                                                          | The center receives a signal about a possible incident.                                          | The signal can come through the Contact Center or the activation of sensors.                                                                       | Signal verification.                                                    |
| Signal verification                                                                         | The operator verifies the authenticity of the signal.                                            | Includes a user survey, notification of the building owner, and registration of a request for a technical service specialist to visit the sensors. | Confirmation of a fire hazard.                                          |
| Confirmation of fire hazard, registration of application                                    | The operator confirms the presence of a fire hazard and registers the application.               | Completion of registration.                                                                                                                        | Determining the level of fire hazard.                                   |
| Determining the level of fire hazard (local, high, emergency)                               | The operator determines the level of danger based on the data received.                          | Making a decision on the scale of the incident.                                                                                                    | Determining the presence of victims and people in danger.               |
| Determining the presence of victims, people in danger                                       | Checking the presence of victims and people in danger.                                           | Confirming or refuting the presence of victims.                                                                                                    | Notifying users and services.                                           |
| Notifying users                                                                             | Operators send fire alerts to registered users of the system.                                    | Sending alerts complete.                                                                                                                           | Notifying the fire safety service and social services.                  |
| Notifying the fire safety service, social services                                          | Operators send messages to the fire department and social services.                              | Messages successfully sent.                                                                                                                        | Calling the manager to monitor the situation.                           |
| Calling the manager to monitor the situation and coordinate actions in case of an emergency | The head of the department is called to coordinate actions.                                      | The manager has started coordinating.                                                                                                              | Briefing users.                                                         |
| Briefing users to localize the hazard or evacuate                                           | Operators instruct users on the necessary actions.                                               | Briefing completed.                                                                                                                                | Receiving a signal about the end of the fire hazard.                    |
| Receiving a signal about the end of the fire hazard                                         | The center receives a signal about the end of the fire hazard.                                   | Incident completion confirmed.                                                                                                                     | Registering a request for reinstallation of sensors and system testing. |
| Registering a request for reinstallation of sensors and system testing                      | Operators register a request for reinstallation of sensors and system testing.                   | Request registered.                                                                                                                                | Monitoring and completion of the incident.                              |

![Alert center diagramm](/img/Alert_center_diagramm.jpg)
