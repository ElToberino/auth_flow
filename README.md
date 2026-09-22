# Spotify Auth Proxy for ESP Microcontrollers

This repository hosts a static, client-side proxy page used to securely authenticate Tobers Multidisplay and Tobers Multidisplay XXL with the Spotify API.

## Why is this needed?
Due to Spotify's security policies, it is no longer possible to use a local, unencrypted IP address (like `http://192.168.x.x`) as a direct redirect URI for OAuth authentication. This proxy acts as a secure HTTPS bridge: it receives the authentication code from Spotify and passes it directly to your local device on your home network.

## Privacy & Security (Privacy by Design)
This proxy is designed with strict privacy in mind:
- **No Data Collection:** The entire process runs locally in your browser. No personal data, IP addresses, or authentication tokens are ever sent to, processed, or stored by the owner of this repository.
- **No Tracking:** This page uses no tracking scripts and no cookies.

For more details, please check the [Privacy Policy](privacy.html) included in this repository.
