## Configuring CloudBeaver with Nginx

By default CloudBeaver listens to plain http protocol, processes all static content via the Jetty server and is not load balanced.  
All these issues can be resolved by putting a real web server in front of CloudBeaver.  
We can use Nginx as the most popular web server.

## Installing Nginx

```bash
sudo apt update
sudo apt install nginx
```

## Add proxy config

Open the Nginx configuration in your favorite text editor.  
The default Nginx config file is `/etc/nginx/sites-enabled/default`.  

```
  location / {
    proxy_pass       http://localhost:8978;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    proxy_set_header Host $http_host;
  }
```

To identify the information (_real IP address_) of client connected to the web server through NGINX, add the parameter `forwardProxy:true` into your [server configuration](https://github.com/dbeaver/cloudbeaver/wiki/Server-configuration#application-parameters).
 