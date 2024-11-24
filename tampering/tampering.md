# Tampering

This example demonstrates tampering through script injection.

## Steps to reproduce

1. Install all dependencies

    `npm install`

2. Start the **insecure.ts** server

    `npx ts-node insecure.ts`

3. In the browser, type a potentially malicious script in the name field of the form

    ```
        <script> document.body.innerHTML = "<a href='https://google.com'> Gotcha </a>"</script>
    ```

4. Do you see the potentially malicious hyperlink being injected into the form?

## For you to do

Answer the following:

1. Briefly explain the potential vulnerabilities in **insecure.ts**
    User inputs can be untrusted. req.body.name.trim() is directly used in dynamic HTML without sanitization.
2. Briefly explain how a malicious attacker can exploit them.
    An attacker can send a fake link like <a href="http://malicious-site.com">Click here</a>, which displays a malicious site, tricking users to click it.
3. Briefly explain why **secure.ts** does not have the same vulnerabilties?
    It uses escapeHTML to sanitize user inputs, transforming all scripts to strings.