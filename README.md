# How to run?

Requirements: 
- HackTheBox account for Openvpn connection file
- Docker & docker-compose

1. Download your ovpn file from HTB
2. Place it inside openvpn_client and edit openvpn_client/Dockerfile to reference your ovpn file
3. `docker-compose run box`

# Troubleshooting

`docker ps` to see if all 3 services are running (proxy, vpn, box)
`docker kill -s HUP <id of proxy container>` to restart after a config update
`docker exec -it <id of proxy container> tail -f /var/log/squid/access.log` to see access logs