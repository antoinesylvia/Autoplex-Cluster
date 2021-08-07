# Think-Pi-Nano+ | Cluster General Apps

My list of apps discovered on:
 - https://github.com/awesome-selfhosted/awesome-selfhosted
 - https://www.reddit.com/r/selfhosted/
 - https://github.com/eagleusb/awesome-repositories

-----------------------------
Every category of web app imaginable is covered with the links above. Build out your own portal for local (includes VPN) use and/or over the internet combined with SSO/2FA. A basic *over the internet* setup entails:
1. Installing an app and running it locally on your network.
2. Ensure the user has a registered domain name, if the user doesn't have a static WAN IP then they'll have to run a DDNS updater on the host or use built-in features (if available) at the router level.
3. Add the web app location (IP and port) information to a reverse proxy like Nginx as a location block. Users can expose their apps as a subdirectory (domain.com/app) or subdomain (app.domain.com), subdomain would need a TLS wildcart cert for the 2nd setup. 
4. Leveraging a feature on Nginx called auth_request on location blocks, lets sytem know which blocks require auth (granular as you want). If not setup appropiately, location blocks that require auth validation, can be accessible without auth validation if nginx is exposed and port 443 is open.
5. Use a front page organizer that leverages IDp, RBAC, SSO and 2FA that can tie in all your installed services locally into one interface. Example: https://github.com/causefx/Organizr
6. Open up port 443 for the IP where you will be passing inbound traffic (and/or IP and port number for VPN, recommend Wireguard).
---->Try to keep your management interfaces accessiblity tied to only local use (leveraging a VPN on the go), if not ensure 2FA is enabled.
7. If users don't want external people hitting their hosts directly, users can add an additional layer of protection through the use of a 3rd party CDN like Cloudflare. Once the CNAME is configured in Cloudflare, users will hit the Cloudflare service/IPs when visiting your domain (requires Cloudflare DDNS updater to run locally). Then Cloudflare (acting as a distributed reverse proxy) will make a request down to your self-hosted reverse proxy which will then route the request to the appropiate service. Cloudflare offers many other features such as a WAF and handling of TLS certs, TLS would terminate once it hits the self-hosted reverse proxy (Nginx in our example, unless the user are also running an internal CA).
---->At the Nginx level, users can add a rule to only allow inbound traffic from known Cloudflare IPs. This can also be done more effectively at the router level instead if the feature is available.
---->At the Cloudflare level, ensure Authenticated Origin Pulls is enabled. Helps validate traffic hitting a user's orgin server is coming 1st from Cloudflare (using a TLS cert)

