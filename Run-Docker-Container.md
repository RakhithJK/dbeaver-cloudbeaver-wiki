CloudBeaver container image is on DockerHub: https://hub.docker.com/r/dbeaver/cloudbeaver.  

So to install the latest version of CloudBeaver use the following script:

```sh
sudo docker pull dbeaver/cloudbeaver:latest
```

To run cloudbaver in terminal:
```sh
sudo docker run -ti -p 8978:8978 dbeaver/cloudbeaver:latest
```

Then switch to the browser and open http://localhost:8978/

Note: use image `dbeaver/cloudbeaver:dev` to get the latest developer build.

Running in daemon mode: 
```sh
sudo docker run -d --restart unless-stopped -p 80:8978 dbeaver/cloudbeaver:latest
```

That's it.

