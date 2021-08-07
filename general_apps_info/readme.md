# Think-Pi-Nano+ | Cluster General Apps

My list of apps discovered on:
 - https://github.com/awesome-selfhosted/awesome-selfhosted
 - https://www.reddit.com/r/selfhosted/
 - https://github.com/eagleusb/awesome-repositories

Every category of web app imaginable is covered with the links above. Build out your own portal for local (includes VPN) use and/or over the internet combined with SSO/2FA. A basic over the internet setup entails:
1. Installing an app and running it locally.
2. Adding the app location (IP and port) to a reverse proxy like Nginx as a location block. Users can expose their apps as a subdirectory (domain.com/app) or subdomain (app.domain.com), subdomain would need a TLS wildcart cert for the 2nd setup. 
3. Leveraging a feature on Nginx called auth_request on location blocks, lets sytem know which blocks require auth (granular as you want).
4. Use a front page organizer that leverages RBAC, IDp, SSO and 2FA that can tie in all your installed services locally into one interface: https://github.com/causefx/Organizr
5. Open up port 443 for the IP where you will be passing inbound traffic (and/or IP and port number for VPN, recommend Wireguard).
6.
