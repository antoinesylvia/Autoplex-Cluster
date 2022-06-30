# Think-Pi-Nano+ | Cluster General Apps

Every category of web app imaginable is covered with the links below. Build out your own portal for local (includes VPN) use and/or over the internet combined with SSO/2FA. A basic *over the internet* setup entails:
1. Installing an app and running it locally on your network.
2. Ensure the user has a registered domain name, if the user doesn't have a static WAN IP then they'll have to run a DDNS updater on the host or use built-in features (if available) at the router level.
3. Add the web app location (IP and port) information to a reverse proxy like Nginx as a location block. Users can expose their apps as a subdirectory (domain.com/app) or subdomain (app.domain.com), subdomain would need a TLS wildcart cert for the 2nd setup. 
4. Leveraging a feature on Nginx called auth_request on location blocks, lets sytem know which blocks require auth (granular as you want). If not setup appropiately, location blocks that require auth validation, can be accessible without auth validation if nginx is exposed and port 443 is open.
5. Use a front page organizer that leverages IDp, RBAC, SSO and 2FA that can tie in all your installed services locally into one interface. Example: https://github.com/causefx/Organizr
6. Open up port 443 for the IP where you will be passing inbound traffic (and/or IP and port number for VPN, recommend Wireguard).
  - Note: Try to keep your management interfaces accessiblity tied to only local use (leveraging a VPN on the go), if not ensure 2FA is enabled.
7. If users don't want external people hitting their hosts directly, users can add an additional layer of protection through the use of a 3rd party CDN like Cloudflare. Once the CNAME is configured in Cloudflare, users will hit the Cloudflare service/IPs when visiting your domain (requires Cloudflare DDNS updater to run locally). Then Cloudflare (acting as a distributed reverse proxy) will make a request down to your self-hosted reverse proxy which will then route the request to the appropiate service. Cloudflare offers many other features such as a WAF and handling of TLS certs, TLS would terminate once it hits the self-hosted reverse proxy (Nginx in our example, unless the user are also running an internal CA).
  - Note: At the Nginx level, users can add a rule to only allow inbound traffic from known Cloudflare IPs. This can also be done more effectively at the router level instead if the feature is available.
  - Note: At the Cloudflare level, ensure Authenticated Origin Pulls is enabled. Helps validate traffic hitting a user's orgin server is coming 1st from Cloudflare (using a TLS cert)
-----------------------------
Popular apps (containerized) listed on this page, were discovered on:
 - https://github.com/awesome-selfhosted/awesome-selfhosted
 - https://github.com/sindresorhus/awesome
 - https://github.com/eagleusb/awesome-repositories
 - https://www.reddit.com/r/selfhosted/
 - https://boinc.berkeley.edu/projects.php

-----------------------------
# My Currated List 

AirDC++: Client for Advanced Direct Connect and Direct Connect networks. 
 - https://github.com/gangefors/docker-airdcpp-webclient
 - image: gangefors/airdcpp-webclient

AppRise: Allows you to send a notification to almost all of the most popular notification services available to us today such as: Telegram, Discord, Slack, Amazon SNS, Gotify, etc..
 - https://github.com/caronc/apprise
 - image: caronc/apprise:latest
      
Arewedown: Is a simple uptime monitoring system and dashboard. It is ideal for the home/self-hosting user who runs multiple services/networked devices on a private LAN, and who doesn't want the complexity of an enterprise-level monitoring system.
 - https://github.com/shukriadams/arewedown
 - image: shukriadams/arewedown

Aria2: Lightweight multi-protocol & multi-source command-line download utility. It supports HTTP/HTTPS, FTP, SFTP, BitTorrent and Metalink.
 - https://aria2.github.io/
 - image: vimagick/aria2

Audacity: Multi-track audio editor and recorder. Developed by a group of volunteers as open source.
 - https://github.com/audacity/audacity
 - image: ghcr.io/linuxserver/audacity
    
Autocompose:Generates a docker-compose yaml definition from a running container.
 - https://github.com/Red5d/docker-autocompose
 - image: red5d/docker-autocompose
 
Avidemux: Free and open-source software for non-linear video editing and transcoding multimedia files.
 - http://avidemux.sourceforge.net/
 - image: jlesage/avidemux

Bazarr: Companion application to Sonarr and Radarr. It manages and downloads subtitles based on your requirements.
 - https://github.com/morpheus65535/bazarr
 - image: ghcr.io/linuxserver/bazarr

