# Project 8 - Pentesting Live Targets

Time spent: 4 hours spent in total

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

Vulnerability #1: SQL Injection (SQLi
1. The vulnerability was present on the salesperson page. Edited the URL of the page adding SLEEP(5)=0--' after the id
 https://35.224.59.192/blue/public/salesperson.php?id=' OR SLEEP(5)=0--'
2. This causeed thesite to stall and delay of 5 seconds

<img src="https://github.com/nayanika96/Codepath-Week-8/blob/master/sqldelay.gif" width="600">


Vulnerability #2 Session Hijacking/Fixation
1. Logged in to the site on one a Google Chrome browser and opened the same site on a Safari browser without logging in on another browser. Using the tool given by codepath  copied the PHPSESSIONID of the page which was logged in and pasted the same PHPSESSIONID on the other browser in which the site was not logged in. 
2.This resulted in the site on Safari being automatically logged in to without entering the username and password and just pasting the PHPSESSIONID 
<img src="https://github.com/nayanika96/Codepath-Week-8/blob/master/sessionhijacking.gif" width="600">


## Green

Vulnerability #1: Username Enumeration
1. Tried logging in with the right username and wrong password, Login was unsuccessful is in bold. However, tried the same steps when username was wrong, the Login was unsuccessful was no longer in bold

<img src="https://github.com/nayanika96/Codepath-Week-8/blob/master/usernameenumeration.gif" width="600">


Vulnerability #2: Cross-Site Scripting (XSS)
1. In the contact section, posted this <script>alert("Alert!");</script> as a feedback comment
2. After logging in with the username and password, the submitted form section had the javascript alert pops up

<img src="https://github.com/nayanika96/Codepath-Week-8/blob/master/crossitegreenfinal.gif" width="600">

## Red

Vulnerability #1:Insecure Direct Object Reference (IDOR)
1. In the find a salesperson page after changing the ID number to 10, access was granted to a site which is not open to public before hand.

<img src="https://github.com/nayanika96/Codepath-Week-8/blob/master/salespersonid.gif" width="600">

Vulnerability #2:Cross-Site Request Forgery (CSRF)
1. Edited the CSRF token in the form, this should have made the form invalid. However, the form submission went through despite it being edited. 
<img src="https://github.com/nayanika96/Codepath-Week-8/blob/master/forgered.gif" width="600">

## Notes

Describe any challenges encountered while doing the work
