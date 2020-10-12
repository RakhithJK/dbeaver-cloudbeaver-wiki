CloudBeaver container image is on DockerHub: https://hub.docker.com/r/dbeaver/cloudbeaver.  
- `dbeaver/cloudbeaver:latest` - latest release build.
- `dbeaver/cloudbeaver:dev` - latest developer build.

#### Installation 
So to install the latest version of CloudBeaver use the following script:

```sh
sudo docker pull dbeaver/cloudbeaver:latest
```

#### Running 
To run cloudbaver in terminal:
```sh
sudo docker run -ti -p 8978:8978 dbeaver/cloudbeaver:latest
```

Then switch to the browser and open http://localhost:8978/

#### Daemon mode

```sh
sudo docker run -d --restart unless-stopped -p 80:8978 dbeaver/cloudbeaver:latest
```

#### Accessing databases on the localhost

If you need to access database server on the host machine add the following parameter in docker run:
```
 --network host
```

