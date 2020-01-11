# How to run?

Requirements: 
- HackTheBox account for Openvpn connection file
- Docker & docker-compose

1. Download your ovpn file from HTB
2. Place it inside openvpn_client and edit Dockerfile to reference your ovpn file
3. `docker-compose run box`