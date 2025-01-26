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

1. The user is familiarized with the protocols and updates to obtain the role of System Operator
2. The user is tested and granted access to work in the System
3. The user receives credentials to enter the System
4. The user is authorized in the System as an Operator
5. The operator receives a signal from sensors that register an increase in temperature or smoke
6. The operator analyzes the data from the sensors and checks for errors and compliance with control values
7. If necessary, the operator contacts the building owner or his representative to confirm the incident
8. If a fire hazard is confirmed, the operator notifies users and the Fire Safety Service
9. The operator registers incidents and sends requests to the technical support department

## Diagram

Here is the full table:

| Initial state                                                 | Current status                                                              | Event                                                  | Next state                                                    |
| ------------------------------------------------------------- | --------------------------------------------------------------------------- | ------------------------------------------------------ | ------------------------------------------------------------- |
| Waiting to receive the System Operator role                   | Familiarization with the System protocols and updates                       | Passing the test                                       | Obtaining access to the System                                |
| Obtaining access to the System                                | Obtaining credentials to work in the System                                 | User authorization                                     | Checking user access rights                                   |
| Checking user access rights                                   | Successful authorization                                                    | Login                                                  | System Monitoring                                             |
| Checking user access rights                                   | Authorization denied                                                        | Login error                                            | Registration of a request to the technical service department |
| System Monitoring                                             | The sensor detects a rise in temperature                                    | The sensor sends a fire alert to the control center    | Receiving a fire alert from the control center                |
| System Monitoring                                             | The sensor detects smoke                                                    | The sensor sends a fire alert to the control center    | Receiving a fire alert from the control center                |
| System Monitoring                                             | Receiving an error signal                                                   | Getting an error code                                  | Registration of a request to the technical service department |
| Receiving a fire alert from the control center                | The operator receives data from sensors about temperature increase or smoke | Data registration                                      | Checking the signal                                           |
| Registration of a request to the technical service department | Getting an answer from a specialist                                         | Login                                                  | System Monitoring                                             |
| Checking the signal                                           | Analysis of data from the System sensors                                    | Control values match                                   | Fire hazard confirmation                                      |
| Checking the signal                                           | Analysis of data from the System sensors                                    | Control values do not match                            | Checking the signal with alternative methods                  |
| Checking the signal with alternative methods                  | Call the owner or contact person                                            | Fire alarm signal not confirmed                        | Registration of a request to the technical service department |
| Checking the signal with alternative methods                  | Call the owner or contact person                                            | Fire alarm confirmed                                   | Fire hazard confirmation                                      |
| Fire hazard confirmation                                      | Determining the level of fire danger                                        | Domestic smoke or fire                                 | Confirmation of ability to cope with the incident             |
| Fire hazard confirmation                                      | Determining the level of fire danger                                        | Domestic smoke or fire                                 | Inability to cope with the incident                           |
| Confirmation of ability to cope with the incident             | Confirmation of incident completion                                         | Smoke or fire has been eliminated                      | Registering a completed incident                              |
| Registering a completed incident                              | Registration of a request to the technical service department               | Checking sensors and system performance                | Completion of the incident                                    |
| Inability to cope with the incident                           | Incident registration                                                       | Notification of users Fire safety systems and services | Confirmation of the incident by the Fire Safety Service       |
| Confirmation of the incident by the fire safety service       | Elimination of smoke or fire                                                | Receiving confirmation from the Fire Safety Authority  | Registering a completed incident                              |

![Alert center diagramm](/img/Alert%20center%20diagramm.jpg)

[Link to comment Alert center diagramm](https://miro.com/welcomeonboard/dFZEK1lvdzVDNjhydlppb2JhakZXbnhkK05XQVI5d0YwRHF4M0cyd0hObjVnb0pMRnZXMnU5K2k1OCtuckJTWXo3RHgwMmxnZ01VUlBUaTlSam1DcVFscjZ6MkhJcTdVbkVZdC9HMmRSRG9JdFBOTUo3MnZtVjl2WThUVmhEWC8hZQ==?share_link_id=99174274404)
