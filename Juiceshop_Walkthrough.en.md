**List of vulnerabilities**

The vulnerabilities present on the platform are categorized by the OWASP community as follows:

![](Aspose.Words.751010d2-48a8-4dd0-a6a6-3cf4c14f4f17.001.png)

In the work I have done, I have exploited the vulnerabilities: The challenges were of difficulty 1 to 3.

**Challenges**

- *Admin Login*

The exploited vulnerability is SQL injection. To solve this challenge, we exploited the non-protection of forms against SQL command injections. Thus, we notice on the connection form on the platform that the data entries are not secure, we can therefore easily bypass password authentication via SQL comments via the command:

' – OR TRUE

- *Admin Section*

Once logged in as an administrator, we have privileges which allow us to have access to the application server, in particular the site administration page. But we obviously don't know the path to access the page. But the site is vulnerable to weak access controls and insecure code. By looking for the keyword “admin or administration” when inspecting the page, we come across the path.

![](Aspose.Words.751010d2-48a8-4dd0-a6a6-3cf4c14f4f17.002.png)

![](Aspose.Words.751010d2-48a8-4dd0-a6a6-3cf4c14f4f17.003.png)


- *DOM XSS*

This attack exploits the XSS vulnerability on the page's search bar which is vulnerable to command execution.

![](Aspose.Words.751010d2-48a8-4dd0-a6a6-3cf4c14f4f17.004.png)

- *Bonus Payload*

This challenge also exploits the vulnerability of the search bar to command execution. Successful completion of this challenge results in playable audio as below.

To operate, simply copy the script provided into the search bar and start the search.

![](Aspose.Words.751010d2-48a8-4dd0-a6a6-3cf4c14f4f17.005.png)


- *Bully chatbot*

  This challenge consisted of chatting with a cat to encourage it to send us a coupon code.

  ![](Aspose.Words.751010d2-48a8-4dd0-a6a6-3cf4c14f4f17.006.png)

- *Error Handling*

This vulnerability present on the system made it possible, for example, to find the error which is generated to understand the format of the SQL command which is not controlled, namely for the “Object==Object” form.

- *Forged Feedback*

This challenge consists of sending feedback on the application, but pretending to be someone else.

I logged in as the admin user whose email I was able to obtain on the site administration page.

Once done, I started the Burpsuite proxy to capture the HTTP request that is sent to see what settings can allow me to impersonate another user.

![](Aspose.Words.751010d2-48a8-4dd0-a6a6-3cf4c14f4f17.007.png) 

Once the query is captured with Burp, we notice that there is a session ID for the user which constitutes a key on the query. By modifying this id (userid), we manage to send the feedback by pretending to be another user once the request is sent to the repeater where we modify the parameters.

- *Login Bender*

For this challenge, it was necessary to exploit the SQL vulnerability on the connection form.

But first, I went to find the email used by user Bender. To do this, it should be noted that in the carousels scrolling on the comments on the application and also in those on the products provided, we could retrieve user emails for Bender which were: bender@juice-shop

I then entered the email normally, which I associated with ' – OR TRUE when entering any password.

- *Login Jim*

Still via SQL injection, the process is the same.

![](Aspose.Words.751010d2-48a8-4dd0-a6a6-3cf4c14f4f17.008.png)

- *Meta Geo Stalking*

The goal of the challenge was to determine the answer to user John's security question to change his password. To do this, I used OSINT to answer the question “Where is the place I love to kicking?”

We can then notice that the user John sent a photo to the application. By analyzing it via Google Lens, we determine the name of the place: Daniel Boone National Forest. Once that was done, I set a new password johnny123.

![](Aspose.Words.751010d2-48a8-4dd0-a6a6-3cf4c14f4f17.009.png)

![](Aspose.Words.751010d2-48a8-4dd0-a6a6-3cf4c14f4f17.010.png)


![](Aspose.Words.751010d2-48a8-4dd0-a6a6-3cf4c14f4f17.011.png)

- *Password Strength*

The goal of the challenge was to log in as the user without a SQL injection attack.

The password used on the system is not very secure and is therefore easily gamed admin123. The vulnerability is in the length and complexity of the password required by the platform.

![](Aspose.Words.751010d2-48a8-4dd0-a6a6-3cf4c14f4f17.012.png)

- *View Basketball*

For this challenge, you had to display the contents of another user's shopping cart using the Broken Access Control vulnerability.

Specifically, I inspected user Amy's Shopping Cart page which I was able to connect to using SQL injection. I noticed that on the page specifically in the local storages, there were double values, key which is associated with objects on the site. We therefore notice the bid parameter (Basket Id more clearly) by replacing it, we thus have access to the basket session of another user. We reload the page and that's it.

![](Aspose.Words.751010d2-48a8-4dd0-a6a6-3cf4c14f4f17.013.png)

- *Password Policy*

Once connected to a user's profile, you can access the application's Policy and Security menu and thus view the Password policy.

- *Scoreboard*

For the scoreboard, you must seek to obtain the link allowing access to it, there are two vulnerabilities there, one for authentication and one for coding security.

By searching the page for the keyword “score” then “score board, we come across the path: '../score-board'.

- *Zero Star*

This challenge consisted of giving zero stars to the application, which would normally be impossible.

I went to the feedback page and after filling out the form, I activated my proxy and captured the HTTP request that I sent to the Repeater to modify the star rating parameter, which I set to 0. Once it's done, we validate the request and Hop, it's done.



