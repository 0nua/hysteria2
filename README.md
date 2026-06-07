# Installation
1. Rename config.example.yaml -> config.yaml
2. Set up password
3. Generate certificate and update config
```bash
export DEDYN_TOKEN="your-token-here"
export DEDYN_NAME="domain.dedyn.io"

acme.sh --issue --dns dns_desec -d domain.dedyn.io --server letsencrypt

Then install:
acme.sh --install-cert -d domain.dedyn.io \
  --cert-file /cert/server.crt \
  --key-file /cert/server.key
```
4. Run docker container
```bash
docker-compose up -d
```
5. Connection link
```
hysteria2://<password>@<ip|domain>:<port>?obfs=salamander&obfs-password=&sni=
```
