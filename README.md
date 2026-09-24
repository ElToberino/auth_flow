## Spotify Authentication Proxy for Tobers Multidisplay

This repository hosts a static, client-side proxy page used to securely authenticate Tobers Multidisplay and Tobers Multidisplay XXL with the Spotify API.<br>
<br>

**Why is this needed?**<br>
Spotify uses [OAUTH 2.0](https://oauth.net/articles/authentication/) for the authentication with its API.<br>
During the authentication process - after the login to Spotify - the user is redirected back to the ESP where the rest of the process takes place. This redirection is done via a *callback address*.<br>
In my previous Multidisplay versions this was done by defining *`http://esp.local`* as callback address. This worked fine until Spotify changed its security policies: It is no longer possible to use a local, unencrypted IP address as a direct redirect URI. That change crashed my well-working auth flow, but I found a simple solution. As the address *`http://127.0.0.1`* is still allowed I took this one as callback address being aware that this local address scheme does not work on ESPs. But there was a simple workaround for that: Of course the redirection caused an error message in the browser, but all the relevant data was still in the address bar; you just had to replace the *`127.0.0.1`* with the local ESP IP and keep the rest - and everything worked fine. <br>
As I still missed the former, smooth authentication flow, I supposed that there must be a possibility to do this simple replacing step in an automatic way. With a little help from AI, this proxy site was born as the solution: It acts as a secure HTTPS bridge: it receives the authentication code from Spotify and passes it directly to your local device on your home network.
Just take a look at index.html and you will see how (simple) it works.<br>
<br>

**Privacy & Security** (Privacy by Design)<br>
This proxy is designed with strict privacy in mind:
- *No Data Collection:* The entire process runs locally in your browser. No personal data, IP addresses, or authentication tokens are ever sent to, processed, or stored by the owner of this repository.
- *No Tracking:* This page uses no tracking scripts and no cookies.

For more details, please check the [Privacy Policy](privacy.html) included in this repository.
