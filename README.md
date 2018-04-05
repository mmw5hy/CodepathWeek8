# Project 8 - Pentesting Live Targets

Time spent: **X** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue

  Vulnerability #1: SQL Injection
  An id is passed as a parameter in the salesperson lookup page. Modifying the id to be %27 (https://35.202.198.115/blue/public/salesperson.php?id=%27) on the blue website causes a page to pop up that says "database query failed." This shows that by changing the id in the url, we are able to directly change the sql command tha tis made to the database. The other two sites simply redirect the user to the default salesperson page.

Vulnerability #2: __________________


## Green

Vulnerability #1: Username Enumeration
When attempting to login with "jmonroe99" but an invalid password, all websites give the output message "log in was unsuccessful" in a span element with the class "failure". However, when logging in with the name of a user account that doesn't exist, such as "asdfasdfa", the green site prins out the error message in a span element with the class "failed" rather than "failure" as the other two do. 

Vulnerability #2: Cross-Site Scripting
Entering the text "<script>alert('Michael found the XSS!');</script>" into the feedback form on the green site and then navigating to the feedback page opens an alert. This shows that the input text was interperted as html and thus javascript code can be placed here to perform an XSS attack.


## Red

Vulnerability #1: Insecure Direct Object Reference
On the red website, the query parameter "id" in the url of the "find a salesperson" lookup can be manually changed to access all salespersons, such as at id=10 (which is says shouldn't be public until sept. 1). On the other two sites, entering the corresponding url "https://35.202.198.115/red/public/salesperson.php?id=10" redirects the user to the public salesperson home page, but only the red site shows the info on the salesman. 

Vulnerability #2: __________________


## Notes

Describe any challenges encountered while doing the work
