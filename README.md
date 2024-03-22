# LIB_Workday

## Description
This library interacts with the workday web portal to perform job requisition and candidate related activities.
Dependencies used:
"UiPath.UIAutomation.Activities": "23.4.8"
 "UiPath.System.Activities": "23.4.5"

## Features
- [Activity-1: Logging to Workday](#activity-1-LoggingToWorkday_WorkdayLogIn)
- [Activity-2: Search JR Number](#activity-2-SearchJRNumber_Workday)
- [Activity-3: Search Employee](#activity-3-SearchEmployee_Workday)
- [Activity-4: Get Job Profile](#activity-4-GetJobProfile_Workday)
- [Activity-5: Get Candidate Home Address Internal](#activity-5-GetCandidateHomeAddress_Internal_Workday)
- [Activity-6: Get Candidate Home Address External](#activity-6-GetCandidateHomeAddress_External_Workday)
- [Activity-7: Get Service Date](#activity-7-GetServiceDate_Workday)
- [Activity-8: Logging out Workday](#activity-8-LoggingOutWorkday_Workday)





## Activity 1: LoggingToWorkday_WorkdayLogIn
 
### Details:
  - This reusable activity logs in to workday web (MSEDGE) portal using SSO.

<br/>List of arguments used:
<br/> in_strURL- URL to the workday portal
<br/> in_strSELoginFailure – Exception message to be thrown in case of login failure.
<br/> out_boolLoginSuccess – Boolean to check if the login was success.

- Table Content : 

    | Command | Description |
    | --- | --- |
    | Input | in_strURL: string; in_strSELoginFailure: string; |
    | Output | out_boolLoginSuccess: bool; |
    | Input/Output | NA |
    | Requirements | NA |
    | App Version | NA |
 
- [Back to menu](#features)


## Activity 2: SearchJRNumber_Workday

### Details:
  - This reusable activity searches input JR number and opens it in workday.

<br/>List of arguments used:
<br/> in_strJRNumber -Input JR number to be searched in workday.
<br/> in_strURL- URL to the workday portal.
<br/> in_strBEJRNumber – Business Exception message if the JR number is not found in workday.
<br/> in_strSEHomeNotFound - System Exception message if the home page is not found in workday.

- Table Content: 

    | Command | Description |
    | --- | --- |
    | Input | in_strJRNumber: string; in_strURL: string;  in_strBEJRNumber: string; in_strSEHomeNotFound: string;|
    | Output | NA |
    | Input/Output | NA |
    | Requirements | NA |
    | App Version | NA |



- [Back to menu](#features)

## Activity 3: SearchEmployee_Workday

### Details:
- This reusable activity search for employee in workday based on input employee name and profile view

<br/>List of arguments used:
<br/> in_strURL- URL to the workday portal.
<br/> in_strEmployeeFullName- Employee name to be searched in workday.
<br/> in_strBEEmployeeNotFound- Business Exception message if the employee is not found in workday.
<br/> in_strProfileView- Profile view of the candidate (Candidate/People).
<br/> in_strSEHomeNotFound - System Exception message if the home page is not found in workday.


- Table Content: 

    | Command | Description |
    | --- | --- |
    | Input | in_strEmployeeFullName: string; in_strURL: string;  in_strBEEmployeeNotFound: string; in_strSEHomeNotFound: string; in_strProfileView:string; |
    | Output | NA |
    | Input/Output | NA |
    | Requirements | NA |
    | App Version | NA |



- [Back to menu](#features)

## Activity 4: GetJobProfile_Workday

### Details:
This activity extracts Job Profile of the job requisition.

<br/>List of arguments used:
<br/> in_strURL- URL to the workday portal.
<br/> in_strSEDetails- System Exception message if the details tab is not found in workday.
<br/> in_strSEJobProfile- System Exception message if the job profile field is not found in workday.
<br/> out_strJobProfile- Extracted job profile value.
<br/> in_strSEWorkerSubType- System Exception message if the worker subtype field is not found in workday.
<br/> out_strWorkerSubType- Extracted worker sub type value.

- Table Content: 

    | Command | Description |
    | --- | --- |
    | Input | in_strURL: string;  in_strSEDetails: string; in_strSEJobProfile: string; in_strSEWorkerSubType: string|
    | Output | out_strJobProfile: string ; out_strWorkerSubType: String|
    | Input/Output | NA |
    | Requirements | NA |
    | App Version | NA |



- [Back to menu](#features)

## Activity 5: GetCandidateHomeAddress_Internal_Workday

### Details:
-This activity extracts home address and phone number of the candidate of internal transfer type.


<br/>List of arguments used:
<br/> in_strURL- URL to the workday portal.
<br/> in_strDelayTimeSmall- Value of delay in between actions.
<br/> in_strSEAddressMissing- System Exception message if the address field is not found in workday.
<br/> in_strSESummaryTab- System Exception message if the summary tab is not found in workday.
<br/> in_strSEContactTab- System Exception message if the contact tab is not found in workday.
<br/> out_strHomeAddress- Extracted home address of the candidate.
<br/> out_strPhoneNumber- Extracted home address of the candidate.

- Table Content: 

    | Command | Description |
    | --- | --- |
    | Input | in_strDelayTimeSmall: string; in_strURL: string;  in_strSEAddressMissing: string; in_strSESummaryTab: string; in_strSEContactTab;|
    | Output | out_strHomeAddress: string; out_strPhoneNumber:string; |
    | Input/Output | NA |
    | Requirements | NA |
    | App Version | NA |



- [Back to menu](#features)



## Activity 6: GetCandidateHomeAddress_External_Workday

### Details:
- This activity extracts home address and phone number of the candidate of external transfer type.

<br/> in_strURL- URL to the workday portal.
<br/> in_strDelayTimeSmall- Value of delay in between actions.
<br/> in_strSESummaryTab- System Exception message if the summary tab is not found in workday.
<br/> out_strHomeAddress- Extracted home address of the candidate.
<br/> out_strPhoneNumber- Extracted home address of the candidate.

- Table Content: 

    | Command | Description |
    | --- | --- |
    | Input | in_strDelayTimeSmall: string; in_strURL: string; in_strSESummaryTab: string; |
    | Output | out_strHomeAddress: string; out_strPhoneNumber:string;  |
    | Input/Output | NA |
    | Requirements | NA |
    | App Version | NA |



- [Back to menu](#features)

## Activity 7: GetServiceDate_Workday

### Details:
This activity extracts service date of the candidate and applicable only for internal transfer type.

<br/>List of arguments used:
<br/> in_strURL- URL to the workday portal.
<br/> in_strSEJobTab- System Exception message if the job tab is not found in workday.
<br/> in_strSECompanyServiceDate- System Exception message if the company service date field is not found in workday.
<br/>in_strSEServiceDate- System exception message if the service date tab is not found.
<br/>out_strCompanyServiceDate- Extracted service date value.

- Table Content: 

    | Command | Description |
    | --- | --- |
    | Input | in_strURL: string;  in_strSEJobTab: string; in_strSECompanyServiceDate: string; in_strSEServiceDate:string; |
    | Output | out_strCompanyServiceDate: string ;|
    | Input/Output | NA |
    | Requirements | NA |
    | App Version | NA |



- [Back to menu](#features)

## Activity 8: LoggingOutWorkday_Workday

### Details:
-This activity logs out from the workday portal.


<br/>List of arguments used:
<br/> in_strURL- URL to the workday portal.

- Table Content: 

    | Command | Description |
    | --- | --- |
    | Input | in_strURL: string;|
    | Output | NA |
    | Input/Output | NA |
    | Requirements | NA |
    | App Version | NA |



- [Back to menu](#features)
