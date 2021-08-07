# Think-Pi-Nano+ | Cluster General Apps

My list of apps discovered on:
 - https://github.com/awesome-selfhosted/awesome-selfhosted
 - https://www.reddit.com/r/selfhosted/
 - https://github.com/eagleusb/awesome-repositories

Every category of web app imaginable is covered with the links above. Build out your own portal for local (includes VPN) use and/or over the internet combined with SSO/2FA. A basic over the internet setup entails:
1. Installing an app and running it locally.
2. Adding the app location (IP and port) to a reverse proxy like Nginx as a location block. Users can expose their apps as a subdirectory (domain.com/app) or subdomain (app.domain.com), subdomain would need a TLS wildcart cert for the 2nd setup. 
3. Leveraging a feature on Nginx called auth_request on location blocks, lets sytem know which blocks require auth (granular as you want).
4. Use a front page organizer that leverages RBAC, IDp, SSO and 2FA that can tie in all your installed services locally into one interface. Example: https://github.com/causefx/Organizr
5. Open up port 443 for the IP where you will be passing inbound traffic (and/or IP and port number for VPN, recommend Wireguard).
 - Try to keep your management interfaces accessiblity tied to only local use (leveraging a VPN on the go).
6. Ensure you have a domain name, if you don't have a static WAN IP you will have to run a DDNS updater on the host or use built-in features (if available) at the router level.
7. If you don't want external users hitting your hosts directly, you can add an additional layer of protection through the use of a 3rd party CDN like Cloudflare. Once the CNAME is configured in Cloudflare, users will hit the Cloudflare service/IPs when visiting your domain. Then Cloudflare (acting as a distributed reverse proxy) will make a request down to your self-hosted reverse proxy which will then route the request to the appropiate service. Cloudflare offers many other features such as a WAF and handling of TLS certs, TLS would terminate once it hits the self-hosted reverse proxy (Nginx in our example, unless you are also running an internal CA). 
