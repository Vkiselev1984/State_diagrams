# Alert center operator status diagram

Let's say that city X has frequent fires, which create serious problems for local residents. The local government decided to implement an automatic fire alarm system to ensure the safety of citizens and
reduce the number of incidents.

## System Description

The operator-assisted fire detection system includes the following stages:

1. Waiting to receive the System Operator role.
2. Gaining access to the system after successfully passing the test.
3. User authorization to log in to the system.
4. Successful login or login failure, which leads to registration of a request to the technical service.
5. Monitoring the system, including receiving fire signals from sensors.
6. Data logging and signal verification.
7. Confirmation or denial of fire hazard.
8. Processing the incident depending on confirmation or denial.
9. Notification of users and the Fire Safety Service.
10. Conducting an incident investigation and compiling a final report.

## Operator States

1. **Waiting to receive the System Operator role**: The operator is waiting to receive access to the system.
2. **Getting access to the system**: The operator is being tested to receive access.
3. **User Authorization**: The operator enters the login credentials.
4. **Successful Login**: The operator successfully logs in to the system and proceeds to monitoring.
5. **Login Error**: In case of an error, the operator registers a request with the technical service.
6. **System Monitoring**: The operator receives fire signals from sensors and registers the data.
7. **Signal Check**: The operator checks the signals for compliance with the control values.
8. **Fire Danger Confirmation**: If the control values ​​match, the operator confirms the fire danger.
9. **Incident Handling**: The operator decides whether he can handle the incident or not.
10. **User Notification**: If the danger is confirmed, the operator notifies the users and the Fire Safety Service.
11. **Incident Registration**: The operator registers incidents and sends requests to technical support.
12. **Escalation**: If technical support is unable to resolve the issue, the request is escalated to a higher level.
13. **Incident Investigation**: The Fire Department investigates the incident and prepares a final report.

## Diagram

Here is the full table:
| Initial State | Current Status | Event | Next State |
|------------------------------------------------------|-----------------------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------|
|WaitingToReceiveSystemOperatorRole | WaitingToReceiveSystemOperatorRole | Passing the test | ObtainingAccessToTheSystem |
| ObtainingAccessToTheSystem | CheckingUserAccessRights | User authorization | SuccessfulLogin |
| CheckingUserAccessRights | SuccessfulLogin | Login | SystemMonitoring |
| CheckingUserAccessRights | LoginError | Login error | RegistrationRequestToTechnicalService |
| SystemMonitoring | ReceivingFireAlert | The sensor sends a fire alert | CheckingSignal |
| SystemMonitoring | ManualOverride | Manual override by operator | ManualOverride |
| CheckingSignal | FireHazardConfirmation | Control values match | AbilityToCope |
| CheckingSignal | AlternativeMethods | Control values do not match | FireHazardConfirmation |
| AlternativeMethods | RegistrationRequestToTechnicalService | Fire alarm signal not confirmed | RegistrationRequestToTechnicalService |
| AlternativeMethods | FireHazardConfirmation | Fire alarm confirmed | AbilityToCope |
| FireHazardConfirmation | AbilityToCope | Domestic smoke or fire | RegisteringCompletedIncident |
| FireHazardConfirmation | InabilityToCope | Domestic smoke or fire | NotifyFireSafetyService |
| InabilityToCope | NotifyFireSafetyService | Notification of users | ConfirmationByFireSafetyService |
| NotifyFireSafetyService | ConfirmationByFireSafetyService | Confirmation of the incident by the Fire Safety Service| RegisteringCompletedIncident |
| RegisteringCompletedIncident | IncidentReview | Smoke or fire has been eliminated | Review of incident response |
| OperatorActions | OperatorChecksSignal | Operator checks the signal | OperatorSendsRequest |
| OperatorChecksSignal | OperatorSendsRequest | Operator sends a request to technical support | OperatorCallsOwner |
| OperatorCallsOwner | InformingUsers | Operator calls the building owner | InformingUsers |
| InformingUsers | FollowUp | Operator informs users | FollowUp |
| OperatorSendsRequest | WaitingForResponse | Waiting for response from technical support | TechnicalSupportResponse |
| TechnicalSupportResponse | OperatorActions | Technical support provides assistance | Operator resumes actions |
| TechnicalSupportResponse | Escalation | Escalation to higher-level support | HigherLevelSupport |
| HigherLevelSupport | TechnicalSupportResponse | Engaging higher-level technical support | TechnicalSupportResponse |
| NotifyFireSafetyService | FireSafetyServiceResponse | Fire Safety Service responds | OperatorActions |
| FireSafetyServiceResponse | IncidentInvestigation | Operator receives confirmation | Investigation of the incident |
| IncidentInvestigation | ReviewFindings | Review findings of the investigation | FinalReport |
| ReviewFindings | FinalReport | Generate final report | | |

