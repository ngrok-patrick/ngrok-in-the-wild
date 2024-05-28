# Ngrok in the Wild !
Examples of Ngrok being used

### Ngrok Runtime Variables:
<sup>Ngrok has Environment Variables that can be access and use at Run-time. This is an example of fetching **${.http.request.url.host}** from Ngrok and rewriting it into the X-Original-Host Header. **(neato)**
```
ngrok http --host-header rewrite --request-header-add ‘X-Original-Host:${.http.request.url.host}’ --hostname exo.eu.ngrok.io 3003
```
### Allow only Your IP Address:
```
ngrok http 8080 --cidr-allow $(curl http://ifconfig.me/ip)/32
```
### Specify alternative Config file:
```
ngrok start --config=ngrok-phpws.yml phpwebservices
```
### Specify Authtoken:
```
ngrok --authtoken 6hwx4fgzL64i39E1YrbwL_7N3gm4wWub5a59twoXb7x http 80
```

### Where is my Config File:
    Linux: `~/.config/ngrok/ngrok.yml`
    MacOS (Darwin): `~/Library/Application Support/ngrok/ngrok.yml`
    Windows: `%HOMEPATH%\AppData\Local\ngrok\ngrok.yml`
```
ngrok config check
```

### Windows Servers (via RDP): 
```
ngrok tcp 3389
```

### MacOs Remote Desktop:
```
ngrok tcp 3389
```    

### Share file on Macos:
```
ngrok http "file:////tmp/php" 
```
### Share file Linux with Basic Authentication
```
./ngrok http "file:////tmp" --basic-auth="user:Password1!"
```

### Monitor Rest requests to Cloud Service
```
ngrok http https://companyx.okta.com --host-header rewrite --subdomain companyx
```

### Simple example of using ngrok CLI with OIDC

```
ngrok http 80 --oidc https://companyx.okta.com  --oidc-client-id 0oa1q3k3t8ohIF9BZ1d8  --oidc-client-secret xnjEWp-LCfPSX8yJdQ4_YYLEB7YHZ2ZiKkZU1xgItY-EQwo0p6_WnpvzZA4kbrC
```
