# Ngrok-in-the-wild
Examples of Ngrok being used

### Allow only Your IP:
```
ngrok http 8080 --cidr-allow $(curl http://ifconfig.me/ip)/32
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

### Monitor Rest requests to Cloud Service
```
ngrok http https://companyx.okta.com --host-header rewrite --subdomain companyx
```

