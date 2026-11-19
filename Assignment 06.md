# Assignment 06 – Broken Access Control via Session Manipulation

## Task

Identify a flaw in the session management implementation of the web application and escalate privileges to obtain administrator access.

## Objective

Analyze the application's authentication workflow and determine whether authorization privileges can be manipulated through user-controlled session data.

### Initial Access

Logged into the application using the provided employee credentials and explored the available functionality available within the employee dashboard.

After successful authentication, access was limited to standard employee features.

### Request Analysis

Using Burp Suite, the authentication request was intercepted and inspected.

During analysis, the following parameter was observed within the request:

user\_role=employee
Since role information was being transmitted from the client side, this indicated a potential authorization weakness.

Evidence
!\[Burp Request Manipulation](Assignment-06screenshots/burp-role-manipulation.jpeg)

### Privilege Escalation

The captured request was forwarded to Burp Repeater for manual testing.

The role parameter was modified from:

user\_role=employee
to:

user\_role=admin
The modified request was then sent to the server.

### Verification

After resubmitting the modified request, the application granted administrator privileges without requiring elevated credentials.

This confirmed that authorization decisions were being made using user-controlled input.

Evidence
!\[Admin Dashboard](Assignment-06screenshots/admin-dashboard.jpeg)

## Attack Flow

* Obtained valid employee credentials.
* Logged into the application.
* Intercepted the authentication request using Burp Suite.
* Identified the role parameter in the request.
* Sent the request to Burp Repeater.
* Modified the role value from employee to admin.
* Forwarded the manipulated request.
* Successfully obtained administrator access.
* Retrieved the flag.

## Result

Successfully escalated privileges from a standard employee account to an administrator account.

## Flag Obtained

FLAG{COOKIE\_MANIPULATION\_SUCCESS}



## Vulnerability Analysis

The application trusted user-controlled data when determining authorization privileges.
Because role information could be modified directly within the request, an attacker was able to elevate privileges without possessing valid administrator credentials.

This vulnerability falls under:

* Broken Access Control
* Privilege Escalation
* Insecure Session Management

\## Security Impact
If present in a real-world application, this vulnerability could allow attackers to:

* Gain unauthorized administrative access
* View sensitive information
* Modify application data
* Perform privileged actions without authorization
* Mitigation

To prevent this issue:

* Enforce authorization checks on the server side.
* Never trust client-supplied role values.
* Store permissions within server-managed sessions.
* Validate access rights for every privileged action.

### Tools Used

* Burp Suite Community Edition
* Firefox Browser
* Linux Virtual Machine

### Key Learnings

* Learned how to intercept and analyze web requests using Burp Suite.
* Practiced request manipulation using Burp Repeater.
* Understood how insecure authorization mechanisms can lead to privilege escalation.
* Reinforced the importance of server-side access control validation.
* Gained practical experience identifying Broken Access Control vulnerabilities.

