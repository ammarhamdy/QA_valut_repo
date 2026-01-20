
# Number of users (Peak Concurrency)

This is the total size of the crowd. 

It represents the maximum number of virtual users that will be active and clicking around your site at the same time once the test is fully running.

>Example: If you set this to 100, Locust will eventually have 100 "people" (Python processes) making requests to your server ==simultaneously==.

**Goal:** Use this to test your server's capacity. 
For instance, "___Can my site handle 500 people at once?___"


# Ramp Up (Users started/second)

This is the speed of the [turnstile](https://en.wikipedia.org/wiki/File:Turnstiles_in_Alewife_station,_August_2005.jpg). 
It defines how fast new users are added until you reach the peak number.

Example: If your Peak Concurrency is 100 and your Ramp Up is 10:
>   Second 1: 10 users start.
Second 2: 20 users are now running.
...
Second 10: All 100 users are finally running.

>   If you put 10 in the Ramp Up box, it means:
"==Every second, open the turnstile and let 10 more virtual users into the test until we hit the total limit==."

Why it matters: If you start `1,000` users at once (Ramp Up = `1,000`), you might "shock" the server, causing it to crash immediately just from the login overhead. 

==Ramping up slowly mimics real life, where people join a site gradually==.



# RPS vs. Users
A common mistake is thinking 100 users equals 100 Requests Per Second (RPS).

If a user clicks a button and waits 5 seconds to read the page, they only generate 0.2 RPS.

If your system is slow and takes 2 seconds to respond, a user can't make their next request until the first one finishes, which lowers your total RPS even if you have many users.


# Why "Turnstile Speed" (Ramp Up) is important:
Avoids "Shocking" the Server: By setting a ramp-up of 2 users/second, you are letting users in slowly. 
The server has time to allocate memory and open database connections gradually.

Finds the Breaking Point: If you ramp up slowly, you can watch your Locust graphs and say: "Oh look, the server was fine at 400 users, but the moment the 401st user entered, the response time spiked."

Realism: In the real world, it's very rare for 1,000 people to click a link at the exact same microsecond. They usually trickle in over a few minutes.







