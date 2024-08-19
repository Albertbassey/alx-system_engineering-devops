0x19-postmortem

issues in accessing account

Duration:
To resolve the problem it took 4 hours from 14:00 to 18:00 WAT

Impact:
I was stuck to the ghost mode model and couldn't log into my web app and few users were affected by this bug

Root cause and resolution:
When I attempt to enhance security, I add a more complex login method to the website's backend. When someone tries to log in, an encrypted code is generated and sent to the server. The server decrypts it and then re-encrypts it before sending it back to the client. If the client is unable to decrypt it, the login fail; otherwise, the process continues.

When I tried to write some code, I made a few mistakes. As a result, when the server tried to create the encrypted code using the decrypted information sent from the client, it also made some errors because of the error in my code.

I worked on it and made the server to encrypt correctly. By doing some updates, I made it work properly.

Measures against such problem in future:
Always keep an eye on your servers to ensure they are running properly
Have extra back-up servers to prevent your program fro completely going offline during an issue
