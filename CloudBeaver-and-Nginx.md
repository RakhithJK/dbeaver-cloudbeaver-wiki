## Configuring CloudBeaver with Nginx

Out of the box CloudBeaver listens plain http protocol, processes all static content via Jetty server and isn't load balanced.  
All these issues can be resolved by putting some real web server in front of CloudBeaver.  
We will use Nginx as the most popular web server.

## Installing Nginx

