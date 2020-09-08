CloudBeaver container image is on DockerHub: https://hub.docker.com/r/dbeaver/cloudbeaver.  

So to install the latest version of CloudBeaver use following script:

```sh
sudo docker pull dbeaver/cloudbeaver:latest
sudo docker run -d -ti 8978:8978 dbeaver/cloudbeaver:latest
```

Then switch to the browser and open http://localhost:8978/

That's it.
