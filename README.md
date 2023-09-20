# wireguard-bootstrap
Public Repo for a quick Wireguard VPN

## Instructions

1. `docker-compose up -d`
2. navigate to `<VPN IP>:5000`

3. Under `Post Up Script` add:
`iptables -A FORWARD -i wg0 -j ACCEPT; iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE`

4. Under `Post Down Script` add:
`iptables -D FORWARD -i wg0 -j ACCEPT; iptables -t nat -D POSTROUTING -o eth0 -j MASQUERADE`

5. Create client configs in UI

Enjoy!