Changedetection.io: Self-hosted change monitoring of web pages.
 - https://github.com/dgtlmoon/changedetection.io
 - image: dgtlmoon/changedetection.io

Chevereto: Image hosting software that allows you to create a beautiful and full-featured image hosting website on your own server. It's your hosting and your rules, so say goodbye to closures and restrictions.
 - https://github.com/Chevereto
 - image: ghcr.io/linuxserver/chevereto
   
Cloudflareddns: Cloudflare DDNS updater.
 - https://support.cloudflare.com/hc/en-us/articles/360020524512-Manage-dynamic-IPs-in-Cloudflare-DNS-programmatically
 - image: hotio/cloudflareddns

Code-server: VS Code in the browser.
 - https://github.com/cdr/code-server
 - image: linuxserver/code-server

Composerize: Turns docker run commands into docker-compose files!
 - https://github.com/magicmark/composerize
 - image: icedream/composerize
    			
Cyberchef: #The Cyber Swiss Army Knife - a web app for encryption, encoding, compression and data analysis.
 - https://github.com/gchq/CyberChef
 - image: 4nxio/cyberchef:latest

Dizquetv: Create live TV channels from your own media. Access the streams using the simulated HDHomerun tuner or the generated M3U URl.
- https://github.com/vexorian/dizquetv
- image: vexorian/dizquetv:latest
		
Docker-bench-security: The Docker Bench for Security is a script that checks for dozens of common best-practices around deploying Docker containers in production.
 - https://github.com/docker/docker-bench-security
 - image: docker/docker-bench-security

Docsassemble: A free, open-source expert system for guided interviews and document assembly, based on Python, YAML, and Markdown. 
 - https://docassemble.org/docs/docker.html#tocAnchor-1-10-3
 - image: jhpyle/docassemble  

Dokuwiki: Wiki application licensed under GPLv2 and written in the PHP programming language. 
 - https://www.dokuwiki.org/dokuwiki
 - image: ghcr.io/linuxserver/dokuwiki

Draw.io: Diagrams.net is free online diagram software for making flowcharts, process diagrams, org charts, UML, ER and network diagrams.
 - https://github.com/fjudith/docker-draw.io
 - image: jgraph/draw.io
		
Duplicacy: Backs up your files to many cloud storages with client-side encryption and the highest level of deduplication.
 - https://github.com/gilbertchen/duplicacy
 - image: hotio/duplicacy
 
Eclipse Mosquitto: Open source MQTT broker.
 - https://mosquitto.org/
 - image: eclipse-mosquitto
		
Edumeet: Multiparty web-meetings using mediasoup and WebRTC.
 - https://github.com/edumeet/edumeet
 - image: edumeet/edumeet:${TAG}
   
FileBot: Ultimate tool for renaming and organizing your movies, TV shows and Anime.
 - https://www.filebot.net/
 - image: jlesage/filebot
 
FileZilla Client: Fast and reliable cross-platform FTP, FTPS and SFTP client with lots of useful features and an intuitive graphical user interface.
- https://filezilla-project.org
- image: ghcr.io/linuxserver/filezilla

Firefox: Free and open-source web browser developed by the Mozilla Foundation.
- https://www.mozilla.org/en-US/firefox/
- image: ghcr.io/linuxserver/firefox

Fleet: Provides an online web interface which displays a set of maintained images from one or more owned repositories.
 - https://github.com/linuxserver/fleet
 - image: ghcr.io/linuxserver/fleet

Folding@home - Distributed computing project aimed to help scientists develop new therapeutics for a variety of diseases by the means of simulating protein dynamics. This includes the process of protein folding and the movements of proteins, and is reliant on simulations run on volunteers' personal computers.
 - https://foldingathome.org/?lng=en-US
 - image: ghcr.io/linuxserver/foldingathome
   
Freshrss: FreshRSS is a self-hosted RSS feed aggregator.
 - https://github.com/FreshRSS/FreshRSS
 - image: ghcr.io/linuxserver/freshrss
		
Fireflyiii: A personal finances manager.
 - https://github.com/firefly-iii/firefly-iii
 - image: jc5x/firefly-iii:latest

Gaps: Searches through your Plex Server or local folders for all movies, then queries for known movies in the same collection. If those movies don't exist in your library, Gaps will recommend getting those movies, legally of course.
 - https://github.com/JasonHHouse/gaps
 - image: housewrecker/gaps

