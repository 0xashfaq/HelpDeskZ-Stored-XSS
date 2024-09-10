### Vulnerability Description:

Cross-site scripting (XSS) is a security vulnerability that allows an attacker to inject malicious scripts into web applications. These scripts can lead to severe consequences such as session hijacking, defacement, or redirection to malicious sites.

In HelpDeskZ v2.0.2, an attacker can exploit an XSS vulnerability by injecting malicious code into the Allowed file types. This code executes within the context of the administration panel, leading to potential security breaches.

### Payload:
  "><img+src=x+onerror=alert(1)>

### Steps to Reproduce:
* Log in as a normal user.
* Navigate to Setup> Tickets Settings.
* Check out the Allowed file types
* Capture the request using Burp Suite or a similar tool.
* Modify the title field with the following payload: "><img+src=x+onerror=alert(1)>
* Forward this modified request.
* Go to the Submit Ticket form and the pop-up will appear.

### POC
https://github.com/0xashfaq/HelpDeskZ-Stored-XSS/blob/860f369046d2e30e4b550c9a7bb5672124d3da28/2024-08-15%2017-21-01.mp4