![UML diagramm](/img/Uml.png)

Use [planttext](https://www.planttext.com/) to plot this diagram.

```UML
@startuml
title Operator-assisted fire detection system states
scale 2400 width

[*] --> WaitingToReceiveSystemOperatorRole

WaitingToReceiveSystemOperatorRole --> ObtainingAccessToTheSystem: Passing the test

state ObtainingAccessToTheSystem {
ObtainingAccessToTheSystem --> CheckingUserAccessRights: User authorization
CheckingUserAccessRights --> SuccessfulLogin: Login
CheckingUserAccessRights --> LoginError: Login error
}

state SuccessfulLogin {
SuccessfulLogin --> SystemMonitoring: Enter system
}

state LoginError {
LoginError --> RegistrationRequestToTechnicalService: Registration of a request to the technical service department
}

state SystemMonitoring {
SystemMonitoring --> ReceivingFireAlert: The sensor sends a fire alert
ReceivingFireAlert --> CheckingSignal: Data registration
SystemMonitoring --> ManualOverride: Manual override by operator
}

state CheckingSignal {
CheckingSignal --> FireHazardConfirmation: Control values match
CheckingSignal --> AlternativeMethods: Control values do not match
}

state AlternativeMethods {
AlternativeMethods --> RegistrationRequestToTechnicalService: Fire alarm signal not confirmed
AlternativeMethods --> FireHazardConfirmation: Fire alarm confirmed
}

state FireHazardConfirmation {
FireHazardConfirmation --> AbilityToCope: Domestic smoke or fire
FireHazardConfirmation --> InabilityToCope: Domestic smoke or fire
}

state AbilityToCope {
AbilityToCope --> RegisteringCompletedIncident: Smoke or fire has been eliminated
RegisteringCompletedIncident --> IncidentReview: Review of incident response
}

state InabilityToCope {
InabilityToCope --> NotifyFireSafetyService: Notification of users
NotifyFireSafetyService --> ConfirmationByFireSafetyService: Confirmation of the incident by the Fire Safety Service
ConfirmationByFireSafetyService --> RegisteringCompletedIncident: Receiving confirmation from the Fire Safety Authority
}

state OperatorActions {
CheckingSignal --> OperatorChecksSignal: Operator checks the signal
OperatorChecksSignal --> OperatorSendsRequest: Operator sends a request to technical support
OperatorSendsRequest --> OperatorCallsOwner: Operator calls the building owner
OperatorCallsOwner --> InformingUsers: Operator informs users
}

state TechnicalSupport {
OperatorSendsRequest --> WaitingForResponse: Waiting for response from technical support
WaitingForResponse --> TechnicalSupportResponse: Technical support provides assistance
TechnicalSupportResponse --> OperatorActions: Operator resumes actions
TechnicalSupportResponse --> Escalation: Escalation to higher-level support
}

state Escalation {
Escalation --> HigherLevelSupport: Engaging higher-level technical support
HigherLevelSupport --> TechnicalSupportResponse: Response from higher-level support
}

state FireSafetyService {
NotifyFireSafetyService --> FireSafetyServiceResponse: Fire Safety Service responds
FireSafetyServiceResponse --> OperatorActions: Operator receives confirmation
FireSafetyServiceResponse --> IncidentInvestigation: Investigation of the incident
}

state IncidentInvestigation {
IncidentInvestigation --> ReviewFindings: Review findings of the investigation
ReviewFindings --> FinalReport: Generate final report
}

@enduml
```
