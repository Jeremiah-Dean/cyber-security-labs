Lab Walkthrough: Exploiting Path-Based Web Cache Poisoning

1. Identify a Target Endpoint
•	Launched Burp’s embedded browser.
•	Navigated t o the lab-provided URL. 
•	Logged in using the credentials:
Username: wiener
Password: peter
•	Observed the response after login; notice that it included the API key for user wiener.
 
________________________________________
2. Find Path Mapping Discrepancy
•	Went to Proxy > HTTP history.
•	Located the GET /my-account request.
•	Right clicked the request and selected Send to Repeater.
Test #1: Arbitrary Path Segment
•	In Repeater, changed the path to /my-account/abc.
•	Sent the request.
•	Noticed that the response still contained the API key — showing that the server treated /my-account/abc the same as /my-account.
Test #2: Static File Extension
•	Modified the path to /my-account/abc.js.
 
•	Sent the request.
•	Noticed response headers:
o	X-Cache: miss
o	Cache-Control: max-age=30
•	Sent the same request again within 30 seconds.
•	Observed X-Cache: hit — confirmed that response was now served from the cache.
________________________________________
3. Craft and Deliver Exploit
•	Opened Go to exploit server in Burp’s browser.
 
•	In the exploit body, inserted the following JavaScript payload to redirect the victim:

<script>document.location="https://YOUR-LAB-ID.web-security-academy.net/my-account/wcd.js"</script>
•	Replaced YOUR-LAB-ID with the lab’s actual ID.
•	Clicked Deliver exploit to victim.
________________________________________
4. Retrieve API Key
•	Visited:
https://YOUR-LAB-ID.web-security-academy.net/my-account/wcd.js
•	Saw that the response included carlos’ API key.
 
•	Copied the key.
________________________________________
5. Submit Solution
•	Clicked Submit solution.
•	Pasted Carlos' API key.
•	Lab completed successfully.
 

