# Server-Side Parameter Pollution Lab

**Platform:** PortSwigger Web Security Academy  
**Category:** Access Control / Server-side Input Handling  
**Tool:** Burp Suite

## Objective

Exploit server-side parameter pollution to retrieve a password reset token and gain administrator access.

---

## Steps Taken

1. Triggered password reset for `administrator`
2. Observed `/forgot-password` request and JS file revealing `reset_token`
3. Used Repeater to test username variations and inject encoded parameters
4. Brute-forced server-recognized parameters using Intruder
5. Discovered `reset_token` and used it to reset admin password
6. Logged in and deleted user `carlos` to solve the lab

---

## Key Takeaways

- Improper parsing of parameters can be exploited using encoded characters like `%26` (`&`) and `%23` (`#`)
- Field injection using `field=reset_token` provided sensitive token
- Server-side validation must not rely on client-side behavior

---

## Outcome

- Successfully retrieved the password reset token
- Gained access to the admin account
- Deleted target user to solve the lab

---

## Screenshot