Gotify: A simple server for sending and receiving messages in real-time per WebSocket. Replaces Pushbullet. 
 - https://github.com/gotify/server
 - image: gotify/server
		
Guacamole: Clientless remote desktop gateway. It supports standard protocols like VNC, RDP, and SSH. We call it clientless because no plugins or client software are required. Thanks to HTML5, once Guacamole is installed on a server, all you need to access your desktops is a web browser.
 - https://github.com/apache/guacamole-server
 - image: ghcr.io/linuxserver/guacd
 
Guora: A self-hosted Quora like web application.
 - https://github.com/meloalright/guora
 - image: meloalright/guora:beta2
		
Grafana: Multi-platform open source analytics and interactive visualization web application. It provides charts, graphs, and alerts for the web when connected to supported data sources.
 - https://grafana.com/
 - image: grafana/grafana
		
Grav:Modern, Crazy Fast, Ridiculously Easy and Amazingly Powerful Flat-File CMS.
 - https://github.com/getgrav/grav
 - image: grav:latest
		
Grocy: ERP beyond your fridge - grocy is a web-based self-hosted groceries & household management solution for your home.
 - https://github.com/grocy/grocy
 -image: ghcr.io/linuxserver/grocy

Headphones: Automatic music downloader for SABnzbd.
 - https://github.com/rembo10/headphones
 - image: ghcr.io/linuxserver/headphones

Heimdall: An Application dashboard and launcher.
 - https://github.com/linuxserver/Heimdall
 - image: ghcr.io/linuxserver/heimdall

Home Assistant: Open source home automation that puts local control and privacy first. 
 - https://github.com/home-assistant/core
 - image: ghcr.io/linuxserver/homeassistant

Huginn: Create agents that monitor and act on your behalf.
 - https://github.com/huginn/huginn
 - image: huginn/huginn

Influxdb: Open-source time series database developed by InfluxData.
 - https://github.com/influxdata/influxdb
 - image: influxdb

Jackett: API Support for your favorite torrent trackers.
 - https://github.com/Jackett/Jackett
 - image: ghcr.io/linuxserver/jackett
		
Jdownloader-2: Open-source download management tool.
 - https://jdownloader.org/download/index
 - image: jlesage/jdownloader-2
		
Jellyfin: Suite of multimedia applications designed to organize, manage, and share digital media files to networked devices.
 - https://github.com/jellyfin/jellyfin
 - image: ghcr.io/linuxserver/jellyfin

Joplin: Open source note taking and to-do application (replaces Evernote).
- https://github.com/laurent22/joplin
- image: joplin/server

Kavita: Fast, feature rich, cross platform reading server. Built with a focus for manga and the goal of being a full solution for all your reading needs. Setup your own server and share your reading collection with your friends and family.
 - https://github.com/Kareadita/Kavita
 - image: kizaing/kavita:latest

Lazylibrarian: Program to follow authors and grab metadata for all your digital reading needs.
 - https://lazylibrarian.gitlab.io/
 - image: ghcr.io/linuxserver/lazylibrarian

Lidarr: Looks and smells like Sonarr but made for music.
 - https://github.com/Lidarr/Lidarr
 - image: ghcr.io/linuxserver/lidarr
		
Leantime: Open source project management system to make your ideas reality.
 - https://leantime.io/
 - image: leantime/leantime:latest

Mariadb: Community-developed, commercially supported fork of the MySQL relational database management system, intended to remain free and open-source software under the GNU General Public License.
 - https://mariadb.org/
 - image: ghcr.io/linuxserver/mariadb
  
Mellow: Can communicate with several APIs like Ombi, Sonarr, Radarr and Tautulli which are related to home streaming to use those services directly in your Discord client.
 - https://github.com/v0idp/Mellow 
 - image: voidp/mellow

Monitoror: Unified monitoring wallboard — Light, ergonomic and reliable monitoring for anything.
 - https://github.com/monitoror/monitoror
 - image: tomdesinto/monitoror
		
Monicaapp: Open source personal CRM.
 - https://www.monicahq.com/
 - image: monica

Moviematch: Have you ever spent longer deciding on a movie than it'd take to just watch a random movie? This is an app that helps you and your friends pick a movie to watch from a Plex server.
 - https://github.com/LukeChannings/moviematch
 - image: lukechannings/moviematch
		
Mozilla-tts: Deep learning for Text to Speech.
 - https://github.com/mozilla/TTS
 - image: synesthesiam/mozilla-tts

