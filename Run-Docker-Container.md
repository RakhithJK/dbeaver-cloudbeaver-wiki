CloudBeaver container image is on DockerHub: https://hub.docker.com/r/dbeaver/cloudbeaver.  

So to install the latest version of CloudBeaver use following script:

```sh
docker pull dbeaver/cloudbeaver:latest
docker run -d -p 8978:8978 dbeaver/cloudbeaver:latest
```

