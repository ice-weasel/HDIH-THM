# HDIH-THM
A writeup for the "Hidden Deep Into my Heart" room on TryHackMe.

We cam visit ``` <MACHINE_IP>:5000 ``` to find the web application.

<img width="2558" height="1392" alt="image" src="https://github.com/user-attachments/assets/ebc06a5f-dadc-4f64-b331-f6068fd08827" />


Now usually websites have a ``` /robots.txt ``` page specifying the list of directories and pages that web crawlers and bots are not supposed to crawl.

Visiting it gives us some interesting information :

<img width="393" height="136" alt="image" src="https://github.com/user-attachments/assets/804efd7f-5030-4a93-8828-3a0901b2b1a2" />

Upon visiting the specified page we find the secret vault of the page. But even upon inspection of the page source we cannot find anything useful for progressing.

<img width="2555" height="1133" alt="image" src="https://github.com/user-attachments/assets/f399257f-19ff-4d01-90e9-3cd2773971d7" />

We can try gobuster on this page and try to find any other pages :

``` gobuster dir -u http://10.49.166.117:5000/cupids_secret_vault/ -w /usr/share/wordlists/dirb/common.txt ```

<img width="1055" height="490" alt="image" src="https://github.com/user-attachments/assets/86df6117-b055-4613-8159-50dffaaf05cd" />

There we got it!!

Now lets check it out. We find a login page, now before we try to brute force or anything we can first use the password-looking text in the robots.txt page,

After some tinkering around, we get this: 

<img width="1280" height="566" alt="image" src="https://github.com/user-attachments/assets/b7d04221-0f36-4d2d-aefc-001befbda67e" />\


And we have got our flag!!!
