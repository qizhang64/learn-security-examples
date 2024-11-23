# Repudiation

The example demonstrates a vulnerability that can lead to repudiation by malicious users attempting to access the services provided by a server.

## Steps to reproduce

1. Install all dependencies

    `$ npm install`

2. Run the server __insecure.ts__.

3. Pretend to be a malicous user and interact with the services by sending requests from the browser.

4. Do you think your actions can be repudiated?

## For you to do

1. Briefly explain the vulnerability.
    Messages can be sent and retrieved without verifying the identity of the user. A malicious can access and send message anonymously and later says they never did it.
2. Briefly explain why the vulnerability is addressed in __secure.ts__.
    It adds authentication checks before allowing access to critical routes like /send-message and /get-messages. A logStream is used to write detailed log entries for each request and significant actions
3. Which design pattern is used in the secure version to address the vulnerability? Briefly explain how it works?
    It has a request logging middleware, which logs request with detailed URL, IP and timestamp.