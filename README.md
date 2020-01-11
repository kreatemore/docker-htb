# Important

### Please read uwu

**This is a PoC, security was completely ignored.**

You're probably running

a) a probably very relaxed and maybe even outdated squid proxy to access HTB sites from your host

b) your "box" as root (which is probably great if someone wants to break out of your container)

Any PRs are welcome to tighten security/update stuff, or improvements of any kind!

# WTF is this?

This is an attempt to eliminate the need of running a complete Linux VM
just for doing some HTB chillaxing.

You can also read as "I didn't buy a mac to ask everyone why am I running Ubuntu on it".

# Notes

Your "box" comes with the minimum of the minimum (like curl & python3). You will have to use apt to install stuff, and
the volumes are not persistent yet, so expect loss of data if you stop all instances.

As root, your home folder (/root/) is mounted on your host, you can use that folder to
pass data between host/container & also what's there is persisted.

# How to run?

Requirements: 
- HackTheBox account for Openvpn connection file
- Docker & docker-compose

1. Download your ovpn file from HTB
2. Place it inside openvpn_client and edit openvpn_client/Dockerfile to reference your ovpn file
3. `docker-compose run box`
4. Connect your browser (host) to the web proxy @ 127.0.0.1:3128

# Troubleshooting

`docker ps` to see if all 3 services are running (proxy, vpn, box)

`docker kill -s HUP <id of proxy container>` to restart after a config update

`docker exec -it <id of proxy container> tail -f /var/log/squid/access.log` to see access logs