Mylar: An automated Comic Book downloader (cbr/cbz) for use with SABnzbd, NZBGet and torrents.
 - https://github.com/evilhero/mylar
 - image: ghcr.io/linuxserver/mylar
		
Mysql: Open source relational database.
 - https://github.com/mysql/mysql-server
 - image: mysql

MongoDB: Source-available cross-platform document-oriented database program.
 - https://www.mongodb.com/ 
 - image: mongo:4.2

Netmaker: Connect any computers together over a secure, fast, private network, and manage multiple networks from a central server.
 - https://github.com/gravitl/netmaker
 - image: gravitl/netmaker

Neko: A self hosted virtual browser (rabb.it clone) that runs in docker.
 - https://github.com/nurdism/neko
 - image: nurdism/neko:chromium
		
Nextcloud: Suite of client-server software for creating and using file hosting services. It is enterprise-ready with comprehensive support options.Nextcloud is a suite of client-server software for creating and using file hosting services. It is enterprise-ready with comprehensive support options.
 - https://github.com/nextcloud
 - image: ghcr.io/linuxserver/nextcloud
		
nginx: Reverse Proxy.
 - https://github.com/nginx/nginx
 - image: ghcr.io/linuxserver/nginx

nginx-proxy:
    image: jwilder/nginx-proxy
	  
nginxproxymanagerzapp:
    image: jc21/nginx-proxy-manager:latest

nginx-ui: Nginx UI allows you to access and modify the nginx configurations files without cli. 
 - https://github.com/schenkd/nginx-ui
 - image: nginx-ui:latest
   
Node-red: Low-code programming for event-driven applications.
 - https://github.com/node-red/node-red
 - image: nodered/node-red
 
Notifiarr: Enables content requests from Media Bot in your Discord Server. It also provides reports for Plex usage and system health.
 - https://notifiarr.com/
 - image: golift/notifiarr
	
Nowshowing: #Generates an email and web page of Plex recently added content.
 - https://github.com/ninthwalker/NowShowing
 - image: ninthwalker/nowshowing:v2	

Nzbhydra2: Usenet meta search.
 - https://github.com/theotherp/nzbhydra2
 - image: ghcr.io/linuxserver/nzbhydra2

Organizr: HTPC/Homelab Services Organizer - Written in PHP.
 - https://github.com/causefx/Organizr
 - image: ghcr.io/linuxserver/organizr

Octoprint: Open source 3D printer controller application, which provides a web interface for the connected printers.
 - https://github.com/OctoPrint/OctoPrint-Pushbullet
 - image: octoprint/octoprint

Ombi: Friendly media request tool, automatically syncs with your media servers! Don't worry, it's grandma friendly, and more importantly; has wife approval certification. 
 - https://github.com/Ombi-app/Ombi
 - image: ghcr.io/linuxserver/ombi
		
Openspeedtest: Pure HTML5 Network Performance Estimation Tool.
 - https://github.com/openspeedtest/Speed-Test
 - image: openspeedtest/latest

Overseerr: Request management and media discovery tool for the Plex ecosystem.
 - https://github.com/sct/overseerr
 - image: sctx/overseerr
		
Pasta: Audio & Subtitle Track Changer for Plex.
 - https://github.com/cglatot/pasta
 - image: cglatot/pasta

Peppermint: Ticket Management System
 - https://github.com/Peppermint-Lab/peppermint
 - image: pepperlabs/peppermint
		
Petio: Third party companion app available to Plex server owners to allow their users to request, review and discover content. 
 - https://github.com/petio-team/petio
 - image: ghcr.io/petio-team/petio:latest
		
Photoprism: Open-Source Photo Management powered by Go and Google TensorFlow.
 - https://github.com/photoprism/photoprism
 - image: photoprism/photoprism:latest

Phpipam-web: Open source IP address management.
 - https://github.com/phpipam/phpipam
 - image: phpipam/phpipam-www:latest

Pihole: Network-wide Ad Blocking.
 - https://github.com/pi-hole/pi-hole
 - image: pihole/pihole:latest

Plex: Organizes video, music and photos from personal media libraries and streams them to smart TVs, streaming boxes and mobile devices. 
 - https://plex.tv
 - image: ghcr.io/linuxserver/plex

Plex-library-cleaner: A simple UI to help find and delete duplicate and sample files from your Plex server.
 - https://github.com/se1exin/Plex-Library-Cleaner
 - image: selexin/plex-library-cleaner:latest
		
