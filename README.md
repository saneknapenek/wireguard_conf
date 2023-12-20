# Wireguard configs
---
#### server
```bash
echo "net.ipv4.ip_forward=1" >> /etc/sysctl.conf
systemctl enable wg-quick@wg0.service
systemctl start wg-quick@wg0.service
```
#### client
```bash
wg genkey | tee privatekey | wg pubkey > publickey
wg-quick up wg0.conf
```
