## Configuring CloudBeaver with Nginx

Out of the box CloudBeaver listens plain http protocol, processes all static content via Jetty server and isn't load balanced.  
All these issues can be resolved by putting some real web server in front of CloudBeaver.  
We will use Nginx as the most popular web server.

## Installing Nginx

```bash
sudo apt update
sudo apt install nginx
```

## Add proxy config

Open Nginx configuration in your favorite text editor.  
Default Nginx config file is `/etc/nginx/sites-enabled/default`.  

```
  location / {
    proxy_pass       http://localhost:8978;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header Host $http_host;
  }
```