Plexarr Simple CLI tool to fix Plex library matches according to Sonarr/Radarr.
 - https://github.com/l3uddz/plexarr
 - image: hotio/plexarr		
		
Posterr: Media display software for Plex, Sonarr and Radarr.
 - https://github.com/petersem/posterr
 - image: petersem/posterr

Projectsend: Open source software that lets you share files with your clients, focused on ease of use and privacy. It supports clients groups, system users roles, statistics, multiple languages, detailed logs... and much more! 
 - https://github.com/projectsend/projectsend
 - image: ghcr.io/linuxserver/projectsend

Prowlarr: Indexer manager/proxy built on the popular arr .net/reactjs base stack to integrate with your various PVR apps.
 - https://github.com/Prowlarr/Prowlarr
 - image: hotio/prowlarr

Portainer: Making Docker and Kubernetes management easy. 
 - https://github.com/portainer/portainer
 - image: portainer/portainer
		
Podgrab: Self-hosted podcast manager/downloader/archiver tool to download podcast episodes as soon as they become live with an integrated player. 
 - https://github.com/akhilrex/podgrab
 - image: akhilrex/podgrab

Postgres: Open-source relational database management system emphasizing extensibility and SQL compliance.
 - https://www.postgresql.org/
 - image: postgres

Pwndrop: Self-deployable file hosting service for red teamers, allowing to easily upload and share payloads over HTTP and WebDAV. 
 - https://github.com/kgretzky/pwndrop
 - image: ghcr.io/linuxserver/pwndrop

Pyload: The free and open-source Download Manager written in pure Python. 
 - https://github.com/pyload/pyload
 - image: ghcr.io/linuxserver/pyload

Qbittorrent with Flood UI: BitTorrent client. 
 - https://github.com/qbittorrent/qBittorrent
 - image: hotio/qflood
		
Radarr: A fork of Sonarr to work with movies à la Couchpotato. 
 - https://github.com/Radarr/Radarr
 - image: ghcr.io/linuxserver/radarr

Readarr: Book Manager and Automation (Sonarr for Ebooks).
 - https://github.com/Readarr/Readarr
 - image: hotio/readarr:nightly

Redis: In-memory data structure store, used as a distributed, in-memory key–value database, cache and message broker, with optional durability. 
 - https://github.com/redis/redis
 - image: redis

Remotely: A remote control and remote scripting solution, built with .NET 5, Blazor, SignalR Core, and WebRTC.
- https://github.com/lucent-sea/remotely
- image: translucency/remotely:latest
	
Resilio-sync: Server Synchronization in Real-Time.
 - https://www.resilio.com/
 - image: ghcr.io/linuxserver/resilio-sync

Retroarch-web: Frontend for emulators, game engines and media players
 - https://www.libretro.com/
 - image: inglebard/retroarch-web

Requestrr: Chatbot used to simplify using services like Sonarr/Radarr/Ombi via the use of chat. Current platform is Discord only, but the bot was built around the ideology of quick adaptation for new features as well as new platforms. 
 - https://github.com/darkalfx/requestrr
 - image: darkalfx/requestrr
		
Rhasspy: Offline voice assistant.
 - https://github.com/rhasspy/rhasspy
 - image: rhasspy/rhasspy

Sabnzbd: The automated Usenet download tool.
 - https://github.com/sabnzbd/sabnzbd
 - image: ghcr.io/linuxserver/sabnzbd

Screego: Screen sharing for developers. 
 - https://github.com/screego/server
 - image: screego/server:1.0.1

Scrutiny: Hard Drive S.M.A.R.T Monitoring, Historical Trends & Real World Failure Thresholds. This a omnibus image, containing both the webapp server (frontend & api) as well as the S.M.A.R.T metric collector. 
 - https://github.com/analogj/scrutiny
 - image: analogj/scrutiny	

Serverstatus: Display and monitor your servers statistics in a beatiful way.
 - https://github.com/BotoX/ServerStatus
 - image: cppla/serverstatus

SnipeIT:#A free open source IT asset/license management system.
 - https://github.com/snipe/snipe-it
 - image: ghcr.io/linuxserver/snipe-it:latest

Sonarr: Smart PVR for newsgroup and bittorrent users. 
 - https://github.com/Sonarr/Sonarr
 - image: ghcr.io/linuxserver/sonarr
		
Sqlitebrowser: Official home of the DB Browser for SQLite (DB4S) project. 
 - https://github.com/sqlitebrowser/sqlitebrowser
 - image: ghcr.io/linuxserver/sqlitebrowser
  
Statping: Status Page for monitoring your websites and applications with beautiful graphs, analytics, and plugins. Run on any type of environment. 
 - https://github.com/statping/statping
 - image: statping/statping:dev

Subspace: A simple WireGuard VPN server GUI.
 - https://github.com/subspacecloud/subspace
 - image: subspacecloud/subspace:latest

Synclounge: Open Source Continuous File Synchronization.
 - https://github.com/syncthing/syncthing
 - image: ghcr.io/linuxserver/synclounge
   
Syncthing: Open Source continuous file syncronization.
 - https://github.com/syncthing/syncthing
 - image: ghcr.io/linuxserver/syncthing
		
Shynet: Modern, privacy-friendly, and detailed web analytics that works without cookies or JS. 
 - https://github.com/milesmcc/shynet
 - image: milesmcc/shynet:latest
 
SSHtron: Play Tron over SSH.
 - https://github.com/zachlatta/sshtron
 - image: sshtron
 
TaskCafe: Kanban board.
 - https://github.com/JordanKnott/taskcafe
 - taskcafe/taskcafe

		
Taisun: Application for a Docker enabled device with an emphasis on providing a web based interface for managing a single server. 
 - https://github.com/Taisun-Docker/taisun
 - image: ghcr.io/linuxserver/taisun

Tautulli: A Python based monitoring and tracking tool for Plex Media Server. 
 - https://github.com/Tautulli/Tautulli
 - image: ghcr.io/linuxserver/tautulli
		
Tdarr: Distributed transcode automation using FFmpeg/HandBrake + Audio/Video library analytics + video health checking (Windows, macOS, Linux & Docker).
 - https://github.com/HaveAGitGat/Tdarr
 - image: haveagitgat/tdarr
  
Telegraf: The plugin-driven server agent for collecting & reporting metrics. 
 - https://github.com/influxdata/telegraf
 - image: telegraf

Traktarr: Script to add new series & movies to Sonarr/Radarr based on Trakt lists. 
 - https://github.com/l3uddz/traktarr#installation
 - image: eafxx/traktarr
     
Ubooquity: Read your ebooks and comics on your favorite device, wherever you go.
 - http://vaemendis.net/ubooquity/
 - image: ghcr.io/linuxserver/ubooquity
		
Unbound: Validating, recursive, and caching DNS resolver. 
 - https://github.com/NLnetLabs/unbound
 - image: mvance/unbound:latest

Unpackerr: Extracts downloads for Radarr, Sonarr, Lidarr, Readarr - Deletes extracted files after import.
 - https://github.com/davidnewhall/unpackerr
 - image: hotio/unpackerr

Uptime-kuma: A fancy self-hosted monitoring tool. 
 - https://github.com/louislam/uptime-kuma
 - image: louislam/uptime-kuma

Watchtower: Updates containers.
- https://github.com/containrrr/watchtower
- image: v2tec/watchtower

Wikijs: The most powerful and extensible open source Wiki software.
 - https://github.com/Requarks/wiki
 - image: ghcr.io/linuxserver/wikijs

Wireguard: Modern and Fast VPN.
 - https://github.com/WireGuard
 - image: ghcr.io/linuxserver/wireguard

Whoogle-search: A self-hosted, ad-free, privacy-respecting metasearch engine. 
 - https://github.com/benbusby/whoogle-search
 - image: benbusby/whoogle-search

XOWA: Free and open-source application written primarily in Java by anonymous developers and is intended for users who wish to run their own copy of Wikipedia, or any other compatible Wiki offline or without an internet connection.
 - http://xowa.org/
 - image: quantumobject/docker-xowa

Youtubedl-Material: Self-hosted YouTube downloader built on Material Design. 
 - https://github.com/Tzahi12345/YoutubeDL-Material
 - image: tzahi12345/youtubedl-material:latest

Youtube-DL: Command-line program to download videos from YouTube.com and other video sites. (replacing with YT-DLP soon)
 - https://github.com/ytdl-org/youtube-dl
 - image: kmb32123/youtube-dl-server

Yet Another Aria2 Webui (Yaaw): Aria2 Webui. 
 - https://github.com/binux/yaaw
 - image: aria2-yaaw:latest

Zammad: Web based open source helpdesk/customer support system. 
 - https://github.com/zammad/zammad
 - image: zammed/zammed
