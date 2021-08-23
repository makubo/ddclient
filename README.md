# ddclient
Ansible role for ddclient, with support of multiple protocol configuration.

Example role variables configuration:
```yaml
ddclient_router:
  type: web
  options:
    web: "dynamicdns.park-your-domain.com/getip"

ddclient_protocol:
- protocol: namecheap
  server: "dynamicdns.park-your-domain.com"
  login: "example.io"
  password: "xxxxx"
  domains:
  - dev
  - test
- protocol: dyndns2
  server: "dynupdate.no-ip.com"
  login: "my@mail.com"
  password: "xxxxx"
  domains:
  - example.ddns.net
```

Example output ddclient configuration:
```
# Ansible managed
# Configuration file for ddclient
#
# /etc/ddclient.conf

use=web, web=dynamicdns.park-your-domain.com/getip

protocol=namecheap
server=dynamicdns.park-your-domain.com
login=example.io
password=xxxxx
dev, test

protocol=dyndns2
server=dynupdate.no-ip.com
login=my@mail.com
password=xxxxx
example.ddns.net
```
