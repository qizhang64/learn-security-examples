# Privilege Escalation

The example demonstrates a privilege escalation vulnerability and how to exploit it.

## Steps to reproduce

1. Install all dependencies

    `$ npm install`

2. Start the **insecure.ts** server

    `$ npx ts-node insecure.ts`

3. In the browser, send a GET request

    ```
        http://localhost:3000/send-form
    ```

4. Try different UserIds and see which one gives you authorized access to change the role of that user.

## For you to do

Answer the following:

1. Briefly explain the potential vulnerabilities in **insecure.ts**
    The system doesn't use session or tokens to authenticate users, and all relies on userId.
2. Briefly explain how a malicious attacker can exploit them.
    An attacker can forge a request with any userId and newRole to bypass the authentication and authorization checks.
3. Briefly explain the defensive techniques used in **secure.ts** to prevent the privilege escalation vulnerability?
    Use express-session to ensure only authenticated user with valid session cookies can access.