# Caddy
: HTTP/2 지원  
: Automatic HTTPS


**Caddy Install**
```bash
# caddy v2
$ sudo yum install yum-plugin-copr
$ sudo yum copr enable @caddy/caddy
$ sudo yum install caddy
$ caddy version

$ sudo systemctl status caddy

$ caddy adapt --config Caddyfile >> config.json
$ caddy start --config config.json
```


**Caddyfile**   
https://caddyserver.com/docs/caddyfile/concepts

```
example.com {
    root
    file_server
    reverse_proxy
    ...
}
```



[top](#)
