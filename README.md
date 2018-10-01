# Web App Security Workflow #

This piece of writing is mainly for getting into Web Security and also approaching various CTF challenges. I've been playing fairly a decent amount of CTF's in last few years and have had spent time unnecessarily on many of the easy sides just because I was not looking at the way it was supposed to be and also because of lesser understanding of how the application works.

I've heard from most of the people that Web based challenges in CTF's involves a lot of guessing which I've felt isn't the case simply because there are two ways to approach a problem, either by understanding what happens or blindly going through the whole application. Here, this piece of article would try to cover how to be good at Web exploitation from CTF point of view and also how to attempt challenges.


## Getting into Security ##

Assuming the person has a basic understanding of PHP/MySQL and JS, rest all that comes up, one can learn on the course!

1) SQL Injection:
    1) [Source Code](https://github.com/Audi-1/sqli-labs)
    2) [YouTube Video](https://www.youtube.com/playlist?list=PLkiAz1NPnw8qEgzS7cgVMKavvOAdogsro)

2) Cross Site Scripting:
    1) This with enough and more hands-on, one will get a better understanding. A few wargame websites will be listed below.
    2) A few good videos; [XSS Protection Bypass](https://www.youtube.com/watch?v=TKn5qdti66c), [Bypassing Modern WAF's Exemplified At XSS by Rafay Baloch](https://www.youtube.com/watch?v=dWLpw-7_pa8), [Revisiting XSS Sanitization](https://www.youtube.com/watch?v=LLtOJNeMp7c)

## Wargames ##
Practicing as much as you can is the key. There are a few websites, ordered in terms of difficulty!

1) [RootMe](https://www.root-me.org/wargame?lang=en)
2) [RingZer0team](https://ringzer0team.com/)
3) [Tasteless](http://chall.tasteless.eu/)
4) [Websec](https://websec.fr/)
5) [Stypr](https://chall.stypr.com/)

### A few others for XSS: ###
1) [alert(1)](https://alf.nu/alert1)
2) [prompt(1)](http://prompt.ml/0)

## Approaching a CTF challenge ##
The following approach is my methodology and feel free to modify it the way you would like to!

*Step 1* is to do a good recon, if possible automate. Those include,

    1) HTML Source
    2) robots.txt
    3) HTTP Response headers (can fetch the server details)
    4) Cookies
    5) git, svn, htaccess

Next important thing is to understand how the application works and would be good to keep notes about what you are finding.

Find which language is being used at the backend, what server is being used. One way to determine this is by requesting for arbitrary common paths such as, `index.php`, `index.html` etc. Sometimes, [Wappalyzer](https://chrome.google.com/webstore/detail/wappalyzer/gppongmhjkpfnbhagpmjfkannfbllamg?hl=en) can give you what you are looking for now. If it is a python backend, mostly it would be SSTI rather than something else which is more common for PHP apps.

The arbitrary common paths could also leak out information about the backend of the app from the `404` pages which would come handy.

After going through all these doesn't give out any information, we can assume that the vulnerability exist somewhere else and sometimes the `CSS` files can reveal out information by the class names used. If at all a class like `login` is being used, we can assume that a `login` page exist and then move ahead.

## Summarising ##

Definitely the more CTF's you play, more quicker you would understand. At this point, we should have a decent understanding of how the `Backend`, `Web Application workflow`, `Different paths`, `Different directories` and `Headers` are.  
