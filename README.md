# bug_report001
Bug report for site : platform.cryptopolice.com

Hi  Team,  Please  find  the  vulnerability  details  below:
  
Vulnerability:  
Missing, Misconfiguration (weakness) X-Frame-Options Response 

Type: Attack

Summary: The remote server does not set the X-Frame-Options in
its responses, this can be used to cause a ClickJacking attack. 

Description:
Clickjacking is when an attacker uses multiple transparent or opaque layers 
to trick a user into clicking on a button or link on another page when they 
were intending to click on the the top level page. Thus, the attacker is "hijacking" 
clicks meant for their page and routing them to another page, most likely owned by 
another application, domain, or both.

Fix :
There are two main ways to prevent clickjacking:
⚫ Sending the proper X-Frame-Options HTTP response headers that instruct the browser to not allow framing from other domains
⚫ Employing defensive code in the UI to ensure that the current frame is the most top level window

The X-Frame-Options HTTP response header can be used to indicate whether or not a browser should
be allowed to render a page in a <frame>,<iframe> or <object> . Sites can use this to avoid clickjacking attacks,
by ensuring that their content is not embedded into other sites.
The X-Frame-Options header can be used to control whether a page can be placed in an IFRAME.
Because the Framesniffing technique relies on being able to place the victim site in an IFRAME,
a web application can protect itself by sending an appropriate X-Frame-Options header.

There are three possible values for X-Frame-Options:
⚫ DENY, The page cannot be displayed in a frame, regardless of the site attempting to do so.
⚫ SAMEORIGIN, The page can only be displayed in a frame on the same origin as the page itself.
⚫ ALLOW-FROM uri, The page can only be displayed in a frame on the specified origin.
