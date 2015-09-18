---
layout: post
title:  "Basics of Web Application Security"
date:   2014-07-27 00:00:00
categories: technical
---


We've come to trust and rely on web applications for many everyday tasks, including ones involving our personal information. Unfortunately, we've all heard stories of such personal information being stolen, as applications are compromised by malicious hackers.

## Common Web Security Threats ##
Websites and web applications are collections of files stored on servers. When a user interacts with a website, he often provides personal information that the website administrators intend to keep private between the user's computer and the website's databases. Skilled hackers can find vulnerabilities in websites that allow them to steal such information. Two of the most prominent threats to web security are cross-site scripting (XSS) and SQL injection.

### Cross-Site Scripting (XSS) ###
Cross-site scripting involves a hacker running a script on the client-side of a web application. This can be implemented in a few different ways.

#### Persistent XSS ####
A hacker embeds a malicious script in a user input field, such as a comment field on a blog or a description field in a user profile. This can be performed by using the &lt;script&gt; HTML tag with a script file stored elsewhere on the internet. When a user loads the compromised webpage, the malicious script is loaded, unless proper precautions were taken in the site's design.

#### Non-Persistent XSS ####
A hacker directs unsuspecting people to a URL that loads an innocent website accompanied by a malicious script of his. This can be performed by taking advantage of a website's search field. Searching "Keyword" on a site may load a URL that ends in "Keyword." Depending on site design, the hacker could create a URL that corresponds to searching "Keyword &lt;script src=malicious-script.js". A user who is led to click on this link would see the page corresponding to the search for "Keyword," but the file malicious-script.js would be run in the background.
Server

#### Document Object Model (DOM) Based XSS ####
DOM-based XSS is a more recent threat, in which malicious files are run from the client side, as opposed to the server side. In persistent and non-persistent XSS, on the other hand, the malicious script file is stored on the hacker's server.

### SQL Injection ###
Many websites use SQL (Standard Query Language) to access database information in response to user requests. These databases may store information intended for customer use, as well as personal customer information. SQL injection can be performed via a search field on such a site. A hacker can enter language which, when input into the SQL query to the site's database provides him with customers' private information.

## Vulnerability Mitigation Strategies ##

### Escaping ###
Escaping is a method used in computer science to prevent characters with special meanings from being read as such. In user fields for which entered text will be input to a SQL query, characters that have special meanings in SQL are escaped to prevent SQL injection. Likewise, escaping HTML, CSS, or JavaScript characters can be used to prevent XSS.

### Sanitization ###
Sanitization is a process performed on untrusted HTML. The process strips the HTML of tags that could contain dangerous content. Tags that contain or format text content remain, while tags such as &lt;script&gt; and &lt;link&gt; are removed. 

## Application Security Testing ##
Applications must be tested before deployment. There are a variety of ways to perform this. Some perform testing near completion of a project, while others recommend testing be integrated throughout the application development process, with an agile approach. There is static testing as well as dynamic testing, and a new approach called interactive testing that combines both. 

Users across the internet trust companies with their personal information everyday. These companies have a responsibility to be aware of the security threats to their applications, and to take measures to prevent them.