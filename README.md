# Installation
1. Rename config.example.yaml -> config.yaml
2. Set up password
3. Add certificate
```bash
openssl req -x509 -nodes -newkey rsa:2048 \
-keyout ./cert/server.key \
-out ./cert/server.crt \
-days 3650 \
-subj "/CN=YOUR_SERVER_IP" \
-addext "subjectAltName=IP:YOUR_SERVER_IP"
```
4. Run docker container
```bash
docker-compose up -d
```
5. Connection link
```
hysteria2://<password>@<ip>:443?obfs=salamander&sni=<domain>&insecure=1#<Name>
```
